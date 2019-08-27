<h1> My Cheat sheet for basic javascript</h1>
 https://www.cheatography.com/davechild/cheat-sheets/css2/ pretty good cheatsheet. 

 single line comment // comment here
 multi line comment /* comment here */
<script type="text/javascript">  ...
</script>
Include external JS file
<script src="filename.js"></script>
Delay - 1 second timeout
setTimeout(function () {
	
}, 1000);
Functions
function addNumbers(a, b) {
    return a + b; ;
}
x = addNumbers(1, 2);
Edit DOM element
document.getElementById("elementID").innerHTML = "Hello World!";

let age = 32;
In JavaScript we'll typically want to store a function inside a variable:

let fn = function foo(a,b){
  return a + b;
}

let string = "Hello";                
    // local variable, when inside a function

string_2 = "Hello World";             
    // global variable in default context (window.string_2)

string_3 = 'My string can include quotes: "Yeah" ';       
    // single or double quote

string_4 = "My really really really \
really long string broken into \
multiple lines";
NUMBERS
num = 19;                         
    // note lack of ""

num = 0xfe + 2.343 + 2.5e3;       
    // hex, floats, exponents
OBJECTS
let newObject = new Object();     
    // constructor

newObject = {};           
    // constructor shorthand

newObject.name = "Thomas"            
    // dynamic attributes

newObject.name = null         
    // it's there (null item)

delete newObject.name         
    // it's gone (undefined)

newObject["real age"] = 33;       
    // array notation/hash table

let person = {           
    name: "Thomas",             
    details: {
        age: 44,
        "favorite color": "orange"
    }
}
    // create object using JSON (JavaScript Object Notation)
    // note the difference between age: and "favorite color" - one is a symbol and one is a string. They are accessed differently.

person.name
    // "Thomas"

person.details["favorite color"]
    // "orange"

person.details.age
    // 44
ARRAYS
let newArray = [];                
    // empty array

newArray[3] = "hello";               
    // grows dynamically

newArray[2] = 13;                 
    // add any datatype

newArray.push(newObject);         
    // add new item at last index

newArray.pop();               
    // remove it from last index

function foo(a,b){          
  return a + b;
}
    // global function

let fn = function(a,b){     

  return foo(a,b);
}
    // save function as a variable

person.fn = function(a,b){     
  return a + b;
}
    // or as part of object

function bar(a,b){
    let n = a;                  
        // local variable
    function helper(x) {            
        // defining a function inside of another function
        return 1/Math.sqrt(x + n);  
        // can use local variables
    }
    return helper(b);           
        // avoid need for global function
}

foo(1,2) == fn(1,2)   
    // true (3)
bar(1,3);
    // 0.5



So which values are falsy— or evaluate to false when checked as a condition? The list of falsy values includes:

0
Empty strings like "" or ''
null which represent when there is no value at all
undefined which represent when a declared variable lacks a value
NaN, or Not a Number

<h2> Ternary operator </h2>
Take a look at the if...else statement example:

let isNightTime = true;

if (isNightTime) {
  console.log('Turn on the lights!');
} else {
  console.log('Turn off the lights!');
}
We can use a ternary operator to perform the same functionality:

isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');

<b> if, else if, else statements </b>
if () {
    console.log(..)
} else if () {
    console.log(.)
} else {
    console.log()
}

<b> Switch keyword </b>
The switch keyword initiates the statement and is followed by ( ... ), which contains the value that each case will compare. In the example, the value or expression of the switch statement is groceryItem.
Inside the block, { ... }, there are multiple cases. The case keyword checks if the expression matches the specified value that comes after it. The value following the first case is 'tomato'. If the value of groceryItem equalled 'tomato', that case‘s console.log() would run.
The value of groceryItem is 'papaya', so the third case runs— Papayas are $1.29 is logged to the console.
The break keyword tells the computer to exit the block and not execute any more code or check any other cases inside the code block. Note: Without the break keyword at the end of each case, the program would execute the code for all matching cases and the default code as well. This behavior is different from if/else conditional statements which execute only one block of code.
At the end of each switch statement, there is a default statement. If none of the cases are true, then the code in the default statement will run.

<h2> Arrow function () => </h2>
ES6 introduced arrow function syntax, a shorter way to write functions by using the special “fat arrow” () => notation.

Arrow functions remove the need to type out the keyword function every time you need to create a function. Instead, you first include the parameters inside the ( ) and then add an arrow => that points to the function body surrounded in { } like this:

const rectangleArea = (width, height) => {
  let area = width * height;
  return area;
};

<h2>Concise Body Arrow Functions</h2>
JavaScript also provides several ways to refactor arrow function syntax. The most condensed form of the function is known as concise body. We’ll explore a few of these techniques below:

1. Functions that take only a single parameter do not need that parameter to be enclosed in parentheses. However, if a function takes zero or multiple parameters, parentheses are required.
Zero parameters: const functionName = () => {};
One parameter: const functionJNAme = param0ne => {};
Two or more parameters: const functionNAme = 
(paramOne, paramTwo) => {}; 

2. A function body composed of a single-line block does not need curly braces. Without the curly braces, whatever that line evaluates will be automatically returned. The contents of the block should immediately follow the arrow => and the return keyword can be removed. This is referred to as implicit return.
single-line block: const sumNumbers = number + number;
multi-line block: const sumNumbers = number => { 
    const sum = number + number; 
return sum; }


<h1> Explanaition of the arrow funtionc => </h1>
on
var elements = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];

// This statement returns the array: [8, 6, 7, 9]
elements.map(function(element) {
  return element.length;
});

// The regular function above can be written as the arrow function below
elements.map((element) => {
  return element.length;
}); // [8, 6, 7, 9]

// When there is only one parameter, we can remove the surrounding parentheses
elements.map(element => {
  return element.length;
}); // [8, 6, 7, 9]

// When the only statement in an arrow function is `return`, we can remove `return` and remove
// the surrounding curly brackets
elements.map(element => element.length); // [8, 6, 7, 9]


.to_f makes things a float

<h2> OBS! spec.helper.js is supposed to be in the rootfolder, i.e. in the bmichallenge folder - not in spec folder! </h2>

Ruby exposes several different methods for handling equality:
- a.equal?(b) # object identity - a and b refer to the same object
- a.eql?(b) # object equivalence - a and b have the same value
- a == b # object equivalence - a and b have the same value with type conversions]


- <b>Unit testing</b> - pass or fail of short snippets of code to check behaviour.
- <b> Acceptance testing </b>- making sure the program meets business requirements and if it's delivery ready. exempel or user scenario. 
- <b>User acceptance testing </b>(UAT/betatesting/applicationtesting/end user testing) testing in the real world.

<h2> NPM commands </h2>
- The command <i>npm run specs </i> will run your unit tests.
- <i> npm run features </i> will start a local webserver, launch Chrome and run your acceptance tests.
- If you execute <i> npm test </i> in your terminal, both your acceptance tests and unit tests will be run.
