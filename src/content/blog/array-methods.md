---
title: 'Array Methods'
description: 'Guide to using JS Array Methods'
pubDate: 'Jul 22 2022'
heroImage: '/array-methods.jpg'
---

JavaScript arrays are powerful data structures that come with a variety of built-in methods to manipulate, transform, and retrieve data efficiently. Here's a guide to the most commonly used array methods.

## Declaration

```javascript
const fruits = ['apple', 'banana', 'cherry'];
```

---

## 1. `.push()`

Adds one or more elements to the end of an array.

```javascript
fruits.push('date'); // ['apple', 'banana', 'cherry', 'date']
```

---

## 2. `.pop()`

Removes the last element of an array and returns it.

```javascript
const last = fruits.pop(); // 'date'
// fruits is now ['apple', 'banana', 'cherry']
```

---

## 3. `.shift()`

Removes the first element of an array and returns it.

```javascript
const first = fruits.shift(); // 'apple'
// ['banana', 'cherry']
```

---

## 4. `.unshift()`

Adds one or more elements to the beginning of an array.

```javascript
fruits.unshift('avocado'); // ['avocado', 'banana', 'cherry']
```

---

## 5. `.map()`

Creates a new array by transforming each element.

```javascript
const lengths = fruits.map(fruit => fruit.length); // [7, 6, 6]
```

---

## 6. `.filter()`

Creates a new array with elements that pass a test.

```javascript
const longNames = fruits.filter(fruit => fruit.length > 6); // ['avocado']
```

---

## 7. `.find()`

Returns the first element that matches a condition.

```javascript
const found = fruits.find(fruit => fruit.startsWith('b')); // 'banana'
```

---

## 8. `.includes()`

Checks if an array contains a specific value.

```javascript
fruits.includes('banana'); // true
```

---

## 9. `.indexOf()`

Returns the first index of the specified element.

```javascript
fruits.indexOf('cherry'); // 2
```

---

## 10. `.forEach()`

Executes a function for each array element.

```javascript
fruits.forEach(fruit => console.log(fruit.toUpperCase()));
// Output: AVOCADO BANANA CHERRY
```

---

## 11. `.reduce()`

Applies a function against an accumulator and returns a single value.

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, curr) => acc + curr, 0); // 10
```

---

## 12. `.slice()`

Returns a portion of the array without modifying it.

```javascript
const sliced = fruits.slice(1, 3); // ['banana', 'cherry']
```

---

## 13. `.splice()`

Changes the contents of an array by removing or replacing elements.

```javascript
fruits.splice(1, 1, 'blueberry'); 
// Removes 1 element at index 1 and inserts 'blueberry'
// Result: ['avocado', 'blueberry', 'cherry']
```

---

## 14. `.sort()`

Sorts the elements of an array in place.

```javascript
const nums = [10, 2, 30];
nums.sort(); // [10, 2, 30] — ⚠️ this sorts as strings
nums.sort((a, b) => a - b); // [2, 10, 30] ✅ correct numeric sort
```

---

## 15. `.reverse()`

Reverses the order of the array in place.

```javascript
nums.reverse(); // [30, 10, 2]
```

---

## Summary Table

| Method     | Description                            |
| ---------- | -------------------------------------- |
| `push()`   | Add to end                             |
| `pop()`    | Remove from end                        |
| `shift()`  | Remove from start                      |
| `unshift()`| Add to start                           |
| `map()`    | Transform items                        |
| `filter()` | Filter based on condition              |
| `find()`   | Find first matching item               |
| `includes()`| Check if value exists                 |
| `indexOf()`| Get index of a value                   |
| `forEach()`| Loop through array                     |
| `reduce()` | Get a single value from array          |
| `slice()`  | Get sub-array (non-mutating)           |
| `splice()` | Remove/replace items (mutating)        |
| `sort()`   | Sort elements                          |
| `reverse()`| Reverse order                          |

---

With these tools, you can manipulate arrays like a pro. Whether you're filtering data, transforming values, or simply iterating, mastering array methods is essential for every JavaScript developer.

