1. 
```sh
// code
var show = 1;
console.log(show);
function show() {
    console.log("🎉");
}
console.log(show);
```
```sh
// output
1
1
```
 - Because during hoisting functions will get more priority then variables. So while parsing function "show" will attached to the scope. After that variable "show" variable will parse and will override the function "show" with variable "show". So at the end the show will contain value assigned to it which is 1. 
---
2.
How to access array elements in reverse order.
```sh
// code
let a = [4,2,5,6,9];
console.log(a.at(-1));
console.log(a.at(-2));
console.log(a.at(0));
```
```sh
// output
9
8
4
```
---
3.
```sh
console.log(new Array(1,2)); // (1,2) workes as array elements, initialized with 1 and 2
console.log(Array(2)); // (2) work as array length, empty array of length 2
```
```sh
[1,2]
[2 empty array]
```
- new Array() and Array() both works same way.

---
4.
Make this code working
```sh
function Animal() {
    Animal.prototype.home = () => {
        console.log("Forest")
    }
}
function Bird() {}
const bird = new Bird();
bird.home();// make it log Forest
```
Ans
```sh
function Animal() {}
Animal.prototype.home = () => {
    console.log("Forest")
}
function Bird() {}
Bird.prototype = Object.create(Animal.prototype); // Inheriting Animal
const bird = new Bird();
bird.home();
```

---
5.
```sh
if(NaN){
    console.log('Success');
}else {
    console.log('Fail');
} // output -> "Fail"
console.log(NaN == false) // false
console.log(NaN === 0) // false
console.log(NaN === "") // false
console.log(NaN == 0); // false
console.log(Object.is(NaN, NaN)); // trun e
```
---
6.
```sh
const obj = {name:"JS"};
const arr = ['name'];
obj[arr] = "react";
console.log(obj.name);
```
```sh
//output
react
```
---
7.
```sh
const str = `let n1 = 2;
let n2 = 2;
console.log(n1+n2)`
setTimeout(str, 1000);
```
```sh
//output
4
```
setTimeout usees eval() method to execute str

---
8.
```sh
console.log(await "4");
```
```sh
//output
4
```
console.log(await "4"); works like await Promise.resolve("4")

---
9.
```sh
const {length} = "JS";
console.log(length);
```
```sh
//output
2
```
This code is working on the concept of "BOXING". Please watch the explaination.

---
10.
```sh
function fetchData(){
    
}
console.log(fetchData());
```
```sh
//output
undefined
```
```sh
async function fetchData(){
    
}
console.log(fetchData());
```
```sh
//output
Promise {<fulfilled>: undefined}
```
```sh
async function fetchData(){
    return 1
}
console.log(fetchData());
```
```sh
//output
Promise {<fulfilled>: 1}
```

---
11.
```sh
const n2 = 10;
const n1 = "2";
console.log(n2+n1);
console.log(n2-n1);
```
```sh
//output
'102'
8
```
Node: incase of '+' javascirpt gives more importance to concatination then addition while one of the operand is string
































