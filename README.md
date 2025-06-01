Sure! Here’s a beautified, well-organized Markdown version of the content you've shared — suitable for inclusion in documentation or study notes.

---

# JavaScript Concepts and Code Snippets

## 📚 Lectures

- [ ] [JavaScript Language](https://javascript.info/js)
- [ ] [Object.defineProperty](https://www.youtube.com/watch?v=_k3WiANNB4U)
- [ ] [Object Properties Configuration](https://javascript.info/object-properties)
- [ ] [FlatMap (filter + map) ](https://www.youtube.com/shorts/QT2-GG-zUzM)

---

## 1. Function vs Variable Hoisting

```js
var show = 1;
console.log(show);
function show() {
    console.log("🎉");
}
console.log(show);
```

**Output:**
```
1
1
```

**Explanation:**  
Function declarations are hoisted before variable declarations, but variables can override them. So the `show` function is overridden by the `show` variable.

---

## 2. Access Array Elements in Reverse

```js
let a = [4, 2, 5, 6, 9];
console.log(a.at(-1)); // 9
console.log(a.at(-2)); // 6
console.log(a.at(0));  // 4
```

---

## 3. `Array()` vs `new Array()`

```js
console.log(new Array(1, 2)); // [1, 2]
console.log(Array(2));        // [ <2 empty items> ]
```

**Note:**  
`Array(n)` creates an empty array of length `n`, while `new Array(a, b)` creates an array with values.

---

## 4. Make Child Class Inherit Method

```js
function Animal() {}
Animal.prototype.home = () => {
    console.log("Forest");
};

function Bird() {}
Bird.prototype = Object.create(Animal.prototype);

const bird = new Bird();
bird.home(); // Forest
```

---

## 5. NaN Behavior

```js
if (NaN) console.log('Success'); else console.log('Fail'); // Fail
console.log(NaN == false);  // false
console.log(NaN === 0);     // false
console.log(NaN === "");    // false
console.log(NaN == 0);      // false
console.log(Object.is(NaN, NaN)); // true
```

---

## 6. Object Key from Array

```js
const obj = { name: "JS" };
const arr = ['name'];
obj[arr] = "react";
console.log(obj.name); // react
```

---

## 7. `setTimeout` with String

```js
const str = `
let n1 = 2;
let n2 = 2;
console.log(n1 + n2)
`;
setTimeout(str, 1000); // 4
```

**Note:**  
`setTimeout` evaluates the string using `eval`.

---

## 8. `await` with a String

```js
console.log(await "4"); // 4
```

**Explanation:**  
Equivalent to `await Promise.resolve("4")`.

---

## 9. String Destructuring (Boxing)

```js
const { length } = "JS";
console.log(length); // 2
```

---

## 10. `async` vs `non-async` function

```js
function fetchData(){}
console.log(fetchData()); // undefined

async function fetchData(){}
console.log(fetchData()); // Promise {<fulfilled>: undefined}

async function fetchData(){ return 1; }
console.log(fetchData()); // Promise {<fulfilled>: 1}
```

---

## 11. String vs Number Operations

```js
const n2 = 10;
const n1 = "2";
console.log(n2 + n1); // "102"
console.log(n2 - n1); // 8
```

---

## 12. `forEach` Loop Mutation

```js
const arr = [0,1,2,3,4,5,6];

arr.forEach(function(num){
    console.log(num);
    if(num === 3) arr.length = 0;
});
```

**Output:**
```
0
1
2
3
```

---

## 13. Array Sparse Indexing

```js
const arr = [];
arr[10] = 10;
console.log(arr.length); // 11
arr[100] = 100;
console.log(arr.length); // 101
```

---

## 14. `forEach` on Sparse Arrays

```js
const arr = [];
arr[10] = 10;
arr[100] = 100;

arr.forEach(d => {
    console.log("Hi");
});
```

**Output:**
```
Hi
Hi
```

---

## 15. Temporal Dead Zone

```js
console.log(z); // ReferenceError
let z = 1;
```

---

## 16. Uninitialized Array with `forEach`

```js
const arr = new Array(2);
console.log(arr); // [ <2 empty items> ]
arr.forEach(elem => console.log(elem)); // (nothing logs)
```

---

## 17. Spread Operator on Sparse Arrays

```js
const arr = new Array(2);
console.log(arr); // [ <2 empty items> ]
[...arr].forEach(elem => console.log("🐦"));
```

**Output:**
```
🐦
🐦
```

---

## 18. Promise Chaining

```js
const P1 = new Promise(resolve => resolve("Done"));
P1.then(() => 10)
  .then(data => console.log(data)); // 10
```

---

## 19. `reverse()` vs `toReversed()`

```js
const arr = [1, 2, 3];
const reversed = arr.reverse();    // Mutates original
const notReversed = arr.toReversed(); // Does not mutate
```

---

## 20. Resolving Function in Promise

```js
Promise.resolve(() => {
    return "🎉";
}).then(data => {
    console.log(data); // function itself, not return value
});
```

---

## 21. Resolve String in Promise

```js
Promise.resolve("3").then(data => console.log(data)); // "3"
```

---

## 22. Global Variable Assignment

```js
function test() {
    const a = b = c = "🥗";
}
test();
console.log(typeof a); // undefined
console.log(typeof b); // string
console.log(typeof c); // string
```

---

## 23. Promise with Microtasks

```js
new Promise((resolve) => {
    resolve("🐦");
    Promise.resolve().then(() => {
        console.log("🥗"); 
    });
}).then((data) => {
    console.log(data);
});
```

**Output:**
```
🥗
🐦
```

---

## 24. Centering Without `position`, `flex`, or `grid`

```html
<div class="parent">
    <div class="child"></div>
</div>
```

```css
.parent {
    background-color: violet;
    align-content: center;
}

.child {
    background-color: red;
    margin: auto;
}
```

---

## 25. `delete` on Local Variable

```js
const func = (function (a) {
    delete a;
    return a;
})(5);

console.log(func); // 5
```

---

## 26. Object Keys as Objects

```js
const a = {};
const b = { key: "b" };
const c = { key: "c" };

a[b] = 123;
a[c] = 456;

console.log(a[b]); // 456
```

**Note:**  
Object keys are converted to strings, so both use `"[object Object]"`.

---

## 27. `JSON.stringify` with Whitelist

```js
const User = {
    name: "Leynd",
    age: 23,
    height: 5.6
};
const result = JSON.stringify(User, ["age", "height"]);
console.log(result); // {"age":23,"height":5.6}
```

---

## 28. `this` Binding in Class Methods

```js
class Person {
    constructor(name) {
        this.name = name;
    }
    fn() {
        console.log(this.name);
    }
}

const person = new Person("Mr.X");
const copyFn = person.fn;
copyFn(); // undefined
```

**Fix Using `bind`:**
```js
const copyFn = person.fn.bind(person);
copyFn(); // "Mr.X"
```

---
## 29. "a.b.c.d.e" convert to object  { a: { b: { c: { d: { e: {} } } } } }
{
  a: {
    b: {
      c: {
        d: {
          e: {}
        }
      }
    }
  }
}

```js
const str = "a.b.c.d.e";

const strArr = str.split(".");

const obj = strArr.reduceRight((acc, next) => ({[next]:acc}));

console.log(obj);
```

---

