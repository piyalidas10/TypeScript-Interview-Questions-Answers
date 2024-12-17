# TypeScript-Interview-Questions-Answers

#### Typescript vs Javascript




| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   |  Does Typescript run in the browser ? <br><br> TypeScript cannot be run or understood in any browser. So, TypeScript is compiled to JavaScript (which browsers can understand) using TSC(TypeScript) compiler. To install TSC compoiler, we have to install Node.js as we need NPM.
| 2   |  What is TypeScript? <br><br> TypeScript is a statically typed language and a superset of JavaScript that builds on top of JavaScript’s existing syntax and functionality. This means that you can use JavaScript in your TypeScript code, but you can't use TypeScript in your JavaScript code as code written in TypeScript uses features and syntax not present in JavaScript. TypeScript must be compiled (transpiled is another term as it isn’t converting to a low-level language) to JavaScript to run in web browsers and in environments like Node.js. The file extension for TypeScript is .ts. 
| 3   |  Undefined vs Null ? <br><br> Undefined means the variable is written there but there is no existence of it in the memory. Undefined is a data type. `let a: number; console.log(a); console.log(typeof a);` <br> Null is a value whose type is Object. `let a = null; console.log(a); console.log(typeof a);` 
| 4   |  What is template literals or Template strings? <br><br> Template literals, also known as template strings, are a feature in JavaScript that allow for easier string interpolation and multi-line strings. They are denoted by backticks (`) instead of single or double quotes. <br/><br/> 1) Display variable value without using concatenation `let a = 90; let str = 'value of a is ${a}'; console.log(str); ` <br/> 2) The way you write string inside, it will appear as it is. `let str = 'one          two         three'; console.log(str); `
