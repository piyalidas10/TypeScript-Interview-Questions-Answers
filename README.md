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
| 20 |  What will the output of `const {a=90, b} = {}; console.log(a, b);`? <br><br> Ans. 90 undefined 
| 21  |  an interface and a class in TypeScript? <br><br> A class is a blueprint from which we can create objects that share the same configuration - properties and methods. An interface is a group of related properties and methods that describe an object, but neither provides implementation nor initialisation for them. 
| 22  |  What are abstract classes? <br><br> Ans. An abstract class is a class that you cannot create an instance, but it serves as a base class to the extended classes or subclasses. It includes both abstract and regular methods. It is a class that is inherited by multiple classes. We cannot create objects of an abstract class. <br/> https://stackblitz.com/edit/class-abstract-interface-myspgfqt?file=src%2Fapp%2Fapp.component.ts
| 23  |  Why interface is preferred over abstract class? <br><br> Ans. In general, you should choose interfaces over abstract classes. The use of an interface separates your design from any implementation details. Even if you declare a purely abstract class without any method implementations, you must inherit from it to define classes that share the behavior defined by its methods.
| 24  |  Can a class inherit from more than two abstract classes? <br><br> Ans. Yes, A class can inherit from any number of abstract classes.
| 25  |  What is Class Accessors (getter & setter) ? <br><br> The getter method is executed when you read/get the value. The setter method is executed when you assign a value to that property. <br/> https://www.typescripttutorial.net/typescript-tutorial/typescript-getters-setters/ 
| 26  |  What is Interfaces ? <br><br> TypeScript interfaces define the structure of an object, specifying property types and method signatures. They act as contracts, ensuring that objects adhere to a particular shape, enhancing type safety and code readability, and enabling features like optional properties, read-only properties, and interface inheritance. `interface IPerson { name: string; age: number; address?: string; display() => void; }  class Customer implements IPerson{ name: 'test', age: 20; display(){console.log('hi');}` <br/> https://www.geeksforgeeks.org/what-is-interfaces-and-explain-it-in-reference-of-typescript/?ref=lbp
| 27  |  What is readonly property in Typescript ? <br><br> In TypeScript, readonly properties in an object type ensure that a property can only be set during the object's initialization. Once assigned, the value of a readonly property cannot be changed, providing a way to create immutable object properties. 
```
interface Employee {
  readonly name: string;
}
const employee: Employee = { name: 'Michael Scott' };
employee.name = 'Oscar Martinez'; // will get compile error

No, readonly properties cannot be modified after the object is created. Any attempt to change the value of a readonly property will result in a TypeScript error.
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 28  |  Readonly vs Const in Typescript ? <br><br> readonly applies to object properties and prevents modification after initialization, while const applies to variables and prevents reassignment of the variable itself, not its contents if it's an object or array. <br/> A const variable cannot be re-assigned, just like a readonly property. Essentially, when you define a property, you can use readonly to prevent re-assignment. This is actually only a compile-time check. When you define a const variable (and target a more recent version of JavaScript to preserve const in the output), the check is also made at runtime.
```
let tuple: Readonly<[number, string]> = [0, ''];
tuple.shift(); // Property 'shift' does not exist on type 'readonly [number, string]'.
tuple.pop(); // Property 'pop' does not exist on type 'readonly [number, string]'.

const Arr = [1,2,3];

Arr[0] = 10;   //OK
Arr.push(12); // OK
Arr.pop(); //Ok
//But
Arr = [4,5,6] // ERROR
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 29  |  When & why use Generics in Typescript ? <br><br> Generics enables developers to write reusable and type-safe code. Generics allow you to create components that can work over a variety of types rather than a single one. When you start needing a generic is when you truly don't know what the type is going to be passed into the function, class, interface, constant.
```
function add<T, U>(a:T, b:U) {
    console.log(a+b);
}
add<number, string>(1, 'hi');
add<string, number>('hi', 1);
----------------------------------------------------------------------
class Box<T> {
    private value: T;
    constructor(value: T) {
        this.value = value;
    }
    getValue(): T {
        return this.value;
    }
}
let box = new Box<number>(42);
console.log(box.getValue()); // Output: 42
----------------------------------------------------------------------
interface Pair<T, U> {
    first: T;
    second: U;
}
let pair: Pair<number, string> = { first: 1, second: "two" };
console.log(pair); // Output: { first: 1, second: "two" }

function reverse<T>(array: T[]): T[] {
    return array.reverse();
}
----------------------------------------------------------------------
let numbers: number[] = [1, 2, 3, 4, 5];
let reversedNumbers: number[] = reverse(numbers);
console.log(reversedNumbers); // Output: [5, 4, 3, 2, 1]
```

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 29  |  What is Generic Constraints in Typescript ? <br><br> In TypeScript, generic constraints restrict the types that can be used with a generic type by using the extends keyword.
```
function getLength<T>(v: T): void {
    console.log(v.length); // will get error "property length doesn't exist on type T"
}
getLength('Hi');

Now here we want to put a constraint that allows to pass only those values which have length property. string in our case
--------------------------------------------------------------------------------------------
interface IC {
    length: number;
}
function getLength<T extends IC>(v: T): void {
    console.log(v.length); // display 2
}
getLength('Hi');
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 29  |  What is Namespace in Typescript ? <br><br> TypeScript, a namespace is a way to organize code into logical groups and avoid naming collisions between identifiers. Namespaces provide a way to group related code into a single namespace or module so that we can manage, reuse and maintain our code easily.

<h5>Benefits of Using Namespaces:</h5>
<strong>Logical grouping:</strong>strong> Namespaces provide a way to group related code into a single namespace or module, making it easier to manage and maintain your code.
<strong>Avoid naming collisions:</strong> Namespaces help to avoid naming collisions between identifiers by providing a unique namespace for each piece of code.
<strong>Encapsulation:</strong> Namespaces provide a way to encapsulate code by hiding implementation details and only exposing the public API.
<strong>Modularity:</strong> Namespaces provide a way to create modular code by breaking up a large codebase into smaller, more manageable pieces.

We have also defined a function called myFunction inside the namespace. The export keyword is used to make the function accessible outside the namespace.
```
namespace Myself {
    export function myFunction() {
        console.log('This is my function');
    }
}
Myself.myFunction(); // Output: This is my function
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 30  |  What is readonly type ? <br><br> you can use readonly to prevent re-assignment. This is actually only a compile-time check. 
```
type Person = {
     readonly name: string;
     age: number;
}
const person1: Person = {
   name = "John";
   age: 30;
}
// name property will not change 'cuz it was assigned to be readonly
person1.name = "Sarah"; ❌
person1.age = 20; ✅ 
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 31  |  How to use the `readonly` keyword on an interface? <br><br> 
```
interface Car {
 make: string;
 model: string;
}
const readonlyCar1: Readonly<Car> = {
 make: "Tesla",
 model: "Model S"
};
// This will not compile because the make property is readonly
readonlyCar1.make = "Toyota"; ❌
// This will not compile because the model property is readonly
readonlyCar1.model = "Camry"; ❌

const car2: Car = {
 make: "Tesla",
 model: "Model S"
};
car2.make = "Toyota"; // OK ✅
car2.model = "Camry"; // OK ✅
```

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 32  |  Write down union type ? <br><br> Unions are created using the | (pipe) operator, which represents a value that can have any of the types in the union. Take the following example: 
```
type ProductCode = number | string;
In this code, ProductCode can be either a string or a number. The following code will pass the type checker:
type ProductCode = number | string;
const productCodeA: ProductCode = 'this-works';
const productCodeB: ProductCode = 1024;
---------------------------------------------------------------------
const stuff: (num | string)[] = [1, 2, 'a'];
---------------------------------------------------------------------
type DayOfWeek =
  | "Monday"
  | "Tuesday"
  | "Wednesday"
  | "Thursday"
  | "Friday"
  | "Saturday"
  | "Sunday";

let today: DayOfWeek = "Sunday";
```

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 33  |  What is Intersection types ? <br><br> You can use intersection types to create a completely new type that has all the properties of all the types being intersected together. In this example, two interfaces named student and teacher are created. Intersected type is created by using ‘&’ between student and teacher. Intersected type contains all the properties of the two interfaces. An obj of intersection type is created and values are retrieved from it. We can not use a property without assigning it to the intersection type object.
```
interface Student { 
student_id: number; 
name: string; 
} 

interface Teacher { 
Teacher_Id: number; 
teacher_name: string; 
} 

type intersected_type = Student & Teacher; 

let obj1: intersected_type = { 
student_id: 3232, 
name: "rita", 
Teacher_Id: 7873, 
teacher_name: "seema", 
}; 

console.log(obj1.Teacher_Id); 
console.log(obj1.name);
-------------------------------------------------------------------------------------------------
interface CreateArtistBioBase {
  artistID: string;
  thirdParty?: boolean;
}
type CreateArtistBioRequest = CreateArtistBioBase & ({ html: string } | { markdown: string });

// Now you can only create a request when you include
// artistID and either html or markdown

const workingRequest: CreateArtistBioRequest = {
  artistID: "banksy",
  markdown: "Banksy is an anonymous England-based graffiti artist...",
};
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 35  |  What is Literal Types ? <br><br> TypeScript's literal types allow developers to specify exact values for variables, function parameters, or properties, enhancing type safety by ensuring variables can only hold predefined values.
```
// Literal Types
let zero: 0 = 0;
let mood: "Happy" | "Sad" = "Happy";
mood = "Sad";
-------------------------------------------------------------
type DayOfWeek =
  | "Monday"
  | "Tuesday"
  | "Wednesday"
  | "Thursday"
  | "Friday"
  | "Saturday"
  | "Sunday";
let today: DayOfWeek = "Sunday";
---------------------------------------------------------------
type SkillLevel = "Beginner" | "Intermediate" | "Advanced" | "Expert"; // SkillLevel is Literal Types
type SkiSchoolStudent = {
  name: string;
  age: number;
  sport: "ski" | "snowboard";
  level: SkillLevel;
};
```

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 36  |  How will create custom type ? <br><br> In TypeScript, the syntax for creating custom types is to use the type keyword followed by the type name and then an assignment to a {} block with the type properties. Take the following:
```
type Programmer = {
  name: string;
  knownFor: string[];
};

const ada: Programmer = {
  name: 'Ada Lovelace',
  knownFor: ['Mathematics', 'Computing', 'First Programmer']
};
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 37  |  Create a tuple ? <br><br> Typically an array contains zero to many objects of a single type. TypeScript has special analysis around arrays which contain multiple types, and where the order in which they are indexed is important. These are called tuples.
```
type HTTTResponse = [number, string];
const apiRes: HTTTResponse = [["200", "Ok"], ["404", "Not Found"]];
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------- ------------------------------------------------------------------------------------------------------------------------------ |
| 38  |  What is Merging Interfaces ? <br><br> At the most basic level, the merge mechanically joins the members of both declarations into a single interface with the same name.
```
interface Box {
  height: number;
  width: number;
}
interface Box {
  scale: number;
}
let box: Box = { height: 5, width: 6, scale: 10 };
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 38  |  Can you extend interface in TypeScript? <br><br> <strong>Interfaces</strong> in TypeScript are a powerful way to define contracts within your code and they can be extended using the extends keyword. This is one of the most straightforward methods to extend a type. <br/> <strong>extends</strong> is used for class inheritance, allowing a class to inherit properties and methods from another class.
```
interface Person {
  name: string
  age: number
}

interface Employee extends Person {
  employeeId: number
}

const employee: Employee = {
  name: 'John Doe',
  age: 30,
  employeeId: 123
}
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 39  |  Extends and Implements in TypeScript? <br><br> <strong>extends</strong> is used for class inheritance, allowing a class to inherit properties and methods from another class.<br> <strong>implements</strong> is used for interface implementation, ensuring a class adheres to a defined contract.
```
interface Product {
    productId: string;
}
interface Appliance extends Product {
    brand: string;
    turnOn(): void;
}

class WashingMachine implements Appliance {
    productId: string;
    brand: string;

    constructor(productId:string, brand: string) {
        this.productId = productId;
        this.brand = brand;
    }

    turnOn(): void {
        console.log(`${this.brand} washing machine is now on. The Product id is ${this.productId}`);
    }
}

const myWasher = new WashingMachine('pd001', 'LG');
myWasher.turnOn(); // LG washing machine is now on.
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 40  |  Type vs Interface in TypeScript? <br><br> https://blog.logrocket.com/types-vs-interfaces-typescript/  <br>
```
Union types
===================================================================
Union types allow us to describe values that can be one of several types and create unions of various primitive, literal, or complex types:
type Transport = 'Bus' | 'Car' | 'Bike' | 'Walk';
Union type can only be defined using type. There is no equivalent to a union type in an interface.

Merging
===================================================================
we can define an interface multiple times, and the TypeScript compiler will automatically merge these definitions into a single interface definition.
interface Client { 
    name: string; 
}
interface Client {
    age: number;
}
const harry: Client = {
    name: 'Harry',
    age: 41
}
Type aliases can’t be merged in the same way. If you try to define the Clienttype more than once, an error will be thrown:

Extends and intersection
===================================================================
An interface can extend one or multiple interfaces. Using the extendskeyword, a new interface can inherit all the properties and methods of an existing interface while also adding new properties.
interface Name {
    name: string;
}
interface Person extends Name {
    age: Number;
}
const person: Person = {
  name: 'Joe',
  age: 28
}

To achieve a similar result for types, we need to use an intersection operator:
type Name = {
    name: string;
}
type Person = Name & {
    age: Number;
}
const person: Person = {
  name: 'Joe',
  age: 28
}
```
