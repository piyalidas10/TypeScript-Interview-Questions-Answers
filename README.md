# TypeScript-Interview-Questions-Answers

#### Advantages of Typescript over Javascript
https://www.totaltypescript.com/tsconfig-cheat-sheet



| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   |  Does Typescript run in the browser ? <br><br> TypeScript cannot be run or understood in any browser. So, TypeScript is compiled to JavaScript (which browsers can understand) using TSC(TypeScript) compiler. To install TSC compoiler, we have to install Node.js as we need NPM.
| 2   |  What is TypeScript? <br><br> TypeScript is a statically typed language and a superset of JavaScript that builds on top of JavaScript’s existing syntax and functionality. This means that you can use JavaScript in your TypeScript code, but you can't use TypeScript in your JavaScript code as code written in TypeScript uses features and syntax not present in JavaScript. TypeScript must be compiled (transpiled is another term as it isn’t converting to a low-level language) to JavaScript to run in web browsers and in environments like Node.js. The file extension for TypeScript is .ts. 
| 3   |  Undefined vs Null ? <br><br> Undefined means the variable is written there but there is no existence of it in the memory. Undefined is a data type. `let a: number; console.log(a); console.log(typeof a);` <br> Null is a value whose type is Object. `let a = null; console.log(a); console.log(typeof a);` 
| 4   |  What is template literals or Template strings? <br><br> Template literals, also known as template strings, are a feature in JavaScript that allow for easier string interpolation and multi-line strings. They are denoted by backticks instead of single or double quotes. <br/><br/> 1) Display variable value without using concatenation `let a = 90; let str = 'value of a is ${a}'; console.log(str);` <br/> 2) The way you write string inside, it will appear as it is. `let str = 'one          two         three'; console.log(str);`
| 5   |  What is a type alias in TypeScript? <br><br> Type aliases in TypeScript allow you to create custom names for complex types, making your code more readable and maintainable. They are particularly useful when dealing with complex data structures, union types, and other scenarios where you want to give a clear name to a specific type. https://www.freecodecamp.org/news/how-typescript-type-aliases-work/
| 6   |  What is an union type in TypeScript? <br><br> A union type describes a value that can be one of several types. We use the vertical bar ( | ) to separate each type, so number | string | boolean is the type of a value that can be a number , a string , or a boolean . `type pincode = number | string; function printStatusCode(code: string | number) {};`
| 7   |  What is never type TypeScript? <br><br> never type represents the type of values that never occur. <strong>Never</strong> means This function will not complete till the last line and before the finish it breaks so it will never return a value. Here you may have a question that when the function is not returning anything, then why don't we use Void as a return type? Well, because there is a difference. <strong>Generally a function not returning anything can be defined as void, but still returns undefined. But if you have never data type, it will give a compile time error. </strong> let see the code `let x: void = undefined; let y: never = undefined;` you will get error on never type "Type 'undefined' is not assignable to type 'never'." <br/> https://www.typescriptlang.org/docs/handbook/basic-types.html#:~:text=The%20never%20type%20represents%20the,that%20can%20never%20be%20true.
| 8   |  Never vs Void ? <br><br> The difference between never and void that you can assign null or undefined to void type, but you cannot do the same with never type. `let x: void = undefined; let y: never = undefined;` you will get error on never type <strong>"Type 'undefined' is not assignable to type 'never'."</strong>
| 9   |  Use of module in tsconfig.json ? <br><br> Using module option, TypeScript docs describe the module compiler option by which TSC compile typescript file to JavaScript. Specify module code generation: "None", "CommonJS", "AMD", "System", "UMD", "ES6", "ES2015" or "ESNext". <br/><br/>  1) "module": "commonjs" is basically used when you want to generate the nodejs related coding. When your typescript code is going to be used with node JS, then Commonjs is the module loader. 2) "module": "ES2020" is modern javascript, export statement will work directly. <br/> https://www.tsmean.com/articles/learn-typescript/typescript-module-compiler-option/
| 10   |  Use of lib in tsconfig.json ? <br><br> lib option tells TypeScript what built-in types to include. lib option is being included in an array. <strong>es2022</strong> is the best option for stability. <strong>dom and dom.iterable</strong> give you types for window, document etc. <br/> https://www.typescriptlang.org/tsconfig/#lib
| 10   |  Use of noEmit in tsconfig.json ? <br><br> Tells TypeScript not to emit any files. This is important when you're using a bundler so you don't emit useless .js files.
| 11   |  What is strict type checking? <br><br> Strict type checking means the function prototype(function signature) must be known for each function that is called and the called function must match the function prototype. It is done at compile time. <br/> `{ "compilerOptions": { "strict": true, "noUncheckedIndexedAccess": true, "noImplicitOverride": true } }` . <br/> <strong>strict:</strong> Enables all strict type checking options. Indispensable. <strong>noUncheckedIndexedAccess:</strong> Prevents you from accessing an array or object without first checking if it's defined. This is a great way to prevent runtime errors, and should really be included in strict. <strong>noImplicitOverride:</strong> Makes the override keyword actually useful in classes.
| 12   |  What is transpiling in typescript? <br><br> Transpilation is about changing code written in one high-level language (like Typescript) into another (like JavaScript) that can run in places like web browsers or on servers using Nodejs. If you're transpiling your code (creating JavaScript files) with tsc, you'll want these options. <br/> `{ "compilerOptions": { "module": "NodeNext", "outDir": "dist" }}` <br/> <strong>module:</strong> Tells TypeScript what module syntax to use. NodeNext is the best option for Node. moduleResolution: NodeNext is implied from this option. <strong>outDir:</strong> Tells TypeScript where to put the compiled JavaScript files. dist is my preferred convention, but it's up to you.
| 13   |  Why need declaration option in tsconfig.json? <br><br> If you're building for a library, you'll want declaration: true. declaration: Tells TypeScript to emit .d.ts files. This is needed so that libraries can get autocomplete on the .js files you're creating. <br/><br/> If you're building for a library in a monorepo, you'll also want these options. <br/> `{  "compilerOptions": { "declaration": true, "composite": true, "sourceMap": true, "declarationMap": true}` <br/> <strong>composite:</strong> Tells TypeScript to emit .tsbuildinfo files. This tells TypeScript that your project is part of a monorepo, and also helps it to cache builds to run faster. <strong>sourceMap and declarationMap:</strong> Tells TypeScript to emit source maps and declaration maps. These are needed so that when consumers of your libraries are debugging, they can jump to the original source code using go-to-definition.
| 14   |  What is a tuple in TypeScript? <br><br> TypeScript introduced a new data type called Tuple. Tuple can contain two values of different data types. It can limit the number of elements along with the data type. `let employee: [number, string] = [1, "Steve"]; let customers: [number, string][]; customers = [[1, "Steve"], [2, "Bill"], [3, "Jeff"]];`
| 15   |  What is a Union in TypeScript? <br><br> TypeScript allows us to use more than one data type for a variable or a function parameter. This is called union type. When you want that a variable should be able to handle two or more data types. Then you can use a pipe sign That is the union type. <br/> https://www.tutorialsteacher.com/typescript/typescript-union
| 16   |  What is Narrowing in TypeScript? <br><br> Type narrowing is a process of refining or narrowing down the type using certain conditions with a particular code block. <br/> https://www.typescriptlang.org/docs/handbook/2/narrowing.html <br/> https://medium.com/@hrishikesh.pandey9955/what-is-narrowing-in-typescript-047b4c450de4
| 17   |  What is type guards in TypeScript? <br><br> Type guards enable you to instruct the TypeScript compiler to infer a specific type for a variable in a particular context. There are several types of type guards : 1) typeof 2) instanceof 3) Custom Type Guards <br/> https://www.typescriptlang.org/docs/handbook/advanced-types.html
| 18   |  What is static in TypeScript? <br><br> In TypeScript, you can use the static keyword to define static class members, including properties. A static property is a property that is shared across all instances of a class, and can be accessed without creating an instance of the class. 
```
class Counter {
    static count: number = 0;

    static increment() {
        Counter.count++;
    }
}
console.log(Counter.count);  // Output: 0
Counter.increment();
console.log(Counter.count);  // Output: 1

Advantages of Using 'static'
Shared State: Static properties allow you to maintain shared state across all instances of a class. This can be valuable for scenarios where maintaining a common value or counter is required.
Utility Functions: Static methods are excellent for creating utility functions that are related to the class but don't require an instance to operate. They keep the class's namespace clean by not cluttering it with instance-specific methods.
Singular Configuration: When you need configuration settings that apply to the entire class, using static properties can centralize this configuration without needing to replicate it across instances.
Factory Methods: Static methods can be used as factory methods to create instances of a class with specific configurations, simplifying the process of instance creation.
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 19  |  Advantages of Enum in TypeScript? <br><br> 
```
export enum AppData {
  APPSERVER = 1.0,
  DT = Date.now()
}
console.log(AppData); // {1: "APPSERVER", APPSERVER: 1, DT: 1735204902342, 1735204902342: "DT"}

let a = 3;
let b = 6;
export enum Result {
  SUM = sum(a, b)
}
function sum(a, b) {
  return a + b;
}
console.log(Result); // {9: "SUM", SUM: 9}
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 19  |  What will the output of `const {a=90, b} = {}; console.log(a, b);`? <br><br> Ans. 90 undefined 
