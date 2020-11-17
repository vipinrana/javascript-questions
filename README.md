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
 The answer is <em>true</em>. The reason is once the callMe() function is called, the variable <b>x</b> will treat as a window property and also note that variable <b>x</b> is without any declaration keyword(var, let or const). You can access using <b>window.x</b> unless you didn't delete it.
</details>

<hr/>

**2.** <span><b>What will be the output of below code?</b></span>

```javascript
let x = (() => 'foo bar')();

((xarg) => x = null)(x);

console.log(x);
```

<span><b>Options:-</b></span>

- `null`
- `foo bar`

<details>
<summary>Answer</summary>
 The answer is <em>null</em>. It's because in second line we reassign the variable <b>x</b> with null.
</details>

<hr/>

**3.** <span><b>What will be the output of below code?</b></span>

```javascript
let obj = Object.defineProperties({}, {
    id: {
        value: 1,
        writable: true,
        enumerable: true,
        configurable: true
    },
    name: {
        value: 'John Doe',
        writable: true,
        enumerable: true,
        configurable: true
    },
    age: {
        value: 25,
        writable: true,
        enumerable: false,
        configurable: true
    },
});

let cpObj = Object.assign({}, obj);

console.log(cpObj);
```

<span><b>Options:-</b></span>

- `{id: 1, name: 'John Doe', age: 25}`
- `{id: 1, name: 'John Doe'}`
- `{id: 1, age: 25}`

<details>
<summary>Answer</summary>
  The answer is <em>{id: 1, name: 'John Doe'}</em>. It's because object <b>obj</b> has property <b>age</b> of enumerable <em>false</em>. Object.assign() only copies enumerated own properties from sources.
</details>

<hr/>

**4.** <span><b>What will be the output of below code?</b></span>

```javascript
let obj = Object.defineProperties({}, {
    id: {
        value: 1,
        writable: true,
        enumerable: true,
        configurable: true
    },
    name: {
        value: 'John Doe',
        writable: false,
        enumerable: true,
        configurable: true
    }
});

obj.name = 'Jack Barker';

let cpObj = Object.assign({}, obj);

cpObj.name = 'Bruce Williams';

console.log(obj.name, cpObj.name);
```

<span><b>Options:-</b></span>

- `John Doe, John Doe`
- `John Doe, Bruce Williams`
- `Jack Barker, Bruce Williams`
- `Jack Barker, John Doe`

<details>
<summary>Answer</summary>
  The answer is <em>John Doe, Bruce Williams</em>. It's because Object.assign() only copies enumerated own properties from sources not the property attributes(writable, configurable).
</details>


