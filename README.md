<h1>JavaScript Questions</h2>

<h3><b>Here are some of the javascript questions to try</b></h3>

**1.** <span><b>What will be the output of below code?</b></span>

```javascript
function callMe() {
  x = 3;
}

callMe();

console.log(delete x);
```

<span><b>Options:-</b></span>

- `true`
- `false`

<details>
<summary>Answer</summary>
 The answer is <em>true</em>. The reason is once the callMe() function is called, the variable <b>x</b> will treat as a window variable and also note that variable <b>x</b> is without any declaration keyword(var, let or const).
</details>
