

JavaScript is a dynamic, interpreted language that has become a foundation of modern web development. Its presence across web browsers is due to its flexibility and ease of use, but this also introduces complexity in its behavior.


### **Key Characteristics of JavaScript:**



1. **Dynamic Typing and Equality Comparisons**: JavaScript is known for its dynamic type system. This flexibility allows for operations like `'2' == 2` to return `true`, showcasing its type coercion capabilities. While this makes JavaScript very accessible and forgiving for beginners, it can lead to subtle bugs and unpredictable behavior, especially when comparing different data types.
2. **Browser-Specific Behavior**: JavaScript's behavior can vary slightly across different web browsers. Each browser has its own JavaScript engine, which may interpret certain aspects of the language differently. This inconsistency requires additional efforts in cross-browser compatibility.


### **JavaScript Engines and Their Impact:**



* **V8 Engine (Google)**: Powers Google Chrome and is known for its performance and efficiency. It's widely regarded as a benchmark in JavaScript engine technology.
* **SpiderMonkey (Mozilla Firefox)**: Notably includes some parts written in Rust, which is known for its safety and performance.
* **JavaScriptCore (Safari)**: Integral to the macOS ecosystem, ensuring optimized performance for Apple's devices.
* **Microsoft's Adoption of V8**: Microsoft shifted to the V8 engine for its Edge browser, indicating a consolidation around some of the more efficient and widely-used engines in the market.

Almost all JavaScript engines are primarily written in C++ or C, with SpiderMonkey incorporating Rust for certain components. This choice of languages is due to the need for high performance and efficient memory management, which are critical for web browsers that handle complex web applications.


### **JavaScript Architecture**

JavaScript's single-threaded nature and its ability to handle asynchronous operations are foundational aspects of the language, crucial for understanding how it executes code, in a web browser environment and node environment.


### **Single-Threaded Nature of JavaScript**

Being single-threaded means JavaScript can execute only one command at a time in a single sequence. This might seem limiting, but it simplifies the programming model since developers don't have to deal with complexities like thread management or synchronization issues common in multi-threaded languages. However, this could lead to performance bottlenecks, particularly if a long-running task blocks the thread.


### **Asynchronous Nature of JavaScript**

To mitigate the limitations of single-threaded execution, JavaScript uses an event-driven, non-blocking model. Asynchronous operations allow JavaScript to perform long-running tasks (like I/O operations) without blocking the main thread. These tasks are offloaded, and their callbacks are executed once the task is complete, without interrupting the ongoing operations.


### **Dual nature of JavaScript **

JavaScript is often categorized as an interpreted language because historically, it was executed directly by an interpreter in the browser without a separate compilation step. However, modern JavaScript engines use JIT compilation, which blurs the line between interpreted and compiled languages. This evolution is due to the need for improved performance in increasingly complex web applications.

JavaScript is indeed both interpreted and compiled, depending on the context:



* **Interpreted**: When JavaScript code is executed without optimization, particularly for code that runs infrequently.
* **Compiled**: When the JIT compiler kicks in to optimize "hot" code for better performance.

This dual nature allows JavaScript engines to provide both the quick start-up time of an interpreted language and the high performance of a compiled language. It adapts to the execution patterns of the code, providing optimal performance without a lengthy initial compilation.


### **Interpreted (Without JIT Compilation)**



1. **Parsing**: The source code is parsed into an Abstract Syntax Tree (AST), which represents the code structure hierarchically.
2. **Interpretation**: An interpreter runs through the AST or byte-code (an intermediate code) and executes the instructions directly. It translates each high-level instruction into machine code one by one and executes them in sequence.
3. **Execution**: The results of execution are returned as the interpreter processes the code.

This process happens every time the script runs, which can be less efficient because repeating the same instructions results in the same translation process each time.


### **JIT Compilation**



1. **Parsing**: Just like with interpretation, the source code is parsed into an AST.
2. **Baseline Compilation**: The code is quickly compiled to a less optimized machine code to start execution as soon as possible.
3. **Execution and Profiling**: The code runs, and the engine monitors (profiles) it to identify hot spots—code that's executed frequently.
4. **Optimization**: The hot spots are re-compiled by a more sophisticated JIT compiler into highly optimized machine code. This step may occur multiple times, with de-optimizations if assumptions about the code prove incorrect.
5. **Execution of Optimized Code**: The optimized machine code is executed, which is much faster than both the baseline compiled code and interpreted code.

The difference between the two processes is that JIT compilation involves an additional step of converting code into optimized machine code, which is executed directly by the CPU. This step can significantly improve performance, especially for code that runs repeatedly, because the optimized machine code runs faster than interpreting the same instructions over and over again.


### **JavaScript Runtime Components**

To understand this better, let's look at the main components of the JavaScript runtime:



1. **Call Stack**: Where the JavaScript runtime keeps track of function calls. Each new call is added to the stack, and removed once the function execution is complete.
2. **Event Loop**: Monitors the call stack and the callback queue. If the call stack is empty, the event loop moves the first event from the callback queue to the call stack.
3. **Callback Queue**: A waiting area for callbacks from asynchronous operations. When an asynchronous operation completes, its callback enters this queue.
4. **Render Queue**: Similar to the callback queue but specifically for rendering-related callbacks. It ensures smooth UI rendering by prioritizing rendering tasks.

Babel and polyfills play significant roles in the ecosystem of JavaScript, particularly concerning ECMAScript, which is the standard that defines the JavaScript language. ECMAScript versions are denoted by the year of their release (for example, ECMAScript 2015 is also known as ES6).


### **ECMAScript Versions**

ECMAScript versions are iterations of the language standard that include new features and syntax improvements. For instance, ES6 introduced arrow functions, classes, and promises, which were not available in ES5.


### **Babel**

Babel is a JavaScript compiler that allows developers to write code using the latest JavaScript features without worrying about whether or not they are supported in all browsers. Here's how it works:



* **Transpilation**: Babel takes modern JavaScript code (like ES6 or later) and transpiles it into equivalent code that is compatible with older JavaScript versions (like ES5), which is widely supported across browsers.
* **Syntax Transformations**: Babel can transform new syntax that is not understood by older JavaScript engines into a syntax that is understood.
* **Source Code Transformation**: Babel also allows for the transformation of source code to implement custom features or experimental language features before they are standardized in ECMAScript.


### **Polyfills**

Polyfills are pieces of code (or plugins) used to provide modern functionality on older browsers that do not natively support it. Here's their role:



* **Environment Emulation**: They emulate the environment required for new features to run as if they were natively supported.
* **Feature Implementation**: For example, if a browser does not support ES6 Promises, a polyfill can be added to the codebase that implements the Promise functionality, allowing developers to use Promises regardless of browser support.

In summary, Babel and polyfills are tools that bridge the gap between the new features of the ECMAScript language and the need for backward compatibility. They enable developers to use the latest features without sacrificing support for users on older browsers, ensuring a consistent experience across the web.


### **Javascript Syntax Overview: Code snippets to understand key concepts**

**Exploring Data Types**


```
// Number type
let num = 42;
// Boolean type
let bool = true;
// String type
let string = "Hello, world!";
// null type
let nothing = null;
// Undefined type
let undef;
// Array type
let array = [1, 2, 3];
// Object type
let object = { key: "value" };
// Symbol type
//Symbols in JavaScript ensure 
//unique object property keys,
// preventing conflicts with other properties and maintaining data privacy.
let sym = Symbol("uniqueIdentifier");
// BigInt type, Available in ES2020 or later
let bigNumber = BigInt(9007199254740991); // Or 9007199254740991n
```


**console.log output for above variables.**


```
Number: 42
Boolean: true
String: Hello, world!
null: null
Undefined: undefined
Array: [ 1, 2, 3 ]
Object: { key: 'value' }
Symbol: Symbol(uniqueIdentifier)
BigInt: 9007199254740991n
```


**Variable Scoping: Global, Function, and Block scope**


```
// Global scope
var globalVar = "Accessible everywhere";
let globalLet = "Also accessible everywhere";
const globalConst = "Also accessible everywhere, but immutable";

function testFunction() {
  // Function scope
  var functionVar = "Accessible in this function";
  let functionLet = "Also accessible in this function";
  const functionConst = "Immutable and accessible in this function";
  globalThis.myGlobalVar = "Hello, global scope!";
  console.log(globalVar); // Works
  console.log(globalLet); // Works
  console.log(globalConst); // Works
}

testFunction();
console.log(functionVar); // Error: functionVar is not defined
console.log(functionLet); // Error: functionLet is not defined
console.log(functionConst); // Error: functionConst is not defined
console.log(myGlobalVar); // Outputs: "Hello, global scope!"

if (true) {
  // Block scope
  var blockVar = "Accessible outside this block";
  let blockLet = "Accessible only in this block";
  const blockConst = "Immutable and only accessible in this block";
}

console.log(blockVar); // Works, var is not block-scoped
console.log(blockLet); // Error: blockLet is not defined
console.log(blockConst); // Error: blockConst is not defined
```


**Understanding Operator precedence and Falsy values**


```
function evaluateLogicalExpressions(a, b, c) {
  // All falsy values in JavaScript: false, 0, -0, 0n, "", null, undefined, NaN
  // Logical '!' has the highest precedence, followed by '&&', and then '||'
  let result = a || !b && c; // '!b' will be evaluated first, then 'b && c', and finally 'a ||'
  console.log(`The expression 'a || !b && c' evaluates to: ${result}`);
  // Equivalent explicit grouping to show precedence
  let explicitResult = a || (!b && c); // Demonstrates that '!b' is evaluated first
  console.log(`With explicit grouping 'a || (!b && c)': ${explicitResult}`);
  // Left-to-right evaluation with mixed logical operators and '!'
  // '!a' is evaluated first, then 'a && b', and finally '|| c'
  if (!a && b || c) {
    console.log('At least one of the following is true: a is falsy and b is truthy, or c is truthy.');
  } else {
    console.log('Neither a is falsy and b is truthy, nor is c truthy.');
  }
}
// Examples with various falsy values
evaluateLogicalExpressions(0, 'Hello', ''); // '' is falsy, 'Hello' is truthy after being negated
evaluateLogicalExpressions(null, null, NaN); // null and NaN are falsy
```


**Handling Promises**


```
// A function that returns a Promise, consider it a long running blocking task.
function checkNumber(num) {
  return new Promise((resolve, reject) => {
    if (num < 10) {
      resolve('The number is less than 10.');
    } else {
      reject('The number is 10 or greater.');
    }
  });
}
// Using then and catch to handle the Promise
checkNumber(8)
  .then((message) => {
    console.log('Success:', message);
  })
  .catch((error) => {
    console.log('Error:', error);
  });
// Using async/await to handle the Promise
async function processNumber(num) {
  try {
    const message = await checkNumber(num);
    console.log('Success:', message);
  } catch (error) {
    console.log('Error:', error, error.stack);
  }
}
// Call the async function
processNumber(12);
```


**Explicit and Implicit Boolean conversion**


```
let value = 1;
// Using the Boolean constructor to explicitly convert 'value' to a boolean
if (Boolean(value)) {
    // This block will execute because 'value' is 1, which is a truthy value in JavaScript.
    // Truthy values include all numbers (except 0 and -0), all strings (except the empty string ""), and all objects.
} else {
    // This block will not execute since 'value' is truthy.
}
// Using the double NOT operator (!!value) to implicitly convert 'value' to a boolean
if (!!value) {
    // This block will execute for the same reason as above.
    // The first '!' negates 'value', turning a truthy into a falsy or vice versa.
    // The second '!' negates it again, effectively converting 'value' to its boolean equivalent.
} else {
    // This block will not execute since 'value' is truthy.
}
```


**Understanding Type Comparision and Type Checking: “==vs===”,”typeof” and “instanceof”**


```
// == vs ===
console.log(null == undefined); // true because null and undefined are considered equal in non-strict comparison
console.log(null === undefined); // false because they are of different types
console.log('1' == 1); // true because string '1' is converted to number 1 before comparison
console.log('1' === 1); // false because the types are different
// typeof usage
console.log(typeof 1); // "number"
console.log(typeof 'string'); // "string"
console.log(typeof true); // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null); // "object" - this is a known JavaScript bug, null is not actually an object
// instanceof usage
class MyClass {}
const instance = new MyClass();
console.log(instance instanceof MyClass); // true because 'instance' is an instance of MyClass
```


**Basic Control Structures and Array Methods: Conditional Statements, Loops and Functions**


```
// if-else
let condition = true;
if (condition) {
  console.log('Condition is true');
} else {
  console.log('Condition is false');
}
// for loop
for (let i = 0; i < 3; i++) {
  console.log(`For loop iteration: ${i}`);
}
// while loop
let j = 0;
while (j < 3) {
  console.log(`While loop iteration: ${j}`);
  j++;
}
// forEach loop
[1, 2, 3].forEach((item) => {
  console.log(`ForEach item: ${item}`);
});
// map
let doubled = [1, 2, 3].map((item) => item * 2);
console.log(`Doubled array: ${doubled}`);
// reduce
let sum = [1, 2, 3].reduce((accumulator, current) => accumulator + current, 0);
console.log(`Sum of array: ${sum}`);
// switch statement
let switchCase = 'a';
switch (switchCase) {
  case 'a':
    console.log('Case A');
    break;
  case 'b':
    console.log('Case B');
    break;
  default:
    console.log('Default case');
}
// function with return
function add(a, b) {
  return a + b;
}
let additionResult = add(1, 2);
console.log(`Function return: ${additionResult}`);
```


**Switching on True**


```
let number = 10;
switch (true) {
    case (number <= 10):
        console.log("Condition A met.");
        break;
    case (number <= 20):
        console.log("Condition B met.");
        break;
    case (number <= 30):
        console.log("Condition C met.");
        break;
    case (number > 30):
        console.log("Condition D met.");
        break;
    default:
        console.log("No conditions met.");
}
```


**Utilizing Inheritence and Encapsulation: Implementing classes with Getters , Setters and Private Fields**


```
class Animal {
  constructor(name) {
    this._name = name; // Using _ convention to denote a property that should be accessed via getter/setter
  }
  get name() {
    return this._name;
  }
  set name(newName) {
    this._name = newName;
  }
  static info() {
    console.log('Animals are living beings.');
  }
  speak() {
    console.log(`${this._name} makes a noise.`);
  }
}
class Dog extends Animal {
  #privateField;
   constructor(name, privateField) {
     super(name);
     this.#privateField = privateField;
   }
   revealSecret(){
   console.log(`${this.name} secret is ${this.#privateField}`);   
}
  speak() {
    console.log(`${this._name} barks.`);
  }
}
let dog = new Dog('Rex');
dog.speak(); // Rex barks.
// Accessing static method
Animal.info(); // Animals are living beings.
// Using getter and setter
console.log(dog.name); // Rex
dog.name = 'Max';
console.log(dog.name); // Max
```


**Implementing and handling custom Errors**


```
// Defining a custom error class
class CustomError extends Error {
  constructor(message) {
    super(message); // Call the parent class constructor with the message
    this.name = this.constructor.name; // Set the error name to the name of the class
    this.customProperty = 'Custom error details'; // Custom properties can be added
  }
}
// Function that throws a custom error
function doSomethingRisky() {
  throw new CustomError('Something went wrong!');
}
// Error handling with try...catch
try {
  doSomethingRisky();
} catch (error) {
  if (error instanceof CustomError) {
    console.error(`Caught a custom error: ${error.message}`);
  } else {
    console.error(`Caught an unexpected error: ${error.message}`);
  }
} finally {
  console.log('This code runs whether or not an error occurred.');
}
```


**JavaScript Object Example**


```
let person = {
    name: 'Alice',
    age: 30,
    salary: 50000,
    purpose: 'Developer',
    awake: true,
    greet() {
        console.log(`Hello ${this.name}`);
    }
};
person.greet(); // Outputs: Hello Alice
```


**Understanding `this` in different JavaScript Contexts**


```
// Global context
console.log(this === window); // true in browsers
// Function context in non-strict mode
function nonStrictFunction() {
  console.log(this === window); // true in browsers
}
nonStrictFunction();
// Function context in strict mode
function strictFunction() {
  'use strict';
  console.log(this === undefined); // true
}
strictFunction();
// Arrow function context
const arrowFunction = () => {
  console.log(this); // Lexical `this` based on where the arrow function is defined
};
arrowFunction();
// Object method context
const person = {
  name: 'Alice',
  greet() {
    console.log(this === person); // true
  }
};
person.greet();
// Event handler context (uncomment in browser to test)
// document.getElementById('myElement').addEventListener('click', function() {
//   console.log(this === document.getElementById('myElement')); // true
// });
// Explicitly setting `this` with call, apply, and bind
function greet(message) {
  console.log(`${message}, ${this.name}`);
}
const user = {
  name: 'Bob'
};
// Using call
greet.call(user, 'Hello'); // Hello, Bob
// Using apply
greet.apply(user, ['Greetings']); // Greetings, Bob
// Using bind
const boundGreet = greet.bind(user);
boundGreet('Welcome'); // Welcome, Bob
```


**JavaScript’s Advanced DataStructures: Map,Set,WeakMap and WeakSet**


```

// Set - stores unique values of any type
const uniqueNumbers = new Set([1, 2, 3, 3, 4]);
uniqueNumbers.add(5); // Adding a new unique value
console.log([...uniqueNumbers]); // Output: [1, 2, 3, 4, 5]
// Map - stores key-value pairs with keys of any type
const userRoles = new Map();
userRoles.set('John', 'admin');
userRoles.set('Jane', 'editor');
console.log(userRoles.get('John')); // Output: 'admin'
// WeakMap - key-value pairs where keys are objects and are weakly referenced
let obj = {};
const weakMap = new WeakMap();
weakMap.set(obj, { key: 'someValue' });
obj = null; // Allows key 'obj' to be garbage-collected if no other references exist
// WeakSet - a set of objects that are weakly referenced
let obj1 = {};
let obj2 = {};
const weakSet = new WeakSet([obj1, obj2]);
obj1 = null; // Allows 'obj1' to be garbage-collected if no other references exist
```

