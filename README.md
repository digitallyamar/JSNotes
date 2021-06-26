# JSNotes

## How to run JS code?
There are two ways:
  1. In a web browser
      Eg: 
      
          2 + 2 // Try in browser JS console
  3. Using Node
      Eg:
      
          node index.js

---------

# JavaScript Basics

## Variables

Variables are used to store data temporarily in computer memory.

### How to declare a variable?
Two ways:

#### Using var keyword
This was the method used prior to ES6. But it has it's own set of problems and usually avoided these days.

Eg: 

    var name = 'Amar';

### Using let keyword
This is the preferred method since ES6.

Eg: 

    let name = 'Amar';


### Rules for naming a variable

  1. Cannot be a reserved keyword like for, if etc.
  2. Should be meaningful.
  3. Cannot start with a number.
  4. Cannot contain space or hyphen (-)
  5. They are case sensitive
  6. Modern best practice is to declare different variables in their own line

## Constants

Constants are used to store values in memory whose value is not expected to change.

  Eg:

    const pi = 3.1415;

## Categories Of Types

There are two categories:

### Primitives / Value Types

These includes:

  1. String
  2. Number - No separate types for integers and float. All are of type *numbers*.
  3. Boolean
  4. Undefined
      1. Any variable assigned to this value is also of type "undefined". 
      
      Eg: 
      
          lastName = undefined; // typeof(lastName) is also undefined.
      
      2. All unitialized variables are by default set to undefined value by JS.
  
  5. Null
      1. Null is of type object. 
         
       Eg:
          
          let selectedItem = null; // typeof(selectedItem) is an Object type.
  
  6. Symbol


### Reference Types

These includes:

  1. Objects
  
    Eg:
    
      let person = {
        name: 'Amar',
        age: 30,
      };
      
   Two ways to access properties of an obect:
   1. Using dot notation.

      Eg:
      
          person.name = 'Amarnath';
     
   This is the easiest, concise and shorter. Should be your preferred method when we know the property name.
   
   2. Using bracket notation

      Eg:
         
          person['name']
          
  Use this when you are not sure of the property name. 
  
  Eg:
  
        let selection = 'name';
        person[selection] = 'Amarnath';
          
  3. Arrays
     1. It can hold data of different types as well.
     2. Both data type and the length of an array can change dynamically.
     
     Eg:
     
          let selectedColors = ['red', 'yellow'];
          console.log(selectedColors);
          selectedColors[2] = 2;
          console.log(selectedColors);
     
     
     When you run
     
          typeof(selectedColors); // Array is an "object" !!
     
     So array object comes with a lot of built in properties and methods like map, filter, forEach, length etc.
     
  5. Functions - A set of statements used to perform a specific task or calculate a value.
      Eg:
      
          function greet(name) {    // This is receiving a parameter
            console.log('Hello ' + name);
          }
          
          greet('Amar');  // This is an argument
   
   
## Why is JS considered a Dynamic language?

JS is considered as a dynamic language because it is dynamically typed. 

Which means for example:
  A variable holding a string can be changed to hold a number later.
  
  Eg:
  
    let value = "red"; //Initialized to a string value
    value = 6; // This is still valid!
   


---------

# Asynchronous Code Execution Methods
1. Asynchronous Callback functions
2. setTimeout()
3. setInterval()
4. requestAnimationFrame()
5. Promises
6. Promise.all()
7. Async/await
