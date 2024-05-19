# Coding Questions based on Data Structures

- [Arrays](#arrays)
  - [1. Sort an Array](#a1)
  - [2. Sort an Array of 0s and 1s](#a2)
  - [3. Sort an array of 0s, 1s, and 2s (Dutch National Flag Problem)](#a3)
- [Linked Lists](#linkedlists)
  - [1. Reverse a Linked List](#l1)
  - [2. Detect a cycle in Linked list](#l2)
  - [3. Merge two sorted linked lists](#l3)
- [Trees](#trees)
  - [1. Binary Search Tree (BST) validation](#t1)
  - [2. Inorder Traversal of a Binary Tree](#t2)
  - [3. Lowest Common Ancestor in a Binary Tree](#t3)
- [String Manipulation](#stringm)
  - [1. Reverse a String](#sm1)
  - [2. Reverse Each Word in a String](#sm2)
  - [3. Reverse Words in a String without Reversing Each Word](#sm3)
- [Array Manipulation](#arraysm)
  - [1. Find Duplicates in an Array](#am1)
  - [2. Anagram Question](#am2)
- [Palindrome Checking](#palindrome)
  - [1. Check if a String is a Palindrome](#p1)
  - [2. Check if a String is a Palidrome with Ignored Characters](#p2)
- [Fibonacci Sequence](#fibonacci)
  - [1. Fibonacci Series using Iteration](#f1)
  - [2. Fibonacci Series using Recursion](#f2)
  - [3. Fibonacci Series using Memoization](#f3)
  - [4. Fibonacci Series using Dynamic Programming (Bottom-up approach)](#f4)
- [Stacks](#stacks)
  - [1. Implement a Stack using Arrays](#s1)
  - [2. Implement a Stack using Linked Lists](#s2)
  - [3. Check Balanced Parenthesis](#s3)
  - [4. Implement a Stack using Two Queues](#s4)
- [Queues](#queues)
  - [1. Implement Queue using Arrays](#q1)
  - [2. Implement Queue using Linked Lists](#q2)
  - [3. Implement Circular Queue](#q3)
- [Graphs](#graphs)
  - [1. Depth First Search](#g1)
  - [2. Breadth First Search](#g2)


## Arrays <a id="arrays"></a>

### 1. Sort an array: <a id="a1"></a>

- Question: Implement a function to sort an array of integers.
- Time Complexity: O(n log n) (for efficient sorting algorithms like quicksort or mergesort).
- Space Complexity: O(n) (for the auxiliary space used by sorting algorithms).

<details>
<summary>Bubble Sort</summary>
<p>

- Time Complexity: O(n^2) (quadratic time complexity).
- Space Complexity: O(1) (constant space complexity).
  
```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap arr[j] and arr[j + 1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        bubbleSort(arr);
        for (int i : arr) {
            System.out.print(i + " "); // Output: 11 12 22 25 34 64 90
        }
    }
}


  
```
</p>
</details>

<details>
<summary>Selection Sort</summary>
<p>
- Time Complexity: O(n^2) (quadratic time complexity).
- Space Complexity: O(1) (constant space complexity).

  
```java
public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIdx = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIdx]) {
                    minIdx = j;
                }
            }
            // Swap arr[minIdx] and arr[i]
            int temp = arr[minIdx];
            arr[minIdx] = arr[i];
            arr[i] = temp;
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        selectionSort(arr);
        for (int i : arr) {
            System.out.print(i + " "); // Output: 11 12 22 25 34 64 90
        }
    }
}

```
</p>
</details>

<details>
<summary>Insertion Sort</summary>
<p>
- Time Complexity: O(n^2) (quadratic time complexity).
- Space Complexity: O(1) (constant space complexity).

```java
public class InsertionSort {
    public static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        insertionSort(arr);
        for (int i : arr) {
            System.out.print(i + " "); // Output: 11 12 22 25 34 64 90
        }
    }
}

```

</p>
</details>

<details>
<summary>Merge Sort</summary>
<p>
- Time Complexity: O(n log n) (logarithmic time complexity).
- Space Complexity: O(n) (linear space complexity).

```java
public class MergeSort {
    public static void mergeSort(int[] arr) {
        if (arr.length < 2) return;
        int mid = arr.length / 2;
        int[] left = new int[mid];
        int[] right = new int[arr.length - mid];

        for (int i = 0; i < mid; i++) {
            left[i] = arr[i];
        }
        for (int i = mid; i < arr.length; i++) {
            right[i - mid] = arr[i];
        }

        mergeSort(left);
        mergeSort(right);
        merge(arr, left, right);
    }

    public static void merge(int[] arr, int[] left, int[] right) {
        int i = 0, j = 0, k = 0;
        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) {
                arr[k++] = left[i++];
            } else {
                arr[k++] = right[j++];
            }
        }
        while (i < left.length) {
            arr[k++] = left[i++];
        }
        while (j < right.length) {
            arr[k++] = right[j++];
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        mergeSort(arr);
        for (int i : arr) {
            System.out.print(i + " "); // Output: 11 12 22 25 34 64 90
        }
    }
}


```

</p>
</details>

<details>
<summary>Quick Sort</summary>
<p>

- Time Complexity: O(n log n) on average, O(n^2) in the worst case.
- Space Complexity: O(log n) on average due to recursion stack
  
```java
public class QuickSort {
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    public static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = (low - 1);
        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        quickSort(arr, 0, arr.length - 1);
        for (int i : arr) {
            System.out.print(i + " "); // Output: 11 12 22 25 34 64 90
        }
    }
}

```
</p>
</details>

---

### 2. Sort an array of 0s and 1s: <a id="a2"></a>

- Question: Given an array containing only 0s and 1s, rearrange the array so that all 0s come before 1s.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

<details>
<summary>New Array</summary>
<p>

```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {1, 0, 1, 0, 1, 0, 0, 1};
        int[] rearrangedArr = rearrangeWithNewArray(arr);
        for (int num : rearrangedArr) {
            System.out.print(num + " ");
        }
    }

    public static int[] rearrangeWithNewArray(int[] arr) {
        int[] result = new int[arr.length];
        int index = 0;
        // First, add all 0s to the new array
        for (int num : arr) {
            if (num == 0) {
                result[index++] = 0;
            }
        }
        // Then, add all 1s to the new array
        for (int num : arr) {
            if (num == 1) {
                result[index++] = 1;
            }
        }
        return result;
    }
}

```
</p>
</details>

<details>
<summary>Two Pointer</summary>
<p>
  
```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {1, 0, 1, 0, 1, 0, 0, 1};
        rearrangeWithTwoPointers(arr);
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }

    public static void rearrangeWithTwoPointers(int[] arr) {
        int left = 0;
        int right = arr.length - 1;
        while (left < right) {
            // Move left pointer until it encounters 1
            while (arr[left] == 0 && left < right) {
                left++;
            }
            // Move right pointer until it encounters 0
            while (arr[right] == 1 && left < right) {
                right--;
            }
            // Swap 0 at left pointer with 1 at right pointer
            if (left < right) {
                arr[left++] = 0;
                arr[right--] = 1;
            }
        }
    }
}


```
</p>
</details>

--- 
### 3. Sort an array of 0s, 1s, and 2s (Dutch National Flag Problem): <a id="a3"></a>

- Question: Given an array containing only 0s, 1s, and 2s, sort the array in linear time without using any sorting algorithm.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).


---
## Linked Lists <a id="linkedlists"></a>

### 1. Reverse a linked list: <a id="l1"></a>

- Question: Implement a function to reverse a singly linked list.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

---
### 2. Detect a cycle in a linked list: <a id="l2"></a>

- Question: Write a function to detect if a linked list contains a cycle.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

--- 
### 3. Merge two sorted linked lists: <a id="l3"></a>

- Question: Given two sorted linked lists, merge them into a single sorted linked list.
- Time Complexity: O(n + m) where n and m are the lengths of the two linked lists.
- Space Complexity: O(1) (constant space complexity).

---
## Trees <a id="trees"></a>

### 1. Binary Search Tree (BST) validation: <a id="t1"></a>

- Question: Write a function to determine if a binary tree is a valid binary search tree.
- Time Complexity: O(n) (linear time complexity where n is the number of nodes in the tree).
- Space Complexity: O(h) where h is the height of the tree (space complexity due to recursion).

---
### 2. Inorder Traversal of a Binary Tree: <a id="t2"></a>

- Question: Implement an inorder traversal of a binary tree (recursive or iterative).
- Time Complexity: O(n) (linear time complexity where n is the number of nodes in the tree).
- Space Complexity: O(h) where h is the height of the tree (space complexity due to recursion or stack space in the iterative approach).

---
### 3. Lowest Common Ancestor in a Binary Tree: <a id="t3"></a>

- Question: Given a binary tree, find the lowest common ancestor of two given nodes in the tree.
- Time Complexity: O(n) (linear time complexity where n is the number of nodes in the tree).
- Space Complexity: O(h) where h is the height of the tree (space complexity due to recursion).

---
## String Manipulation <a id="stringm"></a>

### 1. Reverse a String: <a id="sm1"></a>

- Question: Implement a function to reverse a given string.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

- [Gfg article](https://www.geeksforgeeks.org/reverse-a-string-in-java/), [String vs StringBuffer vs String Builder](https://www.geeksforgeeks.org/string-vs-stringbuilder-vs-stringbuffer-in-java/)

- Objects of String are immutable.
- String class in Java does not have reverse() method, however, the StringBuilder class has built-in reverse() method.
- StringBuilder class do not have toCharArray() method, while String class does have toCharArray() method.

```
Input : Hello, World!
Output : !dlroW ,olleH
```

<details>
<summary>Brute Force with <code>String</code></summary>
<p>

```java
public class ReverseString {

    public static String reverseStringBruteForce(String s) {
        String reversed = "";
        for (int i = s.length() - 1; i >= 0; i--) {
            reversed += s.charAt(i);
        }
        return reversed;
    }

    public static void main(String[] args) {
        String inputString = "Hello, World!";
        System.out.println("Original String: " + inputString);
        System.out.println("Reversed String (Brute Force): " + reverseStringBruteForce(inputString));
    }
}
```
</p>
</details>

<details>
<summary>Two pointer - swap characters</summary>
<p>

```java
public class ReverseString {

    public static String reverseStringEfficient(String s) {
        char[] charArray = s.toCharArray();
        int left = 0;
        int right = charArray.length - 1;
        while (left < right) {
            char temp = charArray[left];
            charArray[left] = charArray[right];
            charArray[right] = temp;
            left++;
            right--;
        }
        return new String(charArray);
    }

    public static void main(String[] args) {
        String inputString = "Hello, World!";
        System.out.println("Original String: " + inputString);
        System.out.println("Reversed String (Efficient): " + reverseStringEfficient(inputString));
    }
}

```
</p>
</details>

<details>
<summary>using String Builder</summary>
<p>

```java
public class ReverseString {

    public static String reverseStringBruteForce(String s) {
        StringBuilder reversed = new StringBuilder();
        for (int i = s.length() - 1; i >= 0; i--) {
            reversed.append(s.charAt(i));
        }
        return reversed.toString();
    }

    public static void main(String[] args) {
        String inputString = "Hello, World!";
        System.out.println("Original String: " + inputString);
        System.out.println("Reversed String (Brute Force): " + reverseStringBruteForce(inputString));
    }
}

```

</p>
</details>

---

### 2. Reverse Each Word in a String: <a id="sm2"></a>

- Question: Given a string, reverse each word in the string while maintaining the order of words.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (where n is the length of the string).
```
Input: s = "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```

<details>
<summary>using reverseString (2 pointer) and string nuilder</summary>
<p>

```java
public class ReverseWords {
    public static String reverseString(String s) {
        char[] charArray = s.toCharArray();
        int left = 0;
        int right = charArray.length - 1;
        while (left < right) {
            char temp = charArray[left];
            charArray[left] = charArray[right];
            charArray[right] = temp;
            left++;
            right--;
        }
        return new String(charArray);
    }

    public static String reverseWords(String s) {
        String[] words = s.split(" "); // Split the string into words
        StringBuilder reversedString = new StringBuilder();
        for (String word : words) {
            // Reverse each word and append to the result string
            reversedString.append(reverseString(word)).append(" ");
        }
        return reversedString.toString().trim(); // Trim trailing space and return
    }

    public static void main(String[] args) {
        String s = "Let's take LeetCode contest";
        System.out.println("Original string: " + s);
        System.out.println("Reversed string: " + reverseWords(s)); // Output: "s'teL ekat edoCteeL tsetnoc"
    }
}

```

</p>
</details>

---
### 3. Reverse Words in a String Without Reversing Each Word: <a id="sm3"></a>

- Question: Reverse the order of words in a string without reversing each word individually.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (where n is the length of the string).

```
Input: s = "the sky is blue"
Output: "blue is sky the"
```

<details>
<summary>code</summary>
<p>

```java
public class ReverseWordsInString {
    public static String reverseWords(String s) {
        StringBuilder reversedString = new StringBuilder();
        int end = s.length();

        for (int i = s.length() - 1; i >= 0; i--) {
            if (s.charAt(i) == ' ') {
                // Found a space, append the word
                reversedString.append(s.substring(i + 1, end)).append(" ");
                // Move the end pointer to the beginning of the current word
                end = i;
            }
        }

        // Append the first word
        reversedString.append(s.substring(0, end));

        return reversedString.toString();
    }

    public static void main(String[] args) {
        String s = "the sky is blue";
        System.out.println("Input: " + s);
        System.out.println("Output: " + reverseWords(s));
    }
}

```
</p>
</details>

---
## Array Manipulation <a id="arraysm"></a>

### 1. Find Duplicates in an Array: <a id="am1"></a>

- Question: Given an array of integers where each integer appears twice except for one, find the element that appears only once.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity) for XOR and O(n) using HashSet.

<details>
<summary>using XOR</summary>
<p>

```java
public class SingleNumber {
    public static int findSingleNumber(int[] nums) {
        int result = 0;
        for (int num : nums) {
            result ^= num; // XOR operation cancels out duplicate occurrences, leaving only the single number
        }
        return result;
    }

    public static void main(String[] args) {
        int[] nums = {4, 1, 2, 1, 2};
        System.out.println("The single number is: " + findSingleNumber(nums)); // Output: 4
    }
}

```
</p>
</details>

<details>
<summary>using HashSet</summary>
<p>
  
```java
import java.util.HashSet;

public class SingleNumber {
    public static int findSingleNumber(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        for (int num : nums) {
            if (!set.add(num)) {
                // If the number is already present, remove it
                set.remove(num);
            }
        }
        // After iterating through the array, the set should contain only the single number
        return set.iterator().next();
    }

    public static void main(String[] args) {
        int[] nums = {4, 1, 2, 1, 2};
        System.out.println("The single number is: " + findSingleNumber(nums)); // Output: 4
    }
}

```
</p>
</details>

---
### 2. Anagram Question: <a id="am2"></a>

- Question: Given two strings, determine if they are anagrams of each other (contain the same characters with the same frequencies).
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity) assuming constant character set (e.g., ASCII).

<details>
<summary>using array</summary>
<p>

```java
public class Anagram {
    public static boolean areAnagrams(String s1, String s2) {
        if (s1 == null || s2 == null || s1.length() != s2.length()) {
            return false; // If either string is null or their lengths are different, they cannot be anagrams
        }
        int[] charCount = new int[256]; // Assuming ASCII character set
        for (char c : s1.toCharArray()) {
            charCount[c]++;
        }
        for (char c : s2.toCharArray()) {
            if (charCount[c] == 0) {
                return false; // If character frequency in s2 is higher than in s1, they cannot be anagrams
            }
            charCount[c]--;
        }
        return true; // If all character frequencies match, they are anagrams
    }

    public static void main(String[] args) {
        String s1 = "listen";
        String s2 = "silent";
        
        System.out.println("Are \"" + s1 + "\" and \"" + s2 + "\" anagrams? " + areAnagrams(s1, s2)); // true
    }
}

```

</p>
</details>

<details>
<summary>using hashmap</summary>
<p>

```java
import java.util.HashMap;

public class Anagram {
    public static boolean areAnagrams(String s1, String s2) {
        if (s1 == null || s2 == null || s1.length() != s2.length()) {
            return false; // If either string is null or their lengths are different, they cannot be anagrams
        }
        HashMap<Character, Integer> charCount = new HashMap<>();
        
        // Count characters in s1
        for (char c : s1.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) + 1);
        }
        
        // Compare characters in s2 with the counts in the map
        for (char c : s2.toCharArray()) {
            if (!charCount.containsKey(c)) {
                return false; // If a character in s2 is not present in the map, they cannot be anagrams
            }
            int count = charCount.get(c);
            if (count == 0) {
                return false; // If the count for a character in s2 is already 0, they cannot be anagrams
            }
            charCount.put(c, count - 1);
        }
        
        return true; // If all characters in s2 match with counts in the map, they are anagrams
    }

    public static void main(String[] args) {
        String s1 = "listen";
        String s2 = "silent";
        
        System.out.println("Are \"" + s1 + "\" and \"" + s2 + "\" anagrams? " + areAnagrams(s1, s2)); // true
    }
}

```
</p>
</details>

--- 

## Palindrome Checking <a id="palindrome"></a>

### 1. Check if a String is a Palindrome: <a id="p1"></a>

- Question: Determine if a given string is a palindrome (reads the same forwards and backwards).
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

<details>
<summary>code</summary>
<p>

```java
public class Palindrome {
    public static boolean isPalindrome(String str) {
        if (str == null || str.isEmpty()) {
            return true; // An empty string or null string is considered a palindrome
        }
        int left = 0;
        int right = str.length() - 1;
        while (left < right) {
            if (str.charAt(left) != str.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        return true; // If the loop completes without returning false, the string is a palindrome
    }

    public static void main(String[] args) {
        String str1 = "racecar";
        String str2 = "hello";
        
        System.out.println("Is \"" + str1 + "\" a palindrome? " + isPalindrome(str1)); // true
        System.out.println("Is \"" + str2 + "\" a palindrome? " + isPalindrome(str2)); // false
    }
}

```

</p>
</details>

---
### 2. Check if a String is a Palindrome with Ignored Characters: <a id="p2"></a>

- Question: Determine if a given string is a palindrome after ignoring non-alphanumeric characters and considering case insensitivity.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

<details>
<summary>code</summary>
<p>

```java
public class Palindrome {
    public static boolean isPalindrome(String str) {
        if (str == null || str.isEmpty()) {
            return true; // An empty string or null string is considered a palindrome
        }
        int left = 0;
        int right = str.length() - 1;
        while (left < right) {
            char leftChar = Character.toLowerCase(str.charAt(left));
            char rightChar = Character.toLowerCase(str.charAt(right));
            if (!Character.isLetterOrDigit(leftChar)) {
                left++;
            } else if (!Character.isLetterOrDigit(rightChar)) {
                right--;
            } else if (leftChar != rightChar) {
                return false;
            } else {
                left++;
                right--;
            }
        }
        return true; // If the loop completes without returning false, the string is a palindrome
    }

    public static void main(String[] args) {
        String str1 = "A man, a plan, a canal, Panama";
        String str2 = "race a car";
        
        System.out.println("Is \"" + str1 + "\" a palindrome? " + isPalindrome(str1)); // true
        System.out.println("Is \"" + str2 + "\" a palindrome? " + isPalindrome(str2)); // false
    }
}

```

</p>
</details>

---
 
## Fibonacci Sequence <a id="fibonacci"></a>

### 1. Fibonacci Series using Iteration: <a id="f1"></a>

- Question: Write an iterative function to generate the nth Fibonacci number.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

<details>
<summary>using iterative method</summary>
<p>

```java
public class FibonacciIterative {
    public static int generateFibonacci(int n) {
        if (n <= 1) {
            return n; // Base case: Fibonacci(0) = 0, Fibonacci(1) = 1
        }
        int fib1 = 0;
        int fib2 = 1;
        int fib = 0;
        for (int i = 2; i <= n; i++) {
            fib = fib1 + fib2;
            fib1 = fib2;
            fib2 = fib;
        }
        return fib;
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci(" + n + ") = " + generateFibonacci(n)); // Fibonacci(10) = 55
    }
}

```

</p>
</details>

---
### 2. Fibonacci Series using Recursion: <a id="f2"></a>

- Question: Write a recursive function to generate the nth Fibonacci number.
- Time Complexity: O(2^n) (exponential time complexity).
- Space Complexity: O(n) (space complexity due to recursion stack).

<details>
<summary>using recursion</summary>
<p>

```java
public class FibonacciRecursive {
    public static int generateFibonacci(int n) {
        if (n <= 1) {
            return n; // Base case: Fibonacci(0) = 0, Fibonacci(1) = 1
        }
        return generateFibonacci(n - 1) + generateFibonacci(n - 2); // Recursive call
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci(" + n + ") = " + generateFibonacci(n)); // Fibonacci(10) = 55
    }
}

```

</p>
</details>

---
### 3. Fibonacci Series using Memoization: <a id="f3"></a>

- Question: Write a recursive function with memoization to generate the nth Fibonacci number.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (space complexity due to memoization table).

<details>
<summary>using hashmap</summary>
<p>

```java
import java.util.HashMap;

public class FibonacciWithMemoization {
    private static HashMap<Integer, Integer> memo = new HashMap<>();

    public static int generateFibonacci(int n) {
        if (n <= 1) {
            return n; // Base case: Fibonacci(0) = 0, Fibonacci(1) = 1
        }
        if (memo.containsKey(n)) {
            return memo.get(n); // Return memoized value if already computed
        }
        int fib = generateFibonacci(n - 1) + generateFibonacci(n - 2);
        memo.put(n, fib); // Memoize the computed Fibonacci number
        return fib;
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci(" + n + ") = " + generateFibonacci(n)); // Fibonacci(10) = 55
    }
}

```

</p>

</details>

---
### 4. Fibonacci Series using Dynamic Programming (Bottom-up approach): <a id="f4"></a>

- Question: Write a function to generate the nth Fibonacci number using dynamic programming (bottom-up approach).
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (space complexity due to storing previous results).

<details>
<summary>code</summary>
<p>

```java
public class Fibonacci {
    public static int generateFibonacci(int n) {
        if (n <= 1) {
            return n; // Base case: Fibonacci(0) = 0, Fibonacci(1) = 1
        }
        int[] fib = new int[n + 1];
        fib[0] = 0;
        fib[1] = 1;
        for (int i = 2; i <= n; i++) {
            fib[i] = fib[i - 1] + fib[i - 2]; // Dynamic programming: Fibonacci(i) = Fibonacci(i-1) + Fibonacci(i-2)
        }
        return fib[n];
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci(" + n + ") = " + generateFibonacci(n)); // Fibonacci(10) = 55
    }
}

```

</p>
</details>

---
## Stacks <a id="stacks"></a>

### 1. Implement a Stack using Arrays: <a id="s1"></a>

- Question: Implement a stack data structure using arrays and support operations like push, pop, and peek.
- Time Complexity: O(1) for push, pop, and peek operations.
- Space Complexity: O(n) where n is the maximum capacity of the stack.

<details>
<summary>code</summary>
<p>

```java
public class Stack {
    private int[] array;
    private int top; // Index of the top element
    private int capacity; // Maximum capacity of the stack

    public Stack(int capacity) {
        this.capacity = capacity;
        this.array = new int[capacity];
        this.top = -1; // Stack is initially empty
    }

    // Push operation
    public void push(int data) {
        if (isFull()) {
            System.out.println("Stack is full. Cannot push.");
            return;
        }
        array[++top] = data;
    }

    // Pop operation
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot pop.");
            return -1;
        }
        return array[top--];
    }

    // Peek operation
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot peek.");
            return -1;
        }
        return array[top];
    }

    // Check if the stack is empty
    public boolean isEmpty() {
        return top == -1;
    }

    // Check if the stack is full
    public boolean isFull() {
        return top == capacity - 1;
    }

    public static void main(String[] args) {
        Stack stack = new Stack(5);

        stack.push(1);
        stack.push(2);
        stack.push(3);

        System.out.println("Top element: " + stack.peek()); // 3
        System.out.println("Popped element: " + stack.pop()); // 3
        System.out.println("Top element after pop: " + stack.peek()); // 2
    }
}


```
</p>
</details>

---
### 2. Implement a Stack using Linked Lists: <a id="s2"></a>

- Question: Implement a stack data structure using a linked list and support operations like push, pop, and peek.
- Time Complexity: O(1) for push, pop, and peek operations.
- Space Complexity: O(n) where n is the number of elements in the stack.

<details>
<summary>code</summary>
<p>

```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class Stack {
    private Node top; // Top of the stack

    // Push operation
    public void push(int data) {
        Node newNode = new Node(data);
        newNode.next = top;
        top = newNode;
    }

    // Pop operation
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot pop.");
            return -1;
        }
        int data = top.data;
        top = top.next;
        return data;
    }

    // Peek operation
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot peek.");
            return -1;
        }
        return top.data;
    }

    // Check if the stack is empty
    public boolean isEmpty() {
        return top == null;
    }

    public static void main(String[] args) {
        Stack stack = new Stack();

        stack.push(1);
        stack.push(2);
        stack.push(3);

        System.out.println("Top element: " + stack.peek()); // 3
        System.out.println("Popped element: " + stack.pop()); // 3
        System.out.println("Top element after pop: " + stack.peek()); // 2
    }
}

```
</p>
</details>

---
### 3. Check Balanced Parentheses: <a id="s3"></a>

- Question: Given a string containing only parentheses, brackets, and braces, determine if the brackets are balanced.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (space complexity due to the stack).

<details>
<summary>code</summary>
<p>

```java
import java.util.Stack;

public class BalancedBrackets {
    public static boolean isBalanced(String str) {
        Stack<Character> stack = new Stack<>();
        for (char c : str.toCharArray()) {
            if (c == '(' || c == '[' || c == '{') {
                stack.push(c);
            } else if (c == ')' || c == ']' || c == '}') {
                if (stack.isEmpty()) {
                    return false; // Closing bracket with no corresponding opening bracket
                }
                char top = stack.pop();
                if ((c == ')' && top != '(') || (c == ']' && top != '[') || (c == '}' && top != '{')) {
                    return false; // Mismatched brackets
                }
            }
        }
        return stack.isEmpty(); // Stack should be empty for balanced brackets
    }

    public static void main(String[] args) {
        String str1 = "{[()]}";
        String str2 = "{[()]";
        String str3 = "{[(])}";
        String str4 = "{[}";
        
        System.out.println("String 1 is balanced: " + isBalanced(str1));
        System.out.println("String 2 is balanced: " + isBalanced(str2));
        System.out.println("String 3 is balanced: " + isBalanced(str3));
        System.out.println("String 4 is balanced: " + isBalanced(str4));
    }
}

```
</p>
</details>

---
### 4. Implement a Stack using Two Queues: <a id="s4"></a>

- Question: Implement a stack data structure using two queues and support operations like push, pop, and peek.
- Time Complexity: O(1) for push operation, O(n) for pop operation (where n is the number of elements in the stack).
- Space Complexity: O(n) where n is the number of elements in the stack.

<details>
<summary>code</summary>
<p>

```java
import java.util.LinkedList;
import java.util.Queue;

public class StackWithQueues {
    private Queue<Integer> queue1;
    private Queue<Integer> queue2;

    public StackWithQueues() {
        queue1 = new LinkedList<>();
        queue2 = new LinkedList<>();
    }

    // Push operation
    public void push(int item) {
        queue1.offer(item);
    }

    // Pop operation
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot pop.");
            return -1;
        }
        // Move all elements except the last one to queue2
        while (queue1.size() > 1) {
            queue2.offer(queue1.poll());
        }
        int poppedItem = queue1.poll(); // Last element remaining in queue1 is the one to be popped
        // Swap queue1 and queue2 references
        Queue<Integer> temp = queue1;
        queue1 = queue2;
        queue2 = temp;
        return poppedItem;
    }

    // Peek operation
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot peek.");
            return -1;
        }
        int peekedItem = -1;
        while (!queue1.isEmpty()) {
            peekedItem = queue1.poll();
            queue2.offer(peekedItem);
        }
        // Swap queue1 and queue2 references
        Queue<Integer> temp = queue1;
        queue1 = queue2;
        queue2 = temp;
        return peekedItem;
    }

    // Check if the stack is empty
    public boolean isEmpty() {
        return queue1.isEmpty();
    }
}

```
</p>
</details>

--- 

## Queues <a id="queues"></a>

### 1. Implement a Queue using Arrays <a id="q1"></a>

- Question :  Implement a queue data structure using arrays and support operations like enqueue and dequeue.
- Time Complexity :
  - Bounded Queue (fixed size array) : O(1) for enqueue and O(n) for dequeue (as elements need to be shifted)
  - Unbounded Queue (dynamix resizing array) :  O(1) amortized for enqueue and O(1) dequeue operations.
- Space Complexity: O(n) where n is the maximum capacity of the queue.

<details>
<summary>Bounded Queue</summary>
<p>

```java
public class BoundedQueue {
    private int[] queue;
    private int front; // index of the front element
    private int rear; // index of the rear element
    private int capacity; // maximum capacity of the queue
    private int size; // current size of the queue

    public BoundedQueue(int capacity) {
        this.capacity = capacity;
        this.queue = new int[capacity];
        this.front = 0;
        this.rear = -1; // no elements initially
        this.size = 0;
    }

    // Enqueue operation
    public void enqueue(int item) {
        if (isFull()) {
            System.out.println("Queue is full. Cannot enqueue.");
            return;
        }
        rear = (rear + 1) % capacity; // Circular increment
        queue[rear] = item;
        size++;
    }

    // Dequeue operation
    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot dequeue.");
            return -1;
        }
        int item = queue[front];
        front = (front + 1) % capacity; // Circular increment
        size--;
        return item;
    }

    // Check if the queue is full
    public boolean isFull() {
        return size == capacity;
    }

    // Check if the queue is empty
    public boolean isEmpty() {
        return size == 0;
    }

    // Get the front item without removing it
    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot peek.");
            return -1;
        }
        return queue[front];
    }
}

```
</p>
</details>

<details>
<summary>Unbounded Queue</summary>
<p>

```java
public class UnboundedQueue {
    private int[] queue;
    private int front; // index of the front element
    private int rear; // index of the rear element
    private int capacity; // current capacity of the queue
    private int size; // current size of the queue

    public UnboundedQueue(int initialCapacity) {
        this.capacity = initialCapacity;
        this.queue = new int[initialCapacity];
        this.front = 0;
        this.rear = -1; // no elements initially
        this.size = 0;
    }

    // Enqueue operation
    public void enqueue(int item) {
        if (isFull()) {
            resize();
        }
        rear++;
        if (rear == capacity) {
            rear = 0; // Circular increment
        }
        queue[rear] = item;
        size++;
    }

    // Dequeue operation
    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot dequeue.");
            return -1;
        }
        int item = queue[front];
        front++;
        if (front == capacity) {
            front = 0; // Circular increment
        }
        size--;
        return item;
    }

    // Check if the queue is full
    private boolean isFull() {
        return size == capacity;
    }

    // Check if the queue is empty
    public boolean isEmpty() {
        return size == 0;
    }

    // Get the front item without removing it
    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot peek.");
            return -1;
        }
        return queue[front];
    }

    // Resize the array when full
    private void resize() {
        int newCapacity = capacity * 2; // Double the capacity
        int[] newQueue = new int[newCapacity];
        int i = 0;
        while (!isEmpty()) {
            newQueue[i++] = dequeue(); // Re-queue all elements to the new array
        }
        queue = newQueue;
        front = 0;
        rear = size - 1;
        capacity = newCapacity;
    }
}

```
</p>
</details>

---

### 2. Implement a Queue using Linked Lists <a id="q2"></a>

- Question: Implement a queue data structure using a linked list and support operations like enqueue and dequeue.
- Time Complexity: O(1) for enqueue and dequeue operations.
- Space Complexity: O(n) where n is the number of elements in the queue.

<details>
<summary>code</summary>
<p>

```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class Queue {
    private Node front;
    private Node rear;

    public Queue() {
        this.front = null;
        this.rear = null;
    }

    // Enqueue operation
    public void enqueue(int data) {
        Node newNode = new Node(data);
        if (isEmpty()) {
            front = rear = newNode;
        } else {
            rear.next = newNode;
            rear = newNode;
        }
    }

    // Dequeue operation
    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot dequeue.");
            return -1;
        }
        int data = front.data;
        if (front == rear) {
            front = rear = null;
        } else {
            front = front.next;
        }
        return data;
    }

    // Check if the queue is empty
    public boolean isEmpty() {
        return front == null;
    }

    // Get the front item without removing it
    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot peek.");
            return -1;
        }
        return front.data;
    }
}

```
</p>
</details>

---

### 3. Implement a Circular Queue <a id="q3"></a>

- Question: Implement a circular queue data structure using arrays and support operations like enqueue and dequeue.
- Time Complexity: O(1) for enqueue and dequeue operations.
- Space Complexity: O(n) where n is the maximum capacity of the circular queue.

<details>
<summary>code</summary>
<p>

```java
public class CircularQueue {
    private int[] queue;
    private int front; // index of the front element
    private int rear; // index of the rear element
    private int size; // current size of the queue
    private int capacity; // maximum capacity of the queue

    public CircularQueue(int capacity) {
        this.capacity = capacity;
        this.queue = new int[capacity];
        this.front = 0;
        this.rear = -1; // no elements initially
        this.size = 0;
    }

    // Enqueue operation
    public void enqueue(int item) {
        if (isFull()) {
            System.out.println("Queue is full. Cannot enqueue.");
            return;
        }
        rear = (rear + 1) % capacity; // Circular increment
        queue[rear] = item;
        size++;
    }

    // Dequeue operation
    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot dequeue.");
            return -1;
        }
        int item = queue[front];
        front = (front + 1) % capacity; // Circular increment
        size--;
        return item;
    }

    // Check if the queue is full
    public boolean isFull() {
        return size == capacity;
    }

    // Check if the queue is empty
    public boolean isEmpty() {
        return size == 0;
    }

    // Get the front item without removing it
    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot peek.");
            return -1;
        }
        return queue[front];
    }
}

```

</p>
</details>

---

## Graphs <a id="graphs"></a>

### 1. Implement Depth First Search (DFS) <a id="g1"></a>

- Question: Implement the depth-first search (DFS) algorithm for a graph.
- Time Complexity: O(V + E) where V is the number of vertices and E is the number of edges.
- Space Complexity: O(V) for the recursion stack.

<details>
<summary>Dfs code</summary>
<p>

```java
import java.util.*;

public class DFS {
    private static class Graph {
        private int vertices;
        private LinkedList<Integer>[] adjList;

        Graph(int vertices) {
            this.vertices = vertices;
            adjList = new LinkedList[vertices];
            for (int i = 0; i < vertices; i++) {
                adjList[i] = new LinkedList<>();
            }
        }

        void addEdge(int src, int dest) {
            adjList[src].add(dest);
        }

        void DFS(int vertex) {
            boolean[] visited = new boolean[vertices];
            DFSUtil(vertex, visited);
        }

        void DFSUtil(int vertex, boolean[] visited) {
            visited[vertex] = true;
            System.out.print(vertex + " ");
            for (int adj : adjList[vertex]) {
                if (!visited[adj]) {
                    DFSUtil(adj, visited);
                }
            }
        }
    }

    public static void main(String[] args) {
        Graph graph = new Graph(4);
        graph.addEdge(0, 1);
        graph.addEdge(0, 2);
        graph.addEdge(1, 2);
        graph.addEdge(2, 0);
        graph.addEdge(2, 3);
        graph.addEdge(3, 3);

        graph.DFS(2); // Output: 2 0 1 3
    }
}

```
</p>
</details>


---

### 2. Implement Breadth First Search (BFS) <a id="g2"></a>

- Question: Implement the breadth-first search (BFS) algorithm for a graph.
- Time Complexity: O(V + E) where V is the number of vertices and E is the number of edges.
- Space Complexity: O(V) for the queue.

<details>
<summary>Bfs code</summary>
<p>

```java
import java.util.*;

public class BFS {
    private static class Graph {
        private int vertices;
        private LinkedList<Integer>[] adjList;

        Graph(int vertices) {
            this.vertices = vertices;
            adjList = new LinkedList[vertices];
            for (int i = 0; i < vertices; i++) {
                adjList[i] = new LinkedList<>();
            }
        }

        void addEdge(int src, int dest) {
            adjList[src].add(dest);
        }

        void BFS(int startVertex) {
            boolean[] visited = new boolean[vertices];
            LinkedList<Integer> queue = new LinkedList<>();

            visited[startVertex] = true;
            queue.add(startVertex);

            while (queue.size() != 0) {
                startVertex = queue.poll();
                System.out.print(startVertex + " ");

                for (int adj : adjList[startVertex]) {
                    if (!visited[adj]) {
                        visited[adj] = true;
                        queue.add(adj);
                    }
                }
            }
        }
    }

    public static void main(String[] args) {
        Graph graph = new Graph(4);
        graph.addEdge(0, 1);
        graph.addEdge(0, 2);
        graph.addEdge(1, 2);
        graph.addEdge(2, 0);
        graph.addEdge(2, 3);
        graph.addEdge(3, 3);

        graph.BFS(2); // Output: 2 0 3 1
    }
}

```
</p>
</details>

---
