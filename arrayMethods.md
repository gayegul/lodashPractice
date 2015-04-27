**_.chunk(array, [size=1])**

Creates an array of elements split into groups the length of size. If collection can’t be split evenly, the final chunk will be the remaining elements.

Returns the new array containing chunks.
```javascript
_.chunk([], 0);
[]

_.chunk([1, 2], 0);
[[1], [2]]

_.chunk([1, 2], 1);
[[1], [2]]

_.chunk([1, 2], 2);
[[1, 2]]

_.chunk([1, 2], 3);
[[1, 2]]

_.chunk([1, 2, 3], 2);
[[1, 2], [3]]
```
**_.compact(array)**

Creates an array with all falsey values removed. The values false, null, 0, "", undefined, and NaN are falsey.

Returns the new array of filtered values.
```javascript
_.compact([0, false, "", undefined, NaN]);
[]

_.compact(["", undefined, NaN, 3, "apples"]);
[3, "apples"]

_.compact([3, "apples"]);
[3, "apples"]

_.compact([]);
[]
```
**_.difference(array, [values])**

Creates an array excluding all values of the provided arrays using SameValueZero for equality comparisons. (The internal comparison abstract operation SameValueZero(x, y), where x and y are ECMAScript language values, produces true or false.)

Returns the new array of filtered values.
```javascript
_.difference([1, 2, 3], [4, 2]);
[1, 3]

_.difference([1, 2, 3], [4]);
[1, 2, 3]

_.difference([], [4]);
[]

_.difference([1, 2, 3], []);
[1, 2, 3]

_.difference([], []);
[]

_.difference([1], [1,2,3]);
[]

_.difference([1], [2,3]);
[1]
```
**_.drop(array, [n=1])**

Creates a slice of array with n elements dropped from the beginning.

Returns the slice of array.
```javascript
_.drop([1, 2, 3]);
[2, 3]

_.drop([1, 2, 3], 2);
[3]

_.drop([1, 2, 3], 4);
[]

_.drop([1, 2, 3], -1);
[1, 2, 3]

_.drop([1, 2, 3], 0);
[1, 2, 3]

_.drop([], 2);
[]
```
**_.dropRight(array, [n=1])**

Creates a slice of array with n elements dropped from the end.

Returns the slice of array.
```javascript
_.dropRight([1, 2, 3]);
[1, 2]

_.dropRight([1, 2, 3], 2);
[1]

_.dropRight([1, 2, 3], 4);
[]

_.dropRight([1, 2, 3], 0);
[1, 2, 3]

_.dropRight([1, 2, 3], -1);
[1, 2, 3]

_.dropRight([]);
[]
```
**\_.dropRightWhile(array, [predicate=\_.identity], [thisArg])**

Creates a slice of array excluding elements dropped from the end. Elements are dropped until predicate returns falsey. The predicate is bound to thisArg and invoked with three arguments: (value, index, array).

Returns the slice of array.
```javascript
_.dropRightWhile([1, 2, 3], function(n) {
  return n > 1;
});
[1]

_.dropRightWhile([1, 2, 3], function(n) {
  return n == 2;
});
[1, 2, 3]

_.dropRightWhile([1, 2, 3], function(n) {
  return n == 3;
});
[1, 2]

_.dropRightWhile([1, 2, 3], function(n) {
  return n > 3;
});
[1, 2, 3]

_.dropRightWhile([1, 2, 3], function(n) {
  return n == 4;
});
[1, 2, 3]
```
**\_.dropWhile(array, [predicate=\_.identity], [thisArg])**

Creates a slice of array excluding elements dropped from the beginning. Elements are dropped until predicate returns falsey. The predicate is bound to thisArg and invoked with three arguments: (value, index, array).

Returns the slice of array.
```javascript
_.dropWhile([1, 2, 3], function(n) {
  return n < 3;
});
[3]

_.dropWhile([1, 2, 3], function(n) {
  return n == 3;
});
[1, 2, 3]

_.dropWhile([1, 2, 3], function(n) {
  return n != 3;
});
[3]
```
