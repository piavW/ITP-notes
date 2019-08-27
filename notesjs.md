TIPS FRÅN COACHEN: Fokusera på DOM-manipultion -alltså att påverka HTML sidan. 
# h1
## h2
### h3

- one
- two

```bash
$ code .
```

then we open the file `hello.rb`



Javascript
runs in browser not terminal. 
Every line in javascript should end with ; 
Can be embedded in the html document <script> code here </script>. 
Can be sourced to it’s own document: <script src=“code.js”/> 

Open dev.tools in webbrowser: right click, choose inspect. Eller option +command +i
I dev tools, gå till console, skriv document - får fram hela html dokumentet
Before we used var, now it’s const for variables we don’t want to change, and let is for variables which can be updated. 

Camelcase/dromedar skrivtyp: firstName	i JS
Pascalcase skrivtyp: FirstName	i JS ibland
Snakecase skrivstyp: first_name	i JS
Kebabcase skrivtyp: first-name

använd backticks ``när det är stringinterprelation` ex. return(`your name is ${firstName}`);

console.log( ) shows things on the console

To declare a variable:
let age = 26;  behöver inga “ “ för nummer 
Let string = “Hello” behöver “ “ för string

Functions in Ruby:
def foo(a, b)
  a + b
end

Functions In Javascript we'll typically want to store a function inside a variable:
let fn = function foo(a,b){
  return a + b;
}

To create an array:
let newArray = [ ]; creates empty array
newArray[3] = “hello”;
newArray.push(newobject);
newArray.pop(objecttoremove)

Array.prototype.concat()
Returns a new array that is this array joined with other array(s) and/or value(s).
Array.prototype.includes()
Determines whether an array contains a certain element, returning true or falseas appropriate.
Array.prototype.indexOf()
Returns the first (least) index of an element within the array equal to the specified value, or -1 if none is found.
Array.prototype.join()
Joins all elements of an array into a string.
Array.prototype.slice()
Extracts a section of an array and returns a new array.
Array.prototype.keys()
Returns a new Array Iterator that contains the keys for each index in the array.

To push from one array to another:
newArray.push(oldArray[0];

To create a new array and copy info from 2 other arrays
let arrayA = [1, 2];
let arrayB = [3, 4];
Let newArray = arrayA.concat(arrayB);
The value of newArray will be [1, 2, 3, 4] (arrayA and arrayB remain unchanged; concat creates and returns a new array for the result).

A function for copying 
Array.prototype.pushArray = function() {
    Let toPush = this.concat.apply([], arguments);
    for (let i = 0, len = toPush.length; i < len; ++i) {
        this.push(toPush[i]);
    }
};


To use a for loop to add our names to an empty array. 
myArray = [“thomas”, “Noel”, “Faraz”, “Pia”, “Julie”]
emptyArray = []
for (let i = 0; i <= myArray.length; i++){
    emptyArray.push(myArray [i]);
}
console.log(emptyArray)

To create/construct new object
Let newObject = new Object(); constructor
newObject = {};  constructor shorthand
newObject.name = “Pia”
delete newObject.name deletes 

let person = {
	name: “Pia”
	details: {
	age: 26
	“favorite color” : “orange”
	}
}

person.name will print “Pia”
Person.details[“favorite color”] will print “orange”
person.details.age will print 26

datatypes
typeof("text") == "string"
    // true

typeof(3) == typeof(3.4) && typeof(0x34) == "number"
    // true

typeof(myArray) == "object" 
    // true (arrays are objects)

typeof(true) == "boolean"
    // true

typeof(Math.sin) == "function"
    // true

typeof(notThere) == "undefined"
    // true (can be useful)
 To compare:
123 == "123"                     
    // true (converts type)

123 === "123"                    
    // false (checks type)

typeof(x) == "undefined"     
    // true (x isn't there)
x == null            
    // x is not defined

Numbers:
parseInt("123")          parse tolkar den strint som kommer efter och returns a js object. I detta fall som en integer
    // base 10 => 123

parseInt("123", 16);         
    // base 16 => 291

parseFloat("123.43");        
    // 123.43

isNaN(0/0) == true       
    // illegal number

3/0 == Infinity          
    // true (Infinity is displayed when a number exceeds the upper limit of the floating point numbers, which is 1.797693134862315E+308)

-3/0 == -Infinity        
    // true (-Infinity is displayed when a number exceeds the lower limit of the floating point numbers, which is -1.797693134862316E+308)

isFinite(3/0) == true       
    // false (The isFinite() function determines whether a number is a finite, legal number. This function returns false if the value is +infinity, -infinity, or NaN (Not-a-Number), otherwise it returns true.)

REGULAR EXPRESSION (REGEX) STRING COMPARISONS
matches = "hello".match(
/h../

)   
    // returns array ["hel"] or null

myRegex = new RegExp("h..", "ig");    
    // construct regexp -- no slashes

matches = "hello".match(myRegex);     
    // use the regex

"hello".replace(
/h/

,"b")     
// => “bello"

Conditionals and loops 
if (string == "Hello"){    
  alert("Hi");       
}
else{
  alert("something is wrong!");
}
    // if-else popup dialog


a = 3, b = 4;       
    // multi-assigment

c = a > b ? a : b;  
    // c gets bigger item (b) (this is a ternary operator)


switch (name){      
  case "Thomas":
    alert("Hi Thomas!")
    break
  case "John":
    alert("Hi John.")
    break
  default: alert("Who are you?")
}
// switch statement


while (i <= n){ 
    console.log(i);        
    i++;
}
    // do something until a value (n) is reached
    // don't forget to have i++ or you will loop forever


for (let i=0; i<=n; i++){
    console.log(i);
}
    // another way to loop an n number of times


for (let key in person){
    console.log(key)
}
    // do something with person[key]

For statement/loops A for loop repeats until a specified condition evaluates to false. 
for ( [initialization]; [condition]; [final Expression]) {
ex. 
Let myArray = [“one”, “two”, “three”];
For(let i = 0; i < myArray.length; i++){
console.log(myArray[i]);
}
outputs: one, two, three (each on a new line)


do… while statement/loop
The do...while statement repeats until a specified condition evaluates to false. A do...while statement looks as follows:
do
  statement
while (condition);

Defining functions
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


<b>Javascript prototypes</b>
All JavaScript objects inherit the properties and methods from their prototype (Date, Array, RegExp, Function, ....).
We use .prototype to group methods together, not unlike a Ruby class.

JAVASCRIPT "CLASSES"
JavaScript doesn’t have formal class notation, but you can create a “constructor” and add methods to it. Examples from here.

example:
    function Person(first, last) { 
        // create "constructor"
        this.first = first;        
        // public variables -- reference current object
        this.last = last;

        let privateFn = function(first, last){  
        // private function
        }

        this.setName = function(first, last){ 
            // public function
            this.first = first;
            this.last = last;
        }
    }

    Person.prototype.fullName = function() { 
        // extend prototype
        return this.first + ' ' + this.last; 
        // even at runtime!
    }

    let bob = new Person("Anna", "Andersson"); 
        // "new" creates an object
    bob.fullName();               
        // "Thomas Ochman"

Explanation of "this" keyword: https://www.reddit.com/r/javascript/comments/6bffg4/understanding_the_this_keyword_in_javascript/
To find out what "this" is, look at when the this was invoked. According to implicit binding rule, the you use a function invoking this, look to the left of that function to see what "this" is referring to. 

IMPLICIT BINDING Below we've created the object stacey and a sayName method/function within that object.
```js
let stacey = {
    name: 'Stacey',
    age:34,
    sayName:  function(){
        console.log('My name is ' + this.name);
    }
};

stacey.sayName(); //this calls/invokes the sayName-function. 
``` 
EXPLICIT BINDING To call a function that isn't within the object, use the .call() 
example:
```js
sayName:  function(){
        console.log('My name is ' + this.name);
}

let stacey = {
    name: 'Stacey',
    age:34,
};

sayName.call(stacey);
``` 
With .call() you have to add in the arguments one by one (så om du hämtar från an array måste du skriva myArray[0], myArray[1] etc).
With .apply you pass in the arguments as an array (so it takes everything in your myArray). 
.bind returns a new function instead of invoking an already existing function like .call. 

Misc. info:

eval("x = 3");       // execute arbitrary code

timer = setTimeout("myfunction()", 1000)  
    // execute in 1 second (1000ms)

clearTimeout(timer);             
    // cancel event

JAVASCRIPT DEMO: 
To give a html node (like h1) an id you can access it in js. So in html <h1 id=“greeting”> “Hello” </h1> in script: Let greetingElement = document.getElementById(‘greeting’) . Now the h1 id is stored in a variable called greetingElement

<h1 id=“greeting”> “Hello” </h1> 
<button> Click me to change greeting </button>

<script>
Let myButton = document.querySelector(‘button’);
myButton.addEventListener(‘click’, changeGreeting); 

Function changeGreeting(name) {
Let greetingElement = document.getElementById(‘greeting’);
greetingElement.innerText = “Hello Pia“;
greetingElement.style.color = ‘red’;
greetingElement.style.fontSize = “40px”;
}
</script>

Om vänta med kod till sidan är färdig laddad:
Document.addEventListener(‘DOMContentLoaded’, () => {Koden som ska execute när de är laddat. 
}

 