### What will this code snippet print:
```
const numbers = [1,3,5,7,9]
numbers.pop()
console.log(numbers);
```
[1,3,5,7]

### What are the possible states of a promise?
Pending, Fulfilled, Rejected

### Which of the following will return false?
- !!(true * 0)
- !("Hello world")
- !!NaN
Ans: All of the above

### Which of the following code snippets will log "Hello":
const string = "Hello"; console.log( string.slice(-(string.length)) );

### How can we pause code execution until a promise is not fulfilled/rejected?
Use async/await

### Which of the following have the type number
- 100/0
- 0/"hello world"
- Both (a) & (b)
Ans: None of the above

### Which of the following is hoisted?
var

### Which of the following expression(s) will store "Hello World" in x?
var x = null?? undefined?? "Hello World"

### Which of the following can be used to run code when a promise is fulfilled?
then()

### Which of the code snippents below will multiply two numbers together?
- function someFunction(a) {return (b) => {return a*b;} }
- function someFunction(a,b){ return a*b; }
Ans: Both (1) and (2)

### Which of the following can be used to run code when a promise is rejected?
catch()

### What is the initial state of a promise?
pending

### The Event Queue stores codes that
are ready to be sent to the call stack for execution

### Is JavaScript synchronous by nature?
Yes

### Which of the following methods can be used to change the ID of an element?
- element.setAttribute("id", "new-id")
- element.id = "new-id"
Ans: Both (1) & (2)

### What is the alternative for reject when creating a new promise?
There is no alternative, we need to use reject

### What will be the code below log:
```
var promise = new Promise(function(resolve, reject){
    resolve("OK");
});

var promise2 = promise.then(function(data){
    return data;
});

var promise3 = promise.then(function(data){
    return data;
});

console.log(p2 == p3);
```
Ans: false

### If var x = NaN, select the statement(s) which are correct
x === x returns false

### Is JavaScript multithreaded?
No

### Which among the following is the slowest to run assuming that we are targeting the same element?
querySelectorAll()

### Find the mistake in the code snippet below:
```
function getData() {
    try {
        const data = await fetch(URL)
    } catch (err) {
        console.error("Something wrong happened")
    }
}
```
We need to add the async modifier to the function

### What are the two arugments that setTimeout() expects?
Callback function and Delay time

### Can the return keyword be used outside a function?
No

### Can we use == or === to compare objects in JavaScript?
No

### Which of the following data types are mutable in JavaScript?
Arrays

### What is the value of [1,2,3].at(-1)?
3

### What will this code snippet print:
```
const strings = ["E", "N", "J", "O", "Y"];
const reduced = strings.reduce((p,o) => p.concat(o));
console.log(reduced);
```
Ans: "ENJOY"

### What will this code snippet print:
```
let name = "hello";
name.toUpperCase();
console.log(name);
```
Ans: hello

### What is the function that's passed to Promise() as an argument called?
Executor

### The delay in setTimeout is in?
Miliseconds