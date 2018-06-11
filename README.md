# MSPeekCollectionViewDelegateImplementation



## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

- XCode 9.3
- Swift 3.2

## Installation

MSPeekCollectionViewDelegateImplementation is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'MSPeekCollectionViewDelegateImplementation'
```

## Usage

### Storyboard
1. Drag-Drop a `UICollectionView`

2. Set the scroll direction to horizontal

3. Remove show vertical indicator and show horizontal indicator

4. Set the deceleration rate to fast
```swift
collectionView.decelerationRate = UIScrollViewDecelerationRateFast
```

5. Set the minimum spacing to `0` for cells and lines

2. Add a `UICollectionViewCell`

3. Set the reuse identifier to `Cell`

4. Create a reference for the collection view
```swift
@IBOutlet weak var collectionView: UICollectionView!
```

4. Bind collection view to outlet

5. Import library
```swift
import MSPeekCollectionViewDelegateImplementation
```

5. Create a global variable of type `MSPeekCollectionViewDelegateImplementation`
```swift
var delegate: MSPeekCollectionViewDelegateImplementation!
```

6. Initialize the variable in `viewDidLoad()`
```swift
delegate = MSPeekCollectionViewDelegateImplementation(itemWidth: width, itemsCount: count)
```
Where `width` is your desired width and `count` is the total number of item

7. In `viewDidLoad()`, set the collection view's delegate:
```swift
collectionView.delegate = delegate
```
8. Create the data source implementation
```swift
extension ViewController: UICollectionViewDataSource {
    func numberOfSections(in collectionView: UICollectionView) -> Int {
        return 1
    }
    
    func collectionView(_ collectionView: UICollectionView, numberOfItemsInSection section: Int) -> Int {
        return 4
    }
    
    func collectionView(_ collectionView: UICollectionView, cellForItemAt indexPath: IndexPath) -> UICollectionViewCell {
        let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "Cell", for: indexPath)
        return cell
    }
}
```

9. In `viewDidLoad()`, Set the collection view's data source to `self`
```swift
collectionView.dataSource = self
```

## Author

maher.santina90@gmail.com, maher.santina90@gmail.com

## License

MSPeekCollectionViewDelegateImplementation is available under the MIT license. See the LICENSE file for more info.
