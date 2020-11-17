<h1 style="color:rgb(63 81 181);">JavaScript Questions</h2>

<h3><b>Here are some of the javascript questions to try</b></h3>

**1.** <span style="color:rgb(97 3 43);"><b>What will be the output of below code?</b></span>

```javascript
function callMe() {
  x = 3;
}

callMe();

console.log(delete x);
```

<span style="color:rgb(103 58 183);"><b>Options:-</b></span>

- `true`
- `false`

<details>
<summary style="color:rgb(9 100 191);font-weight:bold;">Answer</summary>
 The answer is <em style="background: #cccccc45;padding: 0px 10px;border-radius: 3px;">true</em>. The reason is once the callMe() function is called, the variable <b>x</b> will treat as a window variable and also note that variable <b>x</b> is without any declaration keyword(var, let or const).
</details>
