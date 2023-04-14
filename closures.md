## Closures:- A Closures is the combination of a function bundled together (enclosed) with references to its surroundings state(the lexical environment). In closures function are able to remember the previous value i.e. in the outer scope.

### Lexical Scoping:- A function scope’s ability to access variables from the parent scope is known as lexical scope. We refer to the parent function’s lexical binding of the child function as “lexically binding.”

Example 1: This example shows the basic use of closure.

    function outer()
     {
        var a = 10;
        function inner(b){
        return a+b;
    }
        return inner;
    }

    var fn = outer();
    console.log(fn(5));

Example 2:-

    function add(a)
    {
        function myFun(b) {
        return a + b;
    }
        return myFun;
    }
    console.log(add(4)(5));

Example 3:-

    function student()
    {
        let firstName = "Masai";

        setTimeout(() => {
        console.log(firstName);
        }, 2000);

        return firstName;
    }

    console.log(student());
