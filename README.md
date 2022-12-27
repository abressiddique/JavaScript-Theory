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