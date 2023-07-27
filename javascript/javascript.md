Add questions from HKirat sing
Add copy of JS inteview questions - document

#### 1. What is the output of the following code? Give reason for the same

```javascript
const work = "hello";
word[1] = "m";
console.log(word);
```

<details>
<summary>Answer</summary>
<p>

Output :  
`hello`

Reason :  
Strings are immutable.

</p>
</details>

---

#### 2. Is the code given below valid? If yes, what property of JS does it use?

```javascript
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x; // Display x in the element

var x; // Declare x
```

<details>
<summary>Answer</summary>
<p>
The given code is valid.     <br/>  
<strong>Hoisting</strong> is the property of JS used.
</p>
</details>

---

#### 3. Question

```javascript
console.log(a);

const a = 1;
```

<details>
<summary>Answer</summary>
<p>
Output:    
```javascript
Uncaught ReferenceError: a is not defined
```

Reason:
Hoisting is not done for these

</p>
</details>

---

#### 3. Question

Explain Currying and Hoisting in Javascript.

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 4. Question

Different between Typescript and Javascript

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 5. Question

```html
<body>
    <script src="index.js">
    <div>
    </div>
</body>

```

What will happen to DOM tree if some issue happens in script tag?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 6. Question

Explain promise chaining in javascript?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 7. Question

How does javascript figures out that a promise is resolved?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

[DOM related JS questions](https://www.thatjsdude.com/interview/dom.html)

---
**Hkirat Questions**

1. What is the difference between let, const and var ?
2. Is the code given below valid? If yes, what property of JS does it use?
   ```js
   x = 5; // Assign 5 to x
   elem = document.getElementById("demo"); // Find an element
   elem.innerHTML = x;                     // Display x in the element

   var x; // Declare x
   ```
<details>
<summary>Answer</summary>
<p>
It is valid and it uses hoisting.
This snippet won't work for let. (Temporal Dead Zone)
</p>
</details>
   
3. Is this function correct or incorrect
    ```js
    const arr = [1,2,3]
    arr.forEach(function(val) {
        if(val%2 === 0) {
            break;
        }
    console.log(val);
    })
    ```
<details>
<summary>Answer</summary>
<p>
This function is incorrect because `break` is valid inside a loop. 
But in the above code snippet, it is used inside a function and `break` is not valide inside a function.

Correct way to write it will be : 
```js
const arr = [1,2,3]
for (let i = 0; i < arr.length; i++) {
    if(arr[i] % 2 === 0) {
        break;
    }
console.log(val);
}
```
OR
```js
const arr = [1,2,3];
let done = false;
arr.forEach(function(val) {
    if(val%2 === 0) {
        done = true;
    }
    if(!done) {
    console.log(val);
    }
})
```

</p>
</details>

    
5. 

---

- What is EcmaScript in JavaScript?
- What is difference between let, const and var?
- What is spread operator, rest operator, default parameter?
- What is deep copy and shallow copy in JavaScript?
- What is promise, callback function, async await in JavaScript?
- What is difference between promise and callback in JavaScript?
- What is event bubbling and event capturing in JavaScript?
- What is Higher Order Function in JavaScript?
- Explain different two types of function in JavaScript
- What is arrow function in JavaScript?
- Why we use call, apply, bind method in JavaScript?
- How many ways to create object in JavaScript?
- What is prototype inheritance in JavaScript?
- What is typescript?
- What are the array method, string method?
- What is difference between java and javascript?
- What is throttling and debouncing in js?
- What is Null and undefined in js?
- What are the falsy values in js?
- What is executing context, event loop, stack, call queue, microtask queue in js?
- What is setTimeOut and setInterval in js?
- What is object.seal and object.freeze in js?
- What is difference between map and set in js?
- What is WeakMap and Weakset in JavaScript?
- What is sessionStorage, localStorage, cookie?
- Write a program to sort an array
- What is the use of json.stringify and json.parse() method in js?
- What are map, filter and reduce in js?
- What is generator function in js?
- How to stop event propagation in js?
- What is closure in js?
- What is hoisting in js?
- What is dead zone in js?
- What is function currying in js?
- What is mutation observer in js?
- What is memoization in js?
- What is Debounce and Throttle in js?
