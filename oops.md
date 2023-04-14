There are certain features or mechanisms which make a Language Object-Oriented like:

# OOPs Concept in JavaScript

## Object

## Classes

## Encapsulation

## Abstraction

## Inheritance

## Polymorphism

## Object:- An Object is a unique entity that contains properties and methods. For example “a car” is a real-life Object, which has some characteristics like color, type, model, and horsepower and performs certain actions like driving. The characteristics of an Object are called Properties in Object-Oriented Programming and the actions are called methods. An Object is an instance of a class. Objects are everywhere in JavaScript, almost every element is an Object whether it is a function, array, or string.

> Note: A Method in javascript is a property of an object whose value is a function.

The object can be created in two ways in JavaScript:

Example: Using an Object Literal.

    // Defining object
    let person = {
        first_name:'Mukul',
        last_name: 'Latiyan',

        //method
        getFunction : function(){
            return (`The name of the person is
              ${person.first_name} ${person.last_name}`)
        },
        //object within object
        phone_number : {
            mobile:'12345',
            landline:'6789'
        }
    }
    console.log(person.getFunction());
    console.log(person.phone_number.landline);

Example: Using an Object Constructor.

    // Using a constructor
    function person(first_name,last_name){
       this.first_name = first_name;
       this.last_name = last_name;
    }
    // Creating new instances of person object
    let person1 = new person('Mukul','Latiyan');
    let person2 = new person('Rahul','Avasthi');

    console.log(person1.first_name);
    console.log(`${person2.first_name} ${person2.last_name}`);

## Classes: Classes are blueprints of an Object. A class can have many Objects because the class is a template while Objects are instances of the class or the concrete implementation.Before we move further into implementation, we should know unlike other Object Oriented languages there are no classes in JavaScript we have only Object. To be more precise, JavaScript is a prototype-based Object Oriented Language, which means it doesn’t have classes, rather it defines behaviors using a constructor function and then reuses it using the prototype.

> Note: Even the classes provided by ECMA2015 are objects.

JavaScript classes, introduced in ECMAScript 2015, are primarily syntactical sugar over JavaScript’s existing prototype-based inheritance. The class syntax is not introducing a new object-oriented inheritance model to JavaScript. JavaScript classes provide a much simpler and clearer syntax to create objects and deal with inheritance.

-Mozilla Developer Network

Example: Let’s use ES6 classes then we will look at the traditional way of defining an Object and simulate them as classes.

    // Defining class using es6
    class Vehicle {
      constructor(name, maker, engine) {
        this.name = name;
        this.maker =  maker;
        this.engine = engine;
      }
      getDetails(){
          return (`The name of the bike is ${this.name}.`)
      }
    }
    // Making object with the help of the constructor
    let bike1 = new Vehicle('Hayabusa', 'Suzuki', '1340cc');
    let bike2 = new Vehicle('Ninja', 'Kawasaki', '998cc');

    console.log(bike1.name);    // Hayabusa
    console.log(bike2.maker);   // Kawasaki
    console.log(bike1.getDetails());

## Abstraction: Abstraction means displaying only essential information and hiding the details. Data abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation.

Example:

    // Abstraction example
    function person(fname,lname){
        let firstname = fname;
        let lastname = lname;

        let getDetails_noaccess = function(){
            return (`First name is: ${firstname} Last
                name is: ${lastname}`);
        }

        this.getDetails_access = function(){
            return (`First name is: ${firstname}, Last
                name is: ${lastname}`);
        }
    }
    let person1 = new person('Mukul','Latiyan');
    console.log(person1.firstname);
    console.log(person1.getDetails_noaccess);
    console.log(person1.getDetails_access());

## Encapsulation: The process of wrapping properties and functions within a single unit is known as encapsulation.

Example: Let’s understand encapsulation with an example.

    // Encapsulation example
    class person{
        constructor(name,id){
            this.name = name;
            this.id = id;
        }
        add_Address(add){
            this.add = add;
        }
        getDetails(){
            console.log(`Name is ${this.name},
            Address is: ${this.add}`);
        }
    }

    let person1 = new person('Mukul',21);
    person1.add_Address('Delhi');
    person1.getDetails();

## Inheritance: It is a concept in which some properties and methods of an Object are being used by another Object. Unlike most of the OOP languages where classes inherit classes, JavaScript Objects inherit Objects i.e. certain features (property and methods) of one object can be reused by other Objects.

Example: Let’s understand inheritance and polymorphism with an example.

    // Inheritance example
    class person{
        constructor(name){
            this.name = name;
        }
        // method to return the string
        toString(){
            return (`Name of person: ${this.name}`);
        }
    }
    class student extends person{
        constructor(name,id){
            // super keyword for calling the above
            // class constructor
            super(name);
            this.id = id;
        }
        toString(){
            return (`${super.toString()},
            Student ID: ${this.id}`);
        }
    }
    let student1 = new student('Mukul',22);
    console.log(student1.toString());

## Polymorphism: Polymorphism is one of the core concepts of object-oriented programming languages. Polymorphism means the same function with different signatures is called many times. In real life, for example, a boy at the same time may be a student, a class monitor, etc. So a boy can perform different operations at the same time. Polymorphism can be achieved by method overriding and method overloading
