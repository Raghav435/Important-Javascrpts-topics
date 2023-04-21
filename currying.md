## What is currying function in JavaScript ?

### It is a technique in functional programming, transformation of the function of multiple arguments into several functions of a single argument in sequence.

Example :-

```
const currying = function calculateVolume(length) {
  return function (breadth) {
    return function (height) {
      return length * breadth * height;
    };
  };
};
console.log(currying(4)(5)(6));

```
