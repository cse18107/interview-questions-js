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






























