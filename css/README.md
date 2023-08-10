# CSS

## General Questions

### How to center a div

<details>
<summary>Answer</summary>
<p>

### Centering a div

**Horizontal center:**

- `margin: auto` : centers the div horizontally
- [codepen example](https://codepen.io/tanmayid/pen/MWzdzor)

**Vertical center:**

- `position: absolute;`
- `top: 50%;`
- `transform: translate(0, -50%);`
- [codepen example](https://codepen.io/tanmayid/pen/mdQYaVW)

**Position to center:**

- `position: absolute;`
- `top: 50%;`
- `left: 50%;`
- `transform: translate(-50%,-50%);`
- [codepen example](https://codepen.io/tanmayid/pen/vYQwvXg)

### Centering a div within a div

**Horizontal center - flexbox**

- apply below styles to parent
- `display: flex`
- `justify-content: center` : centers the div horizontally
- [codepen example](https://codepen.io/tanmayid/pen/abQrPWz)

**Vertical center - flexbox**

- apply below styles to parent
- `display: flex`
- `align-items: center` : centers the div vertically
- [codepen example](https://codepen.io/tanmayid/pen/bGQyOJO)

**Position center - flexbox**

- apply below styles to parent
- `display: flex`
- `justify-content: center` : centers the div horizontally
- `align-items: center` : centers the div vertically
- [codepen example](https://codepen.io/tanmayid/pen/JjeqwqE)

**Position center - css property**

- apply below style to parent
- `position: relative`
- apply below styles to child
- `position: absolute;`
- `top: 50%;`
- `left: 50%;`
- `transform: translate(-50%,-50%);`
- [codepen example](https://codepen.io/tanmayid/pen/OJaYdPa)

</p>
</details>

---

### What is the difference between CSS and CSS3 ?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What are the selector in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What is media query in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What is different position in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What is bom in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What is difference between PX, unit, em, rem in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What is flex box in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What is pseudo selector in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### How to make website responsive?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### What are breakpoint for viewport responsive device?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### Why we use box-sizing in css?

<details>
<summary>Answer</summary>
<p>
</p>
</details>

---

### Explain CSS Box Model

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

## Questions asked in Interivews

### How to center a div horizontally

<details>
<summary>Answer</summary>
<p>

```html
<div class="square"></div>
```

```css
.square {
  /*other styles*/
  margin: auto;
}
```

</p>
</details>

### How to center a div horizontally within a div

<details>
<summary>Answer</summary>
<p>

```html
<div class="parent">
  <div class="child"></div>
</div>
```

```css
/*add below lines to the parent div of the element which you want to center*/
.parent {
  /*other styles*/
  display: flex;
  justify-content: center;
}

.child {
  /*other styles*/
}
```

</p>
</details>

---
