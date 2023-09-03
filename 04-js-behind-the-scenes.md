# 4. How JS works behind the scenes
## An High-Level Overview of JavaScript
The scratch the surface definition: JS is a high-level, object-oriented, multi-paradigm programming language. 

But there is more about JS:
- High-level language. For low-level languages, such as C, you need to manually manage hardware resources, such as ask computer for memory to create a new variable. High-level languages, such s JS and Python, you do not need to manage resources at all. Because these languages have abstractions, that take all of that work away from the user. This makes the language easier to learn/use, but the programs will never be as fast/optimized as low-level languages. 
- Garbage-collected. One of the powerful tools that takes over memory management from us, which automatically removes old/unused objects from the memory. 
- Interpreted, or just-in-time compiles. Compiling/interpreting converts human-readable code to machine code (0s and 1s), and this happens to all programming languages. For JS, this happens inside the JS engine. 
- Multi-paradigm. A paradigm is an approach/mindset of structuring code, which will direct your coding style/technique. Three popular paradigms are: procedural, object-oriented, and functional programming. Procedural programming: What we've been doing so far, just organizing the code in a very linear way, with some functions in-between. Many languages are only procedural, or only object-oriented, or only functional, but JS does all of it. 
- Prototype-based object-oriented. Almost everything in JS is an object, except for primitive values, such as numbers, strings, etc. A JS array is an Prototype, which is an object instance. The arrays we create in our code inherit the methods from the blueprint. 
- First-class functions. Functions are treated just as regular variables. You can pass functions into other functions, and return functions from functions. This allows for functional programming. Not all languages have first-class functions. 
- Dynamically-typed. We don't assign datatypes to variables. They types only became known when the JS engine executes the code. Also, the type of variables can easily be changes as we re-assign variables. Most other programming languages do not have this. If you want to use JS with types, you can look into TypeScript. 
- Single-threaded. JS runs in one single thread, so it can only do one thing at a time. 
- Non-blocking event loop. Takes long-running tasks, executes them in the background, and puts them back in the main thread, once they are finished. 

## The JavaScript Engine and Runtime
The JS engine is a program that executes JS code. Every browser has its own JS engine. The most we known engine is Google's V8, which powers Google Chrome, but also Node.js, the JS runtime to build server side applications with JS, outside of any browser. 

Any JS engine always contains:
1. A call stack. Is where our code is executed, using execution contexts. 
2. A heap. An unstructured memory pool, which stores all the objects the code needs

In `compilation`, the entire source code is converted into machine code at once. This machine code is then written into a portable file, that can be executed on any computer. The execution can happen any long time after the compilation. 

In `interpretation`, there is an interpreter, that runs through the source code, and executes it line by line. There is no "two step process" like in the compilation. Here, the source code still needs to be converted into machine code, but it simply happens right before it's executed, and not ahead of time. 

JS used to be a purely interpreted language, but since interpreted languages are much slower than compiled languages, this low performance no longer works in modern fully fledged web applications. So modern JS engine now use a mix between compilation and interpretation, which is called "Just-in-time" compilation. 

This "Just-in-time compilation" compiles the entire code into machine code at once, and then executes it right away. 

When a piece of JS code enters the engine, the following steps happen:
1. Parsing. The code is parsed into a data structure, called the Abstract Syntax Tree (AST). This works by splitting up each line of code into pieces that are meaningful to the language, then saving those pieces into a tree in a structured way. This step also checks for syntax errors. 
2. Compilation. Takes the generated AST from prev step, and compile it into machine code. 
3. Execution. The machine code from the prev step goe executed right away. 
4. Optimization. Note that the compilation creates a very un-optimized code in the beginning, so it can start executing ASAP. Then in the background, the code is being optimized and re-compiled, when the machine code is executing. This process can be done multiple times, and after each optimization, the prv machine code will be replaced with the newer version, without stopping the execution. 

This process is what makes modern engines, such as V8, so fast. This parsing/compilation/optimization happens in some special threads inside the engine, that is in-accessible from the call stack of the execution. 

JS runtime can be compared to a big box, which includes all the things that we need to use JS, for example, in the browser. 
- JS engine. The heart of any JS runtime is always a JS engine. 
- Web APIs access. Having the engine alone is not enough. We also need access to the web APIs (everything related to the DOM, timers, console.log(...)), which are functionalities provided to the JS engine, but not part of the JS language. JS gets access to these APIs through the global window object. 
- Callback queue. A data structure that contains all the callback functions, that are ready to be executed. Such as, the callback function from the DOM event listener, for a button. When an event happens, the callback function will be called. It will first be put into the callback queue, then when the stack is empty, the callback function is passed to the stack, by event loop, so it can be executed. 

Out of the browser, then JS in running in Node.js, the Web APIs in the above structure is replaced by C++ bindings and thread pool. 

## Execution Contexts and The Call Stack

## Scope and The Scope Chain

## Scoping in Practice

## Variable Environment: Hoisting and The TDZ

## Hoisting and TDZ in Practice

## The this Keyword

## The this Keyword in Practice

## Regular Functions vs. Arrow Functions

## Primitives vs. Objects (Primitive vs. Reference Types)

## Primitives vs. Objects in Practice






































