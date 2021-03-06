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
   

## Operators

Javascript provides us with certain operators that we can use with variables and constants to create **expressions**.
With these expressions we can implement logic and algorithms.

### Different types of Operators in JavaScript

1. Arithmetic
2. Assignment
3. Comparision
4. Logical
5. Bitwise

#### 1. Arithmetic Operators

Eg:

    let x = 10;
    let y = 20;
    
    console.log(x + y);  // Addition operator
    console.log(x - y);  // Subtraction operator
    console.log(x * y);  // Multiplication operator
    console.log(x / y);  // Division operator
    console.log(x % y);  // Modulus operator
    console.log(x ** y);  // Exponential operator (Power of operator)
    console.log(x++);     // Increment Operator
    console.log(x--);     // Decrement Operator
    

#### 2. Assignment operator

Eg:

    let x = 10;     // Assigment operator
    x += 2          // This is same as x = x + 2;


#### 3. Comparision Operator

Eg:

    let x = 1;
    
    // Relational operators
    console.log(x > 0);   // Compares and returns boolean value true or false. In this case the value true.
    console.log(x >= 1);  // Still returns true.
    console.log( x < 1);
    console.log( x <= 1);
    
    // Equality operators
    console.log(x === 1);
    console.log(x !== 1);

##### What is the difference between === and == operators?

Eg:

    // Strict equality operator (Checks for same Type + Value)
    console.log(1 === 1);   // Returns true
    console.log('1' === 1); // Returns false
    
    // Lose equality operator (Checks only Value)
    console.log(1 == 1);    // Returns true
    console.log('1' === 1); // Returns true
    console.log(true  === 1); // Returns true


##### Ternary Operators

Eg:

    // If a customer has more than 100 points, they are Gold customers
    // Else they are Silver customers

    let points = 110;

    let customerType = points > 100 ? "Gold" : "Silver";
    console.log(customerType); // Output: "Gold"


#### 4. Logical Operators

JS supports 3 logical operators - Logical AND, Logical OR and Logical NOT.

Eg:

    // Logical AND (&&)
    // Returns TRUE of both operands are TRUE
    console.log(true && true); // Output: true
    console.log(true && false); // Output: false

    // Logical OR (||)
    // Returns TRUE if atleast one of the operand is TRUE
    console.log(true || true); // Output: true
    console.log(true || false); // Output: true
    console.log(false || true); // Output: true
    console.log(false || false); // Output: false

    // Logical NOT (!)
    // Returns  opposite of the current boolean value
    console.log(!true); // Output: false
    console.log(!false); // Output: true

##### Logical Operators with Non Boolean values

If one of the operand is not boolean, it checks for it's truthy or falsey value.
It then returns this truthy value.

Eg:

    console.log(false || 'Amar');   // Output: 'Amar'
    console.log(false || 1);   // Output: 1
    console.log(false || 1 || 2); //Output: 1 because OR returns as soon as one of the value is true or truthy! This is called short circuiting.

###### What are falsy values in JS

  1.  Undefined
  2.  null
  3.  0
  4.  ''
  5.  NaN

So anything that is not falsey is a truthy value!

But where is it used? Here is a real world example:

Eg:

    let userColor = undefined;
    let defaultColor = 'green';
    let currentColor = userColor || defaultColor;
    console.log(currentColor);    // Output: 'green'


#### 5. Bitwise Operators

Performs logical operations at the bit level

Eg:

    // 1 = 00000001
    // 2 = 00000010
    // 3 = 00000011
    
    // Bitwise OR
    console.log(1 | 2);     // Output: 3

    // Bitwise AND
    console.log(1 & 2);     // Output: 0
    
    // Bitwise NOT
    console(!1);            // Output: 0


### Operator Precedence

Eg:

    let x = 10 + 3 * 2
    console.log(x);         // Output 16 bcoz * has higher precedence over + so it is computed first.


## Conditional Statements

JavaScript supports two conditional statements:

1. If...else
2. Switch...case

### 1. If...else

Syntax:

    if (condition) {
      statement
    }
    else if (anotherCondition) {
      statement
    }
    else {
      statement
    } 


### 2. Switch...case

Syntax:

    switch(variable) {
      case value1:
        statement
        break;
      case value2:
        statement
        break;
      default:
        statement
    }


## Loops

In JS we have different kind of loops:

1. For loop
2. While loop
3. Do...while loop
4. For...in
5. For...of

### 1. For loop

Syntax

    for(initExpression; condition; incrementExpression) {
      statements
    }

### 2. While loop

Difference from for loop is that we have to declare the initExpression external to the loop

Syntax

    initExpression;
    
    while(condiion) {
      statements
    }

## 3. Do While loop

Gets executed at least once.

Syntax

    initExpression;
    
    do {
      statements
    } while(condition);


## 4. For in loop

Usually used to iterate over properties of an object or elements of an array (but may be not so ideal, check next for loop type for this).

Eg:

    const person = {
      name: 'Amar',
      age: 30,
    };
    
    for  (let key in person)
      console.log(key, person[key]);


## 5. For of loop

Eg:

    let const colors = ['red', 'green', 'blue'];
    
    for (let color of colors)
      console.log(color);

## Break and continue

Break keyword is used to break out of a loop

Eg:

    let i = 0;
    
    while(i <= 10) {
      if (i === 5) break;
      console.log(i);   // Output: 0, 1, 2, 3, 4
      i++;
    }

Continue keyword can be used to skip a specific iteration of loop.


Eg:

    let i = 0;
    
    while(i <= 10) {
      if (i % 2 === 0) continue;
      console.log(i);   // Output: 1, 3, 5, 7, 9
      i++;
    }

---------

# Asynchronous Code Execution Methods
1. Asynchronous Callback functions
2. setTimeout()
3. setInterval()
4. requestAnimationFrame()
5. Promises
6. Promise.all()
7. Async/await
