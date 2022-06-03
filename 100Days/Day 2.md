# Day 2

## What I Learned :

• Today I learned how to implement a custom loading spinner into a `UICollectionView` or `UITableView` 

```
extension UICollectionView {
    
    public func showLoadingSpinner(show: Bool) {
        let loadingAnimationView = SpinnerLoading()
        if show {
            loadingAnimationView.showOnCollectionView(view: self)
        } else {
            for aview in self.subviews {
                aview.removeFromSuperview()
            }
        }
    }
    
}
```

• also I learned how to scroll `UITableView` with `Offset` 

#### here's the two combined result :


https://user-images.githubusercontent.com/89042174/171775106-ff929765-42e3-485b-a5f4-bff3132d4221.mp4


## What I Accomplished :

• I finally created a custom class that generate the API url to get advanced and complex recipes for [iCookPad](https://github.com/JoJoDevAdventure/iCookPad)

• I Fixed an error : Removing loading view from super view
• I almost finished `TheKitchedViewController` in my [iCookPad](https://github.com/JoJoDevAdventure/iCookPad) App
• I Created a photo that clarify [Bounds Vs. Frame](https://github.com/JoJoDevAdventure/Swift-Interview/tree/main/Bounds%20vs.%20Frame) in my [Swift Interview](https://github.com/JoJoDevAdventure/Swift-Interview) repo

#### Here's what it looks like 

![Bounds vs Frame](https://user-images.githubusercontent.com/89042174/171775138-4ab0fa2e-b085-4fed-9c36-90599828364d.jpg)

## What  I Want to learn :

- [ ] Finish one more topic in [Swift Interview](https://github.com/JoJoDevAdventure/Swift-Interview) repo
- [ ] Work on messaging in skate app 
- [ ] Creat a repo with some cool animations test
- [ ] Creat my own library that I can use with swift package manager
- [ ] Creat a Simple app with Realm


