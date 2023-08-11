# Interview Questions

#### 1. Question

Explain the entire process (what happens in the backend) starting from sending request from client to server and then back to client.

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### 2. Question

How would you ensure that defects are minimized or minimal possible upon release in production?

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

#### . Question

```javascript

```

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

### How the Web works (good article on this available on mdn)

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

### Http Methods and when to use them (GET, PUT,PATCH,POST, DELETE,OPTIONS).

<details>
<summary>Answer</summary>
<p>
HTTP methods (also known as HTTP verbs) are fundamental concepts in the HTTP protocol, used to indicate the desired action to be performed on a resource. Each HTTP method has a specific purpose and use case. Here's an overview of commonly used HTTP methods and when to use them:

**GET:**

- Purpose: Retrieve data from the server.
- Use Cases: Use GET to fetch a resource's representation. It should be safe (no side effects) and idempotent (repeated requests have the same effect as a single request).
- Example: Fetching a blog post, retrieving user profile information.

**POST:**

- Purpose: Submit data to the server for processing.
- Use Cases: Use POST to send data to the server to create a new resource or perform a non-idempotent action that might have side effects.
- Example: Creating a new user account, submitting a form, adding a comment.

**PUT:**

- Purpose: Update or create a resource on the server.
- Use Cases: Use PUT to update an existing resource or create a new one if it doesn't exist. It should be idempotent (repeated requests don't have unintended side effects).
- Example: Updating a user's profile, updating a blog post.

**PATCH:**

- Purpose: Partially update a resource on the server.
- Use Cases: Use PATCH to apply partial modifications to a resource. It is used when you want to update specific fields of a resource without affecting the rest of the data.
- Example: Updating only the description of a blog post, modifying certain properties of an object.

**DELETE:**

- Purpose: Remove a resource from the server.
- Use Cases: Use DELETE to delete a resource from the server. It should be idempotent and safe if possible (although deletion is inherently not safe).
- Example: Deleting a user account, removing a comment.

**OPTIONS:**

- Purpose: Retrieve information about the communication options for the target resource.
- Use Cases: Use OPTIONS to request information about the communication options supported by the server for a specific resource.
- Example: Checking supported HTTP methods, CORS preflight requests.

</p>
</details>

---

### What are the HTTP Codes

<details>
<summary>Answer</summary>
<p>

Informational responses (100 – 199)
Successful responses (200 – 299)
Redirection messages (300 – 399)
Client error responses (400 – 499)
Server error responses (500 – 599)

</p>
</details>

---

### How Browsers Work

<details>
<summary>Answer</summary>
<p>

[Answer](https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work)

</p>
</details>

---

### What is difference between Session Storage, Local Storage and Cookies

Session storage, cookies, and localStorage are all techniques for storing data in web applications on the client-side, but they differ in terms of capacity, persistence, and usage. Let's explore each of them in more detail:

**Session Storage:**

- sessionStorage is a client-side storage mechanism available in modern web browsers.
- Data stored in sessionStorage is specific to a particular browser tab or window and is available only for the duration of that session (until the tab or window is closed).
- It provides a simple key-value storage mechanism similar to JavaScript objects.
  sessionStorage is often used to store temporary data that needs to be accessible within a single browsing session, such as form data or state information.
- Data stored in sessionStorage does not persist across different sessions or browser tabs/windows.

**Cookies:**

- Cookies are small pieces of data that a web server can store on the user's device (client-side).
- Cookies are sent back and forth between the client and the server with each HTTP request and response.
- They can be used for various purposes, such as user authentication, tracking user behavior, and maintaining session state.
- Cookies have an expiration time, which can be set to make them persistent (stored even after the browser is closed) or session-based (deleted when the browser is closed).
- Cookies are subject to size limitations (usually around 4KB per cookie) and are often used for storing small amounts of data.

**localStorage:**

- localStorage is another client-side storage mechanism available in modern web browsers.
- It provides a larger storage space (usually around 5-10 MB) compared to cookies or sessionStorage.
- Data stored in localStorage persists even after the browser is closed and reopened.
- Like sessionStorage, localStorage also uses a simple key-value storage model.
- localStorage is often used for storing larger amounts of data, caching resources, or maintaining application state across different sessions.

In summary, sessionStorage and localStorage are client-side storage options that provide a way to store data in a user's browser. sessionStorage is temporary and tied to a single session, while localStorage is more persistent and lasts beyond a session. Cookies, on the other hand, are small pieces of data that are sent between the client and server with each request and are often used for various purposes, including tracking and authentication. The choice of which mechanism to use depends on factors such as data size, persistence requirements, and the specific use case of your web application.

---
