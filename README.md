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
var obj = {};

// using regular property initialization
obj.prop1 = "delete prop1";

// using Object.defineproperty()
Object.defineProperty(obj, 'prop2', {
    value: "delete prop2"
});

console.log(delete obj.prop1);
console.log(delete obj.prop2); 
```

<span><b>Options:-</b></span>

- `true`  `false`
- `false` `false`
- `true`  `true`
- `false` `true`


<details>
<summary>Answer</summary>
 The answer is <em>true</em>, <em>false</em>. When you initialize property using Object.defineProperty(), it is non-configurable. It means you cannot delete the non-configurable property. Use the Object.getOwnPropertyDescriptor() to list the object property descriptors.
</details>

<hr/>

**3.** <span><b>What will be the output of below code?</b></span>

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

**4.** <span><b>What will be the output of below code?</b></span>

```javascript
(function (arg) {
    console.log(typeof arg);
})(() => 'Hello World!');
```

<span><b>Options:-</b></span>

- `Function`
- `String`

<details>
<summary>Answer</summary>
  The answer is <em>Function</em>. We are passing the parameter as the arrow function to the IIFE function as argument.
</details>

<hr/>

**5.** <span><b>What will be the output of below code?</b></span>

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

**6.** <span><b>What will be the output of below code?</b></span>

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
<hr/>

**7.** <span><b>What will be the output of below code?</b></span>

```javascript
let user = {
	greetText: 'Hi',
	name: 'John Doe',

};

Object.defineProperty(user, 'greet', {
	get() {
		return `${this.greetText}! ${this.name}`;
	},
	value: `Hey! ${this.name}`
});

console.log(user.greet);
```

<span><b>Options:-</b></span>

- `Hi! John Doe`
- `Hey! John Doe`
- `undefined`
- `TypeError: Invalid property descriptor`

<details>
<summary>Answer</summary>
  The answer is <em>TypeError: Invalid property descriptor</em>. When using accessor descriptor <em>get or set</em>, we cannot add the data descriptor <em>value</em> or <em>writable</em> with them. Either add accessor descriptor <em>get, set</em>  or data descriptor <em>value, writable</em>.
</details>


