# Coding Questions

#### Write program to Reverse a String

#### Write program to search for an element in an array

#### Write a program to print the occurrences of capital and small letters and count of strings

### Find the greatest element to its right in an array

### Write a program for Bubble Sort

```js
function bubbleSort(arr) {
  const n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        // Swap the elements
        const temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }
}

// Test the bubbleSort function
const arrayToSort = [64, 34, 25, 12, 22, 11, 90];
console.log("Original array:", arrayToSort);
bubbleSort(arrayToSort);
console.log("Sorted array:", arrayToSort);
```

```js
// Swap function separated
function bubbleSort(arr) {
  var n = arr.length;
  for (var i = 0; i < n - 1; i++) {
    for (var j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        swap(arr, j, j + 1);
      }
    }
  }
}

function swap(arr, index1, index2) {
  var temp = arr[index1];
  arr[index1] = arr[index2];
  arr[index2] = temp;
}

// Example usage
var arrayToSort = [64, 34, 25, 12, 22, 11, 90];
console.log("Original array:", arrayToSort);
bubbleSort(arrayToSort);
console.log("Sorted array:", arrayToSort);
```

### Write a program for Merge Sort

### Write a program for Binary Search

### Write a program for Linear Search

9. Write code to sort an array of numbers using loops

10. Write code to reverse a string

11. Write code to remove the duplicates from the array of integers
