# Day 1

## What I Learned :

• Today I learned how to use a new frame work, [MessagesKit](https://github.com/MessageKit/MessageKit), I used it for the chat functionality in my [Let's Skate App](https://github.com/JoJoDevAdventure/Let-s-Skate)

• I Also knew more amore Utility and nice app arch (MVVM), I learned this new extension for ` NSLayoutConstraints ` :

<br>

```
extension NSLayoutConstraint {
    
    public static func pinToView(_ parent: UIView, _ child: UIView, padding: CGFloat = 0) {
        guard child.superview == nil else {
            fatalError("Unable to pin child view. It already has a parent.")
        }
        parent.addSubview(child)
        
        NSLayoutConstraint.activate([
            child.leftAnchor.constraint(equalTo: parent.leftAnchor, constant: padding),
            child.rightAnchor.constraint(equalTo: parent.rightAnchor, constant: -padding),
            child.topAnchor.constraint(equalTo: parent.topAnchor, constant: padding),
            child.bottomAnchor.constraint(equalTo: parent.bottomAnchor, constant: -padding)
        ])
    }
    
}
```


this add a view to a parents view and fix it with paddings, usefull for `UITableView` and `UICollectionView`.

• I'm getting used to the coordonator class that helps me to navigate in the app between view controller, I don't know if it's a got habbit but for now it looks pretty usefull.


## What I Accomplished : 

#### Loading screens :
when waiting for data to come, I added some cool loading screeens with lottie and a custom loading view.

###### here's what it looks like :

https://user-images.githubusercontent.com/89042174/171519743-fd88f1a1-9bf4-45db-acdf-f242c243f0bf.mp4

#### Messages UI :
after a longwait, I finally started the messaging UI, Chat view, and possibility to start a new chat :

###### here's what it looks like :

https://user-images.githubusercontent.com/89042174/171520009-66e2fb09-b19f-41a8-b08f-f24a0081045b.mp4

#### 

## What I Want to do :

- [X] Start messaging functionality
- [ ] Messaging ViewModel
- [ ] Messaging Manager ( Send, Fetch, Delete..)
- [ ] Learn about Realm
- [ ] Finish Frame vs. Bounds On [Interview Repo](https://github.com/JoJoDevAdventure/Swift-Interview)
