# Day 4

## What I learned :

today I learned many things, and I accomplished some cool things

• I build a function that set a listener to any messages changes, it gets `MessageDB` model, then return `[Messages]`

#### here's what it looks like :

```
public func fetchAllMessages(forUser: User, completion: @escaping (Result<[Message], Error>) -> Void) {
        
        guard let currentUser = currentUser else {
            completion(.failure(MessagesError.ErrorFetchingMessages))
            return
        }
        guard let userID = forUser.id else {
            completion(.failure(MessagesError.ErrorNotValidUser))
            return
        }
        
        var messages: [MessageDB]?
        var fMessages = [Message]()
        fireRef.collection("users").document(currentUser.uid).collection("conversations").document(userID).collection("messages")
            .order(by: "date", descending: false)
            .addSnapshotListener { snapshot, error in
            messages = snapshot?.documents.map({try! $0.data(as: MessageDB.self)})
            
            guard let messages = messages else {
                completion(.failure(MessagesError.NoMessages))
                return
            }
            
            for message in messages {
                if !fMessages.contains(where: {$0.messageId == message.id}) {
                    var sender = Sender(photoURL: "", senderId: "", displayName: "")
                    if message.senderID == currentUser.uid {
                        sender = Sender(photoURL: "", senderId: currentUser.uid, displayName: "")
                    } else {
                        sender = Sender(photoURL: forUser.profileImageUrl, senderId: forUser.id!, displayName: forUser.nickname)
                    }
                    let fMessage = Message(messageId: message.id!, sender: sender, sentDate: message.date, kind: .text(message.content))
                    fMessages.append(fMessage)
                }
            }
            completion(.success(fMessages))
        }
    }
```

• I learned how to adjust UI For `MessageViewController` 

• I learned that Upwork takes 5 days for payement

## What I accomplished :

• I finished the messaging functionality, Now we can send messages !!

#### Here's what it looks like :

https://user-images.githubusercontent.com/89042174/172288786-ad650d95-090e-4726-9f51-d0acfe375d26.mp4

• I Finished some visual adjusement for my [Upwork profile](https://www.upwork.com/freelancers/~010eac1a9a4ea6edf2)

• I created a banner for my [SwiftUI Twitter App](https://github.com/JoJoDevAdventure/TwitterSwiftUI) 

#### here's what it looks like :

![twitter](https://user-images.githubusercontent.com/89042174/172289643-8133423d-253c-40a6-82b7-36c485d29997.jpg)

## What  I Want to learn : 

- [ ] Learn how to use a `UIScrollView` for my cooking app.
- [ ] Clean my mac storage 
- [ ] Upload the rest of netflix clone app on Youtube
