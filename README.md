Q. What is JavaScript
A: JavaScript is a high level, object oriented, multi-paradigm, programming language.
A: JavaScript is a High level, prototype based object oriented, multi-paradigm, interpreted or Just In Time Compiled, dynamic, single-threaded, garbage collected programming language with first-class functions and a non-blocking event loop concurrency model.


Low Level Languages: Developer has to manage resources manually. Faster Than High Level Languages.


High Level Languages: Developers don't manage resources manually, its automated. Slower than Low Level Languages.


JS can follow Procedural programming, Object oriented programming, and functional programming.
JS can follow both imperative and declarative paradigm.


First Class Functions => functions are treated as variables.


JavaScript is single Threaded => JavaScript runs in one single thread, so it can do one thing at a time.
In case of long running tasks, in order to achieve non-blocking behaviour, JavaScript engine uses an event loop, executing the long tasks in the "background", and puts them back in the main thread once they are finished.


Compilation: Entire code is converted into machine code and written to a binary file, and then executed.

Interpretation: Line by line execution of the code.

Just In Time(JIT) Compilation: Entire code is converted into machine code at once, then executed immediately.
Code --> Parsing --> Compilation --> Execution --> Optimization --> Compilation --> Execution -->... JS engine creates an unoptimized version of machine code and executes immediately, at the same time keeps optimizing the machine code and replaces the current code with better optimized versions of the code making it extremely fast.


JS Runtime In The Browser
1. Heap - JS Engine
2. Call Stack - JS Engine
3. Web Apis -> DOM, Timers, Fetch APIs, etc.
4. Callback Queue -> onClick, timer, data, etc.
5. Event Loop.

JS Runtime In Node.js
1. Heap - JS Engine
2. Call Stack - JS Engine
3. Libuv (C++ Bindings & Thread Pool)
4. Callback Queue -> onClick, timer, data, etc.
5. Event Loop.


Execution
1. Creation of global execution context(for top level code (code that is not inside a function)). Exactly one gloabl execution context.
2. Execution of top level code inside global execution context.
3. Execution of functions and waiting for callbacks. one execution context per function.


Inside Execution Context - Generated during creation phase - right before  execution
1. Variable Environment - values inside the context eg. let, const, functions, argument objects etc.
2. Scope change
3. this keyword
Arrow Functions dont have their own this keyword and argument objects and they inherit it from their parent.


this keyword:
1. created for every execution context.
2. this is NOT static.


In JS every value is either an object or a primitive value.

7 Data Types In JS
1. Number
2. String
3. Boolean
4. Undefined
5. Null
6. Symbol
7. BigInt (ES2020)


JS has dynamic typing => Data types are determined automatically.


let is block scoped, var is function scoped. Avoid using var, use const as default and let when the value of the variable may change after initialisation.


Falsy Values are values that on conversion to boolean will return false
JS has 5 falsy Values: 0, '', undefined, null, NaN
Rest of the values are truthy values -> on conversion to boolean will return true

== while comparing does type  coercion, while === doesn't. Avoid using ==, always use ===


Expression is a piece of code that produces some value

Statements are complete lines of code that doesn't produce value and translate to actions in a program--> Expressions are generally a part of statements.


JS is Backwards Compatible, not forwards compatible

In JS, functions are just values which can be stored in variables

function declaration can be accessed from a line even before its declaration where as function expression can only be called after its declaration.

function declaration
function calcAge(){}

function expression
const calcAge = function(){}
const calcAge = () => {}


Everything in JS is a value and nearly everything in JS is an object other than the 7 data types — null , undefined , strings, numbers, boolean, symbols and BigInt (These are primitive values or primitive data types).

DOM: Document Object Model is a structured representation of HTML documents. It allows JavaScript to access HTML elements and styles to manipulate them.

DOM Methods and Properties are not part of JS language. They are part of Web Apis which interact with JS.

The Spread Operator(...) takes all elements from the array and also doesn't create new variables, hence we can only use it where we would otherwise write values separated by commas.
Helps creating shallow copies of an array.
// Copy Array
const newArray = [...originalArray];
// Join 2 Arrays
const newArray = [...array1, ...array2];

Spread operator only works with iterables.
Iterables: arrays, strings, maps, sets
Non-Iterables: objects

Spread operator was introduced in es6.
From es2018, spread operator also works on objects even though they are not iterables.
// Creating A new object using key value pairs of the old object while adding new key value pairs
const newObject = {...originalObject, founder: Abhi, date:'2022'};

//Creating A Shallow Copy Of An Object
const newObject = {...originalObject};

Accessing Key Value Pairs In An Object
// 1) for...in
var user = {
    name : "John",
    age  : 25
}
for(const property in user) {
    console.log(`user[${property}] = ${user[property]}`);
}
//output
user[name] = John
user[age]  = 25

// 2) for...of
var user = {
    name : "John",
    age  : 25
}
let entries = Object.entries(user);
for(const [prop, val] of entries) {
    console.log(prop, val);
}

// 3) map
var user = {
    name : "John",
    age  : 25
}
let entries = Object.entries(user);
entries.map( ([prop, val]) => console.log(prop, val));

// 4) forEach
var user = {
    name : "John",
    age  : 25
}
let entries = Object.entries(user);
entries.forEach( ([prop, val]) => console.log(prop, val));

// 5) Another way
const entries = Object.entries(originalObject);

for(const[key, value] of entries){
    console.log(key, value);
}

// 6) Accessing Only Values In An Object
const values = Object.values(originalObject);
console.log(values)


// SPREAD, because on right side of =
const arr = [1, 2, ...[3,4]];
console.log(arr) --> [1, 2, 3, 4]

// REST(rest operator), because on left side of =
const [a, b, ...others] = [1, 2, 3, 4, 5];
console.log(a, b, others) --> 1 2 [3, 4, 5]

Rest operator does not include skipped elements.
const arr = [1, 2, 3, 4, 5];
const [a, , b, ...newArray] = arr;
console.log(a, b, newArray) --> 1 3 [4,5]

There can only be one rest operator in any destructuring assignment.

Rest operator also works with objects and functions.
// Example of Rest Operator In Use
const add = function(...numbers){
    let sum = 0;
    for(let num of numbers){
        sum += num;
    }
    return sum;
}
add(2, 3);
add(2, 3, 4, 5);
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
add(...arr);


Logical Operators can use any data type, return any data type in JavaScript.
They perform Short Circuit Evaluation

ShortCircuiting: If the first value is a truthy value, it will immediately return the first value without even checking the second value
// If any one is truthy -> return truthy value
console.log(3 || 'Abhi') --> 3
console.log('' || 'Abhi') --> Abhi
console.log(true || 0) --> true
console.log(undefined || null) --> null

// If any one is falsy --> return falsy value
console.log(0 && 'Abhi') --> 0
console.log(7 && 'Abhi') --> Abhi (In case of both value being truthy, return the last truthy value)

Nullish: null and undefined (not 0 or '')
const newNumber = restaurant.numGuests ?? 10;
//if restaurant.numGuests is not nullish then the value will be assigned to newNumber else 10;

rest1.numGuests ||=10;
rest2.numGuests ||=10;
//if rest1.numGuests and rest2.numGuests are falsy then 10 will be assigned to them else their value will remain --> es21 feature

rest1.numGuests &&=10;
rest2.numGuests &&=10;
//if rest1.numGuests and rest2.numGuests are truthy then 10 will be assigned to them else their value will remain falsy --> es21 feature

rest1.numGuests ??=10;
rest2.numGuests ??=10;
//if rest1.numGuests and rest2.numGuests are nullish(only null or undefined) then 10 will be assigned to them else their value will remain --> es21 feature

Optional Chaining (es2020): if a certain property doesn't exist then undefined is returned immediately.
console.log(restaurant.openingHours.mon?.open);
//if .mon exists in the object restaurant then .open value will be returned else, undefined will be returned.


JavaScript has built in Data Structures for Sets and Maps.

Creating an array of unique values with Sets

const newArray = [...new Set(originalArray)];

// Iteration over sets
for(const num of sets){
    console.log(num);
}

Creating Map from an Object
const hoursMap = new Map(Object.entries(openingHours));

Iteration Over Maps
for(const [key, value] of question){
    console.log(key, value);
}

Both Sets and Maps don't store duplicate keys.



Default Parameters(es6)
const createBooking = function(flightNum, numPassengers = 1, price = 199 * numPassengers){
    .....
}



Replace spaces in a string
const oneWord = function(str){
    return str.replace(/ /g,'');
}

function returning function
const greet = function(greeting){
    return function(name){
        console.log(`${greeting} ${name}`);
    };
};

const greetHey = greet('Hey');
greetHey('Abhi');
// Output --> Hey Abhi

greet('hello')('Abhi');
// Output --> Hey Abhi


Immediately Invoked Function Expression
(function(){
    console.log('This will only run once');
})();
(() => console.log('This will only run once'))();


Closures:
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

// Example Of Closures
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() {
    // displayName() is the inner function, a closure
    console.log(name); // use variable declared in the parent function
  }
  displayName();
}
init();

// Explanation Of The Code Above
init() creates a local variable called name and a function called displayName(). The displayName() function is an inner function that is defined inside init() and is available only within the body of the init() function. Note that the displayName() function has no local variables of its own. However, since inner functions have access to the variables of outer functions, displayName() can access the variable name declared in the parent function, init().



