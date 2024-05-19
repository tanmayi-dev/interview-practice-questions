[Must Do Coding Questions - GFG](https://www.geeksforgeeks.org/must-do-coding-questions-for-companies-like-amazon-microsoft-adobe/)


# Most asked Coding Questions

- [Arrays and Strings](#arrays)
- [Searching and Sorting](#sort)
- [Stacks](#stacks)
- [Queues](#queues)
- [Linked Lists](#linkedlist)
- [Heaps](#heaps)
- [Trees and BST](#trees)
- [Dynamic Programming](#dp)
- [Graphs](#graphs)
- [Miscellaneous](#misc)

## Arrays and Strings <a id="arrays"></a>

### 1. Find the missing number in an array of integers - [gfg](https://www.geeksforgeeks.org/find-the-missing-number/), [tuf](https://takeuforward.org/arrays/find-the-missing-number-in-an-array/)
<details>
<summary>Answer</summary>
<p>

1. Linear Search - O(N^2)
2. Hashing - O(2*N)
3. Summation Approach - O(N)
4. XOR Approach - O(N)

```java

// XOR Implementation

import java.util.*;

public class tUf {
    public static int missingNumber(int []a, int N) {

        int xor1 = 0, xor2 = 0;

        for (int i = 0; i < N - 1; i++) {
            xor2 = xor2 ^ a[i]; // XOR of array elements
            xor1 = xor1 ^ (i + 1); //XOR up to [1...N-1]
        }
        xor1 = xor1 ^ N; //XOR up to [1...N]

        return (xor1 ^ xor2); // the missing number
    }

    public static void main(String args[]) {
        int N = 5;
        int a[] = {1, 2, 4, 5};

        int ans = missingNumber(a, N);
        System.out.println("The missing number is: " + ans);
    }
}



```

</p>
</details>

---

### 2. Implement an algorithm to rotate an array - [gfg](https://www.geeksforgeeks.org/array-rotation/)

    ```
    Input: 
    N = 7, d = 2 ,arr[] = {1, 2, 3, 4, 5, 6, 7}
    Output: 3 4 5 6 7 1 2
    
    Input: N = 7, d=2 , arr[] = {3, 4, 5, 6, 7, 1, 2},
    Output: 5 6 7 1 2 3 4
    ```
<details>
<summary>Answer</summary>
<p>

1. Using Temp Array
2. Rotate one by one
3. Juggling Algorithm - use GCD
4. Reversal Algorithm

```java

```

</p>
</details>

---

### 3. Check if a string is a palindrome [leetcode](https://leetcode.com/problems/valid-palindrome/description/)
<details>
<summary>Answer</summary>
<p>

```java
class Solution {
  public boolean isPalindrome(String s) {
    int l = 0;
    int r = s.length() - 1;

    while (l < r) {
      while (l < r && !Character.isLetterOrDigit(s.charAt(l)))
        ++l;
      while (l < r && !Character.isLetterOrDigit(s.charAt(r)))
        --r;
      if (Character.toLowerCase(s.charAt(l)) != Character.toLowerCase(s.charAt(r)))
        return false;
      ++l;
      --r;
    }

    return true;
  }
}
```

</p>
</details>

---

### 4. Find the first non-repeating character in a string
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 5. Write a program to remove duplicates from a sorted array
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 6. Reverse a String - [link](https://www.geeksforgeeks.org/problems/reverse-a-string/1)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

### 7. Reverse each word in a string - [link](https://leetcode.com/problems/reverse-words-in-a-string-iii/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 8. Reverse words in a string - [link](https://leetcode.com/problems/reverse-words-in-a-string/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 9. Check for Palindrome - [link](https://leetcode.com/problems/valid-palindrome/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 10. Anagram Question - [link](https://leetcode.com/problems/valid-anagram/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 11. Check for Balanced Parenthesis - [link](https://www.geeksforgeeks.org/check-for-balanced-parentheses-in-an-expression/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 12. Two Sum - [link](https://leetcode.com/problems/two-sum/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 13. FizzBuzz - [link](https://leetcode.com/problems/fizz-buzz/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 14. Write a program to print the occurrences of capital and small letters and count of strings
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 15. Find the greatest element to its right in an array
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 16. Maximum Sum Subarray : Kadane's Algorithm
```
Input:
Arr[] = {1,2,3,-2,5}

Output:

9
Explanation:
Max subarray sum is 9 of elements (1, 2, 3, -2, 5) which is a contiguous subarray.
```
<details>
<summary>Answer</summary>
<p>


```java
import java.util.*;
import java.lang.*;
import java.io.*;
class Main {
    public static int maximumSubarraySum(int[] arr) {
        int n = arr.length;
        int maxSum = Integer.MIN_VALUE;

        for (int i = 0; i <= n - 1; i++) {
            int currSum = 0;
            for (int j = i; j <= n - 1; j++) {
            currSum += arr[j];
            if (currSum > maxSum) {
                maxSum = currSum;
            }
            }
        }

        return maxSum;
    }
    public static void main(String args[]) {
        // Your code goes here
        int a[] = {1, 2, 3, -2, 5};
        System.out.println(maximumSubarraySum(a));
    }
}
```

</p>
</details>

---


## Searching and Sorting <a id="sort"></a>

### 1. Implement Binary Search
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 2. Find the kth smallest / largest element in an array
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 3. Implement Bubble Sort
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 4. Implement Selection Sort
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 5. Implement Merge Sort
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 6. Implement Quick Sort
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 7. Count the number of inversions in an array
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 8. Search in a Rotated Sorted Array
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 9. Implement a sorting algorithm for linked lists
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 10. Sort an array of 0s and 1s
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

## Stacks <a id="stacls"></a>

### 1. 
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

## Queues <a id="queues"></a>

### 1. 
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

## Linked Lists <a id="linkedlist"></a>

### 1. Implement an algorithm to reverse a linked list
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 2. Detect a cycle in a linked list
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 3. Find the intersection point of two linked lists
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 4. Reverse a linked list in a groups of k
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 5. Implement a function to add two numbers represented by linked lists
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 6. Clone a linked list with next and random pointer
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

## Heaps <a id="heaps"></a>

### 1. 
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---


## Trees and Binary Search Trees (BST) <a id="trees"></a>

### 1. Find the height of a binary tree
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 2. Check if a binary tree is balanced
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 3. Find the lowest common ancestor in a binary tree
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 4. Serialize and deserialize a binary tree
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 5. Implement an algorithm for in-order traversal without recursion
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 6. Convert a BST to a sorted doubly linked list
<details>
<summary>Answer</summary>
<p>



</p>
</details>


---

### 7. Invert a Binary Tree
<details>
<summary>Answer</summary>
<p>



</p>
</details>


---

### 8. Write algorithm to find if Binary Tree is a Binary Search Tree
<details>
<summary>Answer</summary>
<p>



</p>
</details>


---

## Dynamic Programming <a id="dp"></a>

### 1. Find the longest common subsequence
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 2. Calculate the nth Fibonacci number using dynamic programming - [link](https://leetcode.com/problems/fibonacci-number/description/)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 3. Coin Change problem
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 4. Longest Increasing Subsequence
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 5. Knapsack Problem
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### example
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

## Graphs and DFS / BFS <a id="graphs"></a>

### 1. Implement depth-first search (DFS) and breadth-first search (BFS)
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 2. Check if a Graph is cyclic
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 3. Shortest path in a weighted graph (Dijkstra's or Bellman-Ford)
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 4. Topological sort of a Directed Acyclic Graph (DAG)
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 5. Count the number of connected components in an undirected graph
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### example
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---



## Miscellaneous <a id="misc"></a>

### 1. Implement a LRU (Least Recently Used) Cache
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 2. Find the median of two sorted arrays
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 3. Implement a stack that supports push, pop, top and retrieving minimum element in constanct time
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### 4. Design a data structure that supports insert, delete, getRandom() operations in constant time
<details>
<summary>Answer</summary>
<p>



</p>
</details>

---

### 5. Check if a Sudoku is valid
<details>
<summary>Answer</summary>
<p>


</p>
</details>

---

### example
<details>
<summary>Answer</summary>
<p>



</p>
</details>



   
