**_.chunk(array, [size=1])**

Creates an array of elements split into groups the length of size. If collection can’t be split evenly, the final chunk will be the remaining elements.

Returns the new array containing chunks.
```javascript
_.chunk([], 0);
// → []

_.chunk([1, 2], 0);
// → [[1], [2]]

_.chunk([1, 2], 1);
// → [[1], [2]]

_.chunk([1, 2], 2);
// → [[1, 2]]

_.chunk([1, 2], 3);
// → [[1, 2]]

_.chunk([1, 2, 3], 2);
// → [[1, 2], [3]]
```
**_.compact(array)**

Creates an array with all falsey values removed. The values false, null, 0, "", undefined, and NaN are falsey.

Returns the new array of filtered values.
```javascript
_.compact([0, false, "", undefined, NaN]);
// → []

_.compact(["", undefined, NaN, 3, "apples"]);
// → [3, "apples"]

_.compact([3, "apples"]);
// → [3, "apples"]

_.compact([]);
// → []
```
**_.difference(array, [values])**

Creates an array excluding all values of the provided arrays using SameValueZero for equality comparisons. (The internal comparison abstract operation SameValueZero(x, y), where x and y are ECMAScript language values, produces true or false.)

Returns the new array of filtered values.
```javascript
_.difference([1, 2, 3], [4, 2]);
// → [1, 3]

_.difference([1, 2, 3], [4]);
// → [1, 2, 3]

_.difference([], [4]);
// → []

_.difference([1, 2, 3], []);
// → [1, 2, 3]

_.difference([], []);
// → []

_.difference([1], [1,2,3]);
// → []

_.difference([1], [2,3]);
// → [1]
```
**_.drop(array, [n=1])**

Creates a slice of array with n elements dropped from the beginning.

Returns the slice of array.
```javascript
_.drop([1, 2, 3]);
// → [2, 3]

_.drop([1, 2, 3], 2);
// → [3]

_.drop([1, 2, 3], 4);
// → []

_.drop([1, 2, 3], -1);
// → [1, 2, 3]

_.drop([1, 2, 3], 0);
// → [1, 2, 3]

_.drop([], 2);
// → []
```
**_.dropRight(array, [n=1])**

Creates a slice of array with n elements dropped from the end.

Returns the slice of array.
```javascript
_.dropRight([1, 2, 3]);
// → [1, 2]

_.dropRight([1, 2, 3], 2);
// → [1]

_.dropRight([1, 2, 3], 4);
// → []

_.dropRight([1, 2, 3], 0);
// → [1, 2, 3]

_.dropRight([1, 2, 3], -1);
// → [1, 2, 3]

_.dropRight([]);
// → []
```
**\_.dropRightWhile(array, [predicate=\_.identity], [thisArg])**

Creates a slice of array excluding elements dropped from the end. Elements are dropped until predicate returns falsey. The predicate is bound to thisArg and invoked with three arguments: (value, index, array).

Returns the slice of array.
```javascript
_.dropRightWhile([1, 2, 3], function(n) {
  return n > 1;
});
// → [1]

_.dropRightWhile([1, 2, 3], function(n) {
  return n == 2;
});
// → [1, 2, 3]

_.dropRightWhile([1, 2, 3], function(n) {
  return n == 3;
});
// → [1, 2]

_.dropRightWhile([1, 2, 3], function(n) {
  return n > 3;
});
// → [1, 2, 3]

_.dropRightWhile([1, 2, 3], function(n) {
  return n == 4;
});
// → [1, 2, 3]
```
**\_.dropWhile(array, [predicate=\_.identity], [thisArg])**

Creates a slice of array excluding elements dropped from the beginning. Elements are dropped until predicate returns falsey. The predicate is bound to thisArg and invoked with three arguments: (value, index, array).

Returns the slice of array.
```javascript
_.dropWhile([1, 2, 3], function(n) {
  return n < 3;
});
// → [3]

_.dropWhile([1, 2, 3], function(n) {
  return n == 3;
});
// → [1, 2, 3]

_.dropWhile([1, 2, 3], function(n) {
  return n != 3;
});
// → [3]
```
**_.fill(array, value, [start=0], [end=array.length])**

Fills elements of array with value from start up to, but not including, end. This method mutates array.

Returns array.
```javascript
var array = [1, 2, 3];

_.fill(array, 'a');
// → ['a', 'a', 'a']

_.fill(Array(3), 2);
// → [2, 2, 2]

_.fill(Array(3), 3);
// → [3, 3, 3]

_.fill([4, 6, 8], '*', 1, 2);
// → [4, '*', 8]

_.fill([4, 6, 8], '*', 1, 3);
// → [4, "*", "*"]
```
**\_.findIndex(array, [predicate=\_.identity], [thisArg])**

This method is like \_.find except that it returns the index of the first element predicate returns truthy for instead of the element itself.

Returns the index of the found element, else -1.
```javascript
var numbers = [{1:"a", 2:"b"}, {3:"c"}, {4:"d"}];

_.findIndex(numbers, 2, "b");
// → 0

_.findIndex(numbers, 3, "c");
// → 1

_.findIndex(numbers, "c");
// → -1

_.findIndex(numbers, 3);
// → 1

_.findIndex(numbers, 1);
// → 0

_.findIndex(numbers, 4);
// → 2
```
**\_.findLastIndex(array, [predicate=\_.identity], [thisArg])**

This method is like \_.findIndex except that it iterates over elements of collection from right to left.

Returns the index of the found element, else -1.
```javascript
var numbers = [{1:"a", 2:"b"}, {3:"c"}, {4:"d"}, {2:"e"}];

_.findLastIndex(numbers, 2);
// → 3

_.findLastIndex(numbers, 2, "b");
// → 0

_.findLastIndex(numbers, "b");
// → -1
```
**_.first(array)**

Gets the first element of array.

Returns the first element of array.
```javascript
_.first([2,3,4]);
// → 2

_.first([]);
// → undefined

_.first([null]);
// → null

_.first([NaN]);
// → NaN
```
**_.flatten(array, [isDeep])**

Flattens a nested array. If isDeep is true the array is recursively flattened, otherwise it is only flattened a single level.

Returns the new flattened array.
```javascript
_.flatten([1, [2, 3, [4]]]);
// → [1, 2, 3, [4]]

_.flatten([1, [2, 3, [4]]], true);
// → [1, 2, 3, 4]

_.flatten([1, [2, 3, [4]]], false);
// → [1, 2, 3, [4]]

_.flatten([1, [2, 3, 4]]);
// → [1, 2, 3, 4]

_.flatten([1, []]);
// → [1]

_.flatten([[]]);
// → []
```
**_.flattenDeep(array)**

Recursively flattens a nested array.

Returns the new flattened array.
```javascript
_.flattenDeep([1, [2, 3, [4]]]);
// → [1, 2, 3, 4]

_.flattenDeep([1, [2, 3, []]]);
// → [1, 2, 3]

_.flattenDeep([[]]);
// → []
```
**_.indexOf(array, value, [fromIndex=0])**

Gets the index at which the first occurrence of value is found in array using SameValueZero for equality comparisons. If fromIndex is negative, it is used as the offset from the end of array. If array is sorted providing true for fromIndex performs a faster binary search.

[fromIndex=0] (boolean|number): The index to search from or true to perform a binary search on a sorted array.

Returns the index of the matched value, else -1.
```javascript
_.indexOf([1, 2, 1, 2], 2);
// → 1

_.indexOf([1, 2, 1, 2], 0);
// → -1

_.indexOf([1, 2, 1, 2], 1);
// → 0

_.indexOf([1, 2, 1, 2], 1, 1); // using `fromIndex`
// → 2

_.indexOf([1, 2, 1, 2], 1, 2);
// → 2

_.indexOf([1, 2, 1, 2], 1, 3);
// → -1

_.indexOf([1, 1, 2, 2], 2, true); // performing a binary search
// → 2
```
**_.initial(array)**

Gets all but the last element of array.

Returns the slice of array.
```javascript
_.initial([1, 2, 3]);
// → [1, 2]

_.initial([]);
// → []
```
**_.intersection([arrays])**

Creates an array of unique values in all provided arrays using SameValueZero for equality comparisons.

Returns the new array of shared values.
```javascript
_.intersection([1, 2], [4, 2], [2, 1]);
// → [2]

_.intersection([1, 2], [4, 2], [0, 1]);
// → []

_.intersection([1, [2]], [4, [2], 1]);
// → [1]
```
**_.last(array)**

Gets the last element of array.

Returns the last element of array.
```javascript
_.last([1, 2, 3]);
// → [3]

_.last([]);
// → undefined

_.last([[]]);
// → []
```
**_.lastIndexOf(array, value, [fromIndex=array.length-1])**

This method is like \_.indexOf except that it iterates over elements of array from right to left.

Returns the index of the matched value, else -1.
```javascript
_.lastIndexOf([1, 2, 1, 2], 2);
// → 3

_.lastIndexOf([1, 2, 1, 2], 2, 2); // using `fromIndex`
// → 1

_.lastIndexOf([1, 1, 2, 2], 2, true); // performing a binary search
// → 3

_.lastIndexOf([1, 2, 1, 2], 3);
// → -1

_.lastIndexOf([1, 2, 1, 2], 1, 1);
// → 0
```
**_.pull(array, [values])**

Removes all provided values from array using SameValueZero for equality comparisons.

Returns array.
```javascript
var array = [1, 2, 3, 1, 2, 3];

_.pull(array, 2, 3);
// → [1, 1]

_.pull(array, 1, 2, 3);
// → []
```
**_.pullAt(array, [indexes])**

Removes elements from array corresponding to the given indexes and returns an array of the removed elements. Indexes may be specified as an array of indexes or as individual arguments. Unlike \_.at, this method mutates array.

Returns the new array of removed elements.

```javascript
var array = [5, 10, 15, 20];
var evens = _.pullAt(array, 1, 3);

array;
// → [5, 15]

evens;
// → [10, 20]

var array = [];
var evens = _.pullAt(array, 0, 3);

array;
// → []

evens;
// → [undefined, undefined]
```
