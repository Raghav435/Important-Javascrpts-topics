## What are Callbacks?

### A callback is a function that is passed as an argument to another function, and is called after the main function has finished its execution. The main function is called with a callback function as its argument, and when the main function is finished, it calls the callback function to provide a result. Callbacks allow you to handle the results of an asynchronous operation in a non-blocking manner, which means that the program can continue to run while the operation is being executed.

```
Example -1

// function
function greet(name, callback) {
  console.log("Hi" + " " + name);
  callback();
}

// callback function
function callMe() {
  console.log("I am callback function");
}

// passing function as an argument
greet("Peter", callMe);

Example - 2

function sum(a, b) {
  console.log(a + b);
}

function operation(val1, val2, callback) {
  callback(val1, val2);
}

operation(6, 5, sum);


```
