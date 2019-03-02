# Array Unique Count Solutiono Explanation
 
#### Solution 1
```
let sorted = self.sorted(by: <)
```
* First we need to recognize that the self variable is referring to the array having the function called on it.
* We are assigning the decreasing version of this array to a constant (unchangable) variable called sorted
* For example, if the passed array is [7,2,8], sorted would equal [2,7,8]
```
let start: (Element?, Int) = (.none, 0)
```
* Here we are creating a tuple of (Element?, Int). A tuple is very similar to a struct. More can be read about them here: https://medium.com/swift-programming/swift-tuple-328aecff50e7
* In this line we are also assigning a value to the element value = .none (AKA last element inspected) and our Int value to 0
```
let result = sorted.reduce(start) { (previous, currentElement) in
    var uniqueCount = previousResult.1
    if (previousResult.0 != currentElement) {
        uniqueCount += 1
    }
    return ((currentElement, uniqueCount))
}
```
* Here we are creating a constant (unchangable) variable result that set to the "reduce" our previous created sorted variable
* The reduce function will take the sorted array and compare an element to its previous element. If they are equal, it will bump our unique counter and then assign the current element being checked as the previous element for the next iteration. Finally, once all elements have been looped,  it will return a tuple of the last checked element as well as the unique count total.
* previousResult.0 is the previously checked element in the array
* uniqueCount is the current number of unique numbers in the array
* the current element is the current element being checked in the array
```
    return result.1
```
* This final return is the getting the "1" index element in the resulting tuple (AKA the unique count amount)
