# Coding Questions based on Data Structures

- [Arrays](#arrays)
  - [1. Sort an Array](#a1)
  - [2. Sort an Array of 0s](#a2)
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

### Sort an array: <a id="a1"></a>

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



### Sort an array of 0s and 1s: <a id="a2"></a>

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

### Sort an array of 0s, 1s, and 2s (Dutch National Flag Problem): <a id="a3"></a>

- Question: Given an array containing only 0s, 1s, and 2s, sort the array in linear time without using any sorting algorithm.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).


---
## Linked Lists <a id="linkedlists"></a>

### Reverse a linked list: <a id="l1"></a>

- Question: Implement a function to reverse a singly linked list.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

### Detect a cycle in a linked list: <a id="l2"></a>

- Question: Write a function to detect if a linked list contains a cycle.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

### Merge two sorted linked lists: <a id="l3"></a>

- Question: Given two sorted linked lists, merge them into a single sorted linked list.
- Time Complexity: O(n + m) where n and m are the lengths of the two linked lists.
- Space Complexity: O(1) (constant space complexity).

---
## Trees <a id="trees"></a>

### Binary Search Tree (BST) validation: <a id="t1"></a>

- Question: Write a function to determine if a binary tree is a valid binary search tree.
- Time Complexity: O(n) (linear time complexity where n is the number of nodes in the tree).
- Space Complexity: O(h) where h is the height of the tree (space complexity due to recursion).

### Inorder Traversal of a Binary Tree: <a id="t2"></a>

- Question: Implement an inorder traversal of a binary tree (recursive or iterative).
- Time Complexity: O(n) (linear time complexity where n is the number of nodes in the tree).
- Space Complexity: O(h) where h is the height of the tree (space complexity due to recursion or stack space in the iterative approach).

### Lowest Common Ancestor in a Binary Tree: <a id="t3"></a>

- Question: Given a binary tree, find the lowest common ancestor of two given nodes in the tree.
- Time Complexity: O(n) (linear time complexity where n is the number of nodes in the tree).
- Space Complexity: O(h) where h is the height of the tree (space complexity due to recursion).

---
## String Manipulation <a id="stringm"></a>

### Reverse a String: <a id="sm1"></a>

- Question: Implement a function to reverse a given string.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

### Reverse Each Word in a String: <a id="sm2"></a>

- Question: Given a string, reverse each word in the string while maintaining the order of words.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (where n is the length of the string).

### Reverse Words in a String Without Reversing Each Word: <a id="sm3"></a>

- Question: Reverse the order of words in a string without reversing each word individually.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (where n is the length of the string).

---
## Array Manipulation <a id="arraysm"></a>

### Find Duplicates in an Array: <a id="am1"></a>

- Question: Given an array of integers where each integer appears twice except for one, find the element that appears only once.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

### Anagram Question: <a id="am2"></a>

- Question: Given two strings, determine if they are anagrams of each other (contain the same characters with the same frequencies).
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity) assuming constant character set (e.g., ASCII).

--- 

## Palindrom Checking <a id="palindrome"></a>

### Check if a String is a Palindrome: <a id="p1"></a>

- Question: Determine if a given string is a palindrome (reads the same forwards and backwards).
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

### Check if a String is a Palindrome with Ignored Characters: <a id="p2"></a>

- Question: Determine if a given string is a palindrome after ignoring non-alphanumeric characters and considering case insensitivity.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

--- 
## Fibonacci Sequence <a id="fibonacci"></a>

### Fibonacci Series using Iteration: <a id="f1"></a>

- Question: Write an iterative function to generate the nth Fibonacci number.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(1) (constant space complexity).

### Fibonacci Series using Recursion: <a id="f2"></a>

- Question: Write a recursive function to generate the nth Fibonacci number.
- Time Complexity: O(2^n) (exponential time complexity).
- Space Complexity: O(n) (space complexity due to recursion stack).

### Fibonacci Series using Memoization: <a id="f3"></a>

- Question: Write a recursive function with memoization to generate the nth Fibonacci number.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (space complexity due to memoization table).

### Fibonacci Series using Dynamic Programming (Bottom-up approach): <a id="f4"></a>

- Question: Write a function to generate the nth Fibonacci number using dynamic programming (bottom-up approach).
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (space complexity due to storing previous results).

---
## Stacks <a id="stacks"></a>

### Implement a Stack using Arrays: <a id="s1"></a>

- Question: Implement a stack data structure using arrays and support operations like push, pop, and peek.
- Time Complexity: O(1) for push, pop, and peek operations.
- Space Complexity: O(n) where n is the maximum capacity of the stack.

### Implement a Stack using Linked Lists: <a id="s2"></a>

- Question: Implement a stack data structure using a linked list and support operations like push, pop, and peek.
- Time Complexity: O(1) for push, pop, and peek operations.
- Space Complexity: O(n) where n is the number of elements in the stack.

### Check Balanced Parentheses: <a id="s3"></a>

- Question: Given a string containing only parentheses, brackets, and braces, determine if the brackets are balanced.
- Time Complexity: O(n) (linear time complexity).
- Space Complexity: O(n) (space complexity due to the stack).

### Implement a Stack using Two Queues: <a id="s4"></a>

- Question: Implement a stack data structure using two queues and support operations like push, pop, and peek.
- Time Complexity: O(1) for push operation, O(n) for pop operation (where n is the number of elements in the stack).
- Space Complexity: O(n) where n is the number of elements in the stack.

--- 

## Queues <a id="queues"></a>

### Implement a Queue using Arrays <a id="q1"></a>

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

### Implement a Queue using Linked Lists <a id="q2"></a>

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

### Implement a Circular Queue <a id="q3"></a>

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

### Implement Depth First Search (DFS) <a id="g1"></a>

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

### Implement Breadth First Search (BFS) <a id="g2"></a>

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
