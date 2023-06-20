# Coding Questions

### 1. [Given a sorted array of N elements and an element K. Fine the frequency of element K in the array](https://practice.geeksforgeeks.org/problems/number-of-occurrence2259/1)

- Discussion on edge cases like
  - if the element K is not present in the array
  - if the array is null or empty

### 2. [Given a binary tree, find the maximum path sum. The path may start and end at any node in the tree.](https://practice.geeksforgeeks.org/problems/maximum-path-sum-from-any-node/1)

- Discussion on edge cases like
  - if binary tree is empty or null
  - if all nodes in tree contains negative values only

### 3. [Given an array of N elements and an integer X, find 3 elements in the array whose sum is closest to given element X ](https://practice.geeksforgeeks.org/problems/three-sum-closest/1/#:~:text=Given%20an%20array%20Arr%20of,sum%202%20in%20the%20array.)

- Discussion on edge cases like
  - if input array is empty or null
  - if input array contains less than 3 numbers or no such triplest exists in the array
  - if there are multiple triplets in the array. (print any one triplet)

### 4. String manipulation question [LC - Easy/Medium]. Was asked a follow up question which was to basically add this function to the Function prototype chain.

### 5. Flatten Array for example Input: [[1,2],[[3,4]],[5]] Output: [1,2,3,4,5]

### 6. Don't quite remember the exact question but it was related to DOM tree traversal.

### 7. Given a string, reverse only the alphabets keeping rest of the character at the same place

### 8. Find all pairs in an array where sum is equal to a certain number(You can create a JS Object and then directly look for sum-num in Object)

### 9. DP based question(You have to use memoization to solve this)

### 10. [Rotten Tomato](https://www.geeksforgeeks.org/minimum-time-required-so-that-all-oranges-become-rotten/)

### 11. [Missing Number](https://www.geeksforgeeks.org/find-the-missing-number/)

### 12. [Merge K sorted arrays](https://www.geeksforgeeks.org/merge-k-sorted-arrays/)

### 13. [Binary Search](https://www.geeksforgeeks.org/binary-search/)

### 14. [Valid Mountain Array](https://leetcode.com/problems/valid-mountain-array/)

# Flipkart 2021 - UI Engineer I

- Summary
  - Round 1 : Machine Coding
  - Round 2 : Coding Round
  - Round 3 : UI Technical
  - Round 4 : Hiring Manager Round

---

## Round 1 : Machine Coding

# Machine Coding Questions

## 4. Question - Bowling Alley

### Write machine code for a single-lane bowling alley system.

One bowling game will be played by multiple players on a single lane.  
During the game, players and their scores will be maintained and shown by the system and the winner will be declared at the end of the game.

Some rules about bowling:

- The Game of bowling consists of 5 Rounds.
- Each round consists of alternate plays (one by each player), and each player will have two chances to drop all the “pins”
- The score for a round is the total number of pins knocked down, plus bonuses for **strikes** and **spares**.
- A **strike** is when the player knocks down all ten pins on the first try. If there is a strike the player gets 10 bonus points.
- A **spare** is when the player knocks down all ten pins in two tries. If there is spare the player gets 5 bonus points.
- In the final round, a player who rolls a **spare** or a **strike** is allowed to roll extra 2 balls(not rounds) to complete the round. This allows for a potential of 7 strikes (5+2) in a single game.
- **Strike** is denoted by **‘x’** and **spare** is denoted by ‘/’. All other pin drop count can be denoted by 0 - 9 (for ex: 5, if five pins were dropped in a round)
- After the final round, display the Player list in ranked order on the basis of score.

### Bonus Point: (Only Attempt If Time Permits)

**Changing Bonus Rule:** Bonus points are awarded, depending on what is scored in the next 2 balls (for a strike) or next 1 ball (for a spare).

_Input:_

- No. of players
- Score Input can be taken from fileInput or console.

_Output:_

- Current position of the running games (Scoreboard) and after the final round, display players in ranked order on the basis of score.

_Example:_

- Below example is for 3 Rounds

```
Input:
Number of players: 2

Round 1:
Enter Score for Player1 - Chance1: 8
Enter Score for Player1 - Chance2: 2
*********************************************************
Player1 Score Chance1 - 8pins Chance2 - 2pin                   ********************************************************* Scoreboard:
P1: {8,/} -> 15 (10+5)
P2: {} -> 0

Enter Score for Player2 - Chance1: 10
*********************************************************
 Player2 Score Chance1 - 10pins
********************************************************* Scoreboard:
P1: {8,/} -> 15
P2: {X,} -> 20 (10+10)
*********************************************************


Round 2:
Enter Score for Player1 - Chance1: 2
Enter Score for Player1 - Chance2: 7
*********************************************************
Player1 Score Chance1 - 2pins Chance2 - 7pin     ********************************************************* Scoreboard:
P1: {8,/}, {2,7} -> 24 (15+9)
P2: {X,}, {} -> 20
Enter Score for Player2 - Chance1: 6
Enter Score for Player2 - Chance2: 4
*********************************************************
Player2 Score Chance1 - 6pins Chance2 - 4pin        ********************************************************* Scoreboard:
P1: {8,/}, {2,7} -> 24
P2: {X,}, {6,/} -> 35 (20+10+5)
*********************************************************

Round 3:
Enter Score for Player1 - Chance1: 10
Enter Score for Player1 - Chance2: 8
Enter Score for Player1 - Chance3: 2
*********************************************************
Player1 Score Chance1 - 10pins
Player1 Score Chance2 - 8pins Chance3 - 2pin (Extra chance as all pins were dropped in last round)              *********************************************************
Scoreboard:
P1: {8,/}, {2,7}, {X,}, {8,/} -> 59 (24+(10+10)+(10+5)) P2: {X, }, {6, /}, {} -> 35
Enter Score for Player2 - Chance1: 3
Enter Score for Player2 - Chance2: 4
*********************************************************
Player2 Score Chance1 - 3pins Chance2 - 4pin                *********************************************************

Scoreboard:
P1: {8,/}, {2,7}, {X, }, {8,/} -> 59 P2: {X, }, {6, /}, {3,4} -> 42 (35+3+4)  *********************************************************

```

**Final Output:**
P1 - 59 points (winner)  
P2 - 42 points

_Example for bonus question:_

```
Strike:
    Round 1, ball 1: 10 pins (strike)
    Round 2, ball 1: 3 pins
    Round 2, ball 2: 6 pins
    The total score from these throws is:
    Round one: 10 + (3 + 6) = 19
    Round two: 3 + 6 = 9
    TOTAL = 28

Spare:
    Round 1, ball 1: 7 pins
    Round 1, ball 2: 3 pins (spare)
    Round 2, ball 1: 4 pins
    Round 2, ball 2: 2 pins

The total score from these throws is:
    Round one: 7 + 3 + 4 (bonus) = 14
    Round two: 4 + 2 = 6
    TOTAL = 20

```

Evaluation criteria

- Demo-able code
- Separation of concerns
- Functional correctness
- Code readability
- Abstractions
- Entity Modeling
- Handling edge cases
- Usage of design patterns, where applicable
- Testability
- Language proficiency
- Design should be extensible.
- The code should be parameterized rather than hardcoded.

Candidate Guidelines

- Please discuss the solution with an interviewer.
- Please do not access the internet for anything EXCEPT syntax
- You are free to use the language of your choice
- All work should be your own
- Please focus on the Bonus Feature only after ensuring the required features are complete and demoable.

---

## 2. Question - Two Forms as Filters

### Create a frontend system having below features [Flipkart 2021 - UI Developer]

## Left side of UI

- A small form containing radio buttons, two text boxes and submit button.
- The radio buttons needs to be implemented in form of small circles having specific size.
- The two text boxes are labelled as **Title** and **Subtitle**
- The background of radio buttons needs to be colored. The color needs to be randomly generated by calling an API that was given to me.
- The purpose of the form is to act as a filter. It could take input in different form of combinations such as by selecting color, color + inputting title, color + subtitle, color + title + subtitle.
- Based on the input given, the final output will be filtered accordingly.
- The final output is nothing but a list of rectangular boxes having specific color as background and containing title or subtitle based on filter selected.
- Say, if you choose blue color, then all those rectangles having blue color will be displayed.
- Say, if you choose green color and input title as "Title1" then all the rectangles having color green and title "Title1" will be displayed.
- Say, if you choose any filter which doesn't match with any rectangles then no rectangles will be displayed.

## Right side of UI

- The left and right side of UI is to be separated by a thick black line.
- The features for the right side are as below:
- Another form needs to be implemented containing 2 text boxes, several radio buttons whose background colors is to be fetched by calling the API given to me and a submit button.
- Again the 2 text boxes are labelled as **Title** and **Subtitle**
- Based on the type of input given, a corresponding rectangle will get generated to the left hand side of the UI.
- Say, if you choose red color and give title as **"Hello"** then a rectangle with red background color gets generated with the title **"Hello"**

---

## 3. Question - Whatsapp web

Time : 90 minutes (coding) + 30 minutes (discussion)

### Implement frontend of a chat application, similar to web.whatsapp.com

- Allowed Tech stack : Vanilla JS and plain CSS
- Api endpoint url returns mock data required. It has array of objects with contact details and message list.
- Using Object Oriented JavaScript can be used to create reusable components

```
[
  {
    "id": 1,
    "title": "title",
    "imageURL": "someUrl",
    "orderId": "OD123",
    "messageList": [
      {
        "messageId": "msg1",
        "message": "Hi",
        "messageType": "text"
      },
      {
        "messageId": "msg2",
        "message": "need assistance",
        "messageType": "text"
      }
    ]
  },
  {
    "id": 2,
    "title": "title2",
    "imageURL": "someUrl2",
    "orderId": "OD1234",
    "messageList": []
  },
]
```

- Required Features

  - left view / panel
    - contains scrollable list of contacts with image, title, date, etc
    - has a search box which can be used to search contact by id and title
  - right view / panel
    - on click of any contact open a chat window which shows previous messages as well as input to send messages that need to be persisted (used localStorage)
  - style according to design provided (similar to whatsapp web)

- Bonus Features
  - attach images, files and videos to the chat
  - clicking on link opens it in new tab (youtube or other links)

---

## 4. Question - Flipkart Home Page

Tech stack : Vanilla JS

- Create a web page where whole layout is dynamically rendered
- All containers of Flipkart home page i.e., the header, search bar, banner, producto catalogue, carousel, footer etc.
- API provides a nested object with container and widgets inside it
- Each widget has its own width and color
- Search bar should be able to filter the widgets as per their ids i.e., that widget should appear on screen
- Focus is on writing modular code using JS

Bonus feature:

- Make it responsive

---

## Round 2 : Coding Round

[interview questions](https://www.ambitionbox.com/interviews/flipkart-interview-questions/front-end-developer)

### 1. [Given a sorted array of N elements and an element K. Fine the frequency of element K in the array](https://practice.geeksforgeeks.org/problems/number-of-occurrence2259/1)

- Discussion on edge cases like
  - if the element K is not present in the array
  - if the array is null or empty

### 2. [Given a binary tree, find the maximum path sum. The path may start and end at any node in the tree.](https://practice.geeksforgeeks.org/problems/maximum-path-sum-from-any-node/1)

- Discussion on edge cases like
  - if binary tree is empty or null
  - if all nodes in tree contains negative values only

### 3. [Given an array of N elements and an integer X, find 3 elements in the array whose sum is closest to given element X ](https://practice.geeksforgeeks.org/problems/three-sum-closest/1/#:~:text=Given%20an%20array%20Arr%20of,sum%202%20in%20the%20array.)

- Discussion on edge cases like
  - if input array is empty or null
  - if input array contains less than 3 numbers or no such triplest exists in the array
  - if there are multiple triplets in the array. (print any one triplet)

### 4. String manipulation question [LC - Easy/Medium]. Was asked a follow up question which was to basically add this function to the Function prototype chain.

### 5. Flatten Array for example Input: [[1,2],[[3,4]],[5]] Output: [1,2,3,4,5]

### 6. Don't quite remember the exact question but it was related to DOM tree traversal.

### 7. Given a string, reverse only the alphabets keeping rest of the character at the same place

### 8. Find all pairs in an array where sum is equal to a certain number(You can create a JS Object and then directly look for sum-num in Object)

### 9. DP based question(You have to use memoization to solve this)

### 10. [Rotten Tomato](https://www.geeksforgeeks.org/minimum-time-required-so-that-all-oranges-become-rotten/)

### 11. [Missing Number](https://www.geeksforgeeks.org/find-the-missing-number/)

### 12. [Merge K sorted arrays](https://www.geeksforgeeks.org/merge-k-sorted-arrays/)

### 13. [Binary Search](https://www.geeksforgeeks.org/binary-search/)

### 14. [Valid Mountain Array](https://leetcode.com/problems/valid-mountain-array/)

---

## Round 3 : UI Technical Round

### JavaScript

#### 1. Question

```javascript
const work = "hello";
word[1] = "m";
console.log(word);
```

<details>
<summary>Answer</summary>
<p>

`hello`
Strings are immutable.

</p>
</details>

---

#### 2. Question

```javascript
console.log(a);

const a = 1;
```

<details>
<summary>Answer</summary>
<p>

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

Explain promise chaining in javascript?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 6. Question

How does javascript figures out that a promise is resolved?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 7. Question

JavaScript Fundamentals and tricky output based questions which indirectly covered topics like closures, hoisting, var scope vs let,const scope, IIFE, callback vs promises vs async await, how to handle dependent promise logic / promise chaining.

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 8. Question

Implement Function.prototype.bind polyfill

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 9. Question

Event loop, and how setTimeout and Promises are queued

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 10. Question

Prototypal Inheritance in Javscript and how does prototype chain works?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 11. Question

What is a reduce function in Javascript. How to write a polyfill of a reduce function? He wanted me to cover all cases while writing a pollyfill of reduce. (check MDN documentation )

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 12. Question

How does Redux Saga works, what problem it solves and how can we achieve our goals without redux saga?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 13. Question

How will you design a calendar? What controls will you make? What events will you attach? How will you render a numbers in calendar for every month?

- write JS functions
- Write CSS layout
<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 14. Question

questions on javascript prototypes and some trick questions.
learn prototypes here

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

### HTML and CSS

#### 1. Question

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

#### 2. Question

```html
<style>
  .blue {
    background-color: blue;
  }
  .red {
    background-color: red;
  }
</style>
<body>
  <div class="blue red"></div>
  <div class="red blue"></div>
</body>
```

What will be the background color is both the divs?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 3. Question

Write HTML and CSS for a grid of images where in one row there are 3 images. (flexbox) - what if the image sizes are not same.

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 4. Question

display none vs visibility hidden

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 5. Question

Explain CSS Box Model

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 6. Question

Positioning in css along with flex box to style components along with hands on coding.
[Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 7. Question

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

### General Questions

#### 1. Question

Explain the entire process (what happens in the backend) starting from sending request from client to server and then back to client.

OR

What happens when you hit a domain/website in your browser.

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 2. Question

How the Web works (good article on this available on mdn)

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 3. Question

Http Methods and when to use them (GET, PUT,PATCH,POST, DELETE,OPTIONS).

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 4. Question

How Browsers Work

<details>
<summary>Answer</summary>
<p>

[Answer](https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work)

</p>
</details>

---

#### 5. Question

Question on prop drilling

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### . Question

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### . Question

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### . Question

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

## Round 4 : Hiring Manager Round

---

### General Questions

#### 1. Question

How would you ensure that defects are minimized or minimal possible upon release in production?

#### 2. Question

Any role model you want to emulate?

#### 3. Question

Discussion on current company project

#### 4. Question

What are the different aspects you would look upon when you join a new job?

#### 5. Question

What motivates you the most at work?

---

### Company Specific

#### 1. Question

Why you want to join Flipkart? What makes you interesting in this job?

#### 2. Question
