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

