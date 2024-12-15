# Basics
**JavaScript is case-sensitive**

```javascript
const Fruit = "Apple";
const fruit = "Apple";
```
Here, the variable `Fruit` is not the same as `fruit` because JavaScript is case sensitive.

In JS, instrucitons are called statements and are sepearted by semicolons(;).

>**Note**: A semicolon is not necessary after a statement if it is written on its own line. But if more than one statement on a line is desired, then they must be separated by semicolons.

The Source text of JavaScript script gets scanned from left to right, and is converted into a sequence of input elements which are tokens, control characters, line terminators, comments, or whitespace.(Spaces, tabs, and newline characters are considered whitespace.)


# Declarations

JavaScript has three kinds of variable declarations.

`var` : Declares a variable, optionally initializing it to a value.

`let` : Declares a block-scoped, local variable, optionally initializing it to a value.

`const`: Declares a block-scoped, read-only named constant.

# Variables
You use variables as symbolic names for values in your application. The names of variables, called identifiers, conform to certain rules.

A JavaScript identifier usually starts with a letter, underscore (_), or dollar sign ($). Subsequent characters can also be digits (0 – 9). Because JavaScript is case sensitive, letters include the characters A through Z (uppercase) as well as a through z (lowercase).


# Declaring variables
we can declare a variable in two ways:
- With the keyword `var`. For example, `var x= 42`. 
This syntax can be used to declare both local and global variables, depending on the execution context.
-With the keyword `const` or `let`. For example, `let y = 18`. This syntax can be used to declare a block-scope local variable.

# Declaration and initialization
In a statement like `let x = 18`, the `let x` part is called a declaration, and the `=42` part is called a initializer. The declaration allows the varible to be accessed later in code without throwing a [ReferenceError](), while the initiaizer assigns a value to the variable. In `var` and `let` declarations, the initializer is optional. If a varaible is declared without an initializer, it is assigned the value [undefined]().

```javascript
let x;
console.log(x); // logs "undefined"
```

In essence, `let x= 18` is equivalent to `let x; x =42`.

`const` declarations always need an initializer, because they forbid any kind of assignment after declaration, and implicitly initializing it with `undefined` is likely a programmer mistake.

```javascript
const x; // SyntaxError: Missing initializer in const declaration
```
# Variable Scope
- Global scope: The default scope for all code running in script mode.
- Module Scope: The scope for code running in module mode.
- Function scope: The scope created with a funciton.

In addition, variables declared with `let` or `const` can belong to an additional scope:
- Block scope: the scope created with a pair of curly braces (a [block]()).

_Global variable_: when you declare a variable outside of any function because it is available to any other code in the current doc.

_local variable_: When you declare a variable within a function, it is called a local variable, because it is available only within that funciton.

- `let` and `const` declarations can also be scoped to the [block statement]() that they are declared in.

```javascript
    if(Math.random() > 0.5) {
        const y = 5;
    }
    console.log(y); //ReferenceError: y is not defined
```
- However, `var` declarations are not block-scoped, but only local to the function (or global scope) that the block resides within.
```javascript
    if (true) {
        var x = 5;
    }
    console.log(x); // x is 5
```

# Variable hoisting
`var` declared variables are hoisted, meaning we can refer to the variable anywhere in its scope, even if its declareation isn't reached yet.
However, if you access a variable before it's declared, the value is always `undefined`, because only its _declaration_ and _default initialization_ (with `undefined`) is hoisted, but not its value assignment.

```javascript
    console.log(x === undefined); // true
    var x = 3;

    (function(){
        console.log(x); // undefined
        var x = "local value";
    })();
```
The above example will be interpreted the same as:

```javascript
    var x;
    console.log(x === undefined); //true
    x = 3;

    (function(){
        var x;
        console.log(x); //undefined
        x = "local value";
    })();
```
>Because of hoisting, all var statements in a function should be placed as near to the top of the function as possible. This best practice increases the clarity of the code.

Whether `let` and `const` are hoisted is a matter of defination debate. Referencing the variable in the block before the variable declaration always results in a [ReferenceError](), because the variable is in a "[temporal dead zone]()" from the start of the block until the declaration is processed.

```javascript
    console.log(x); //ReferenceError
    const x = 3;


    console.log(y); //ReferenceError
    let y = 3;
```

# Global variables
Global variables are in fact properties of the global object.

n web pages, the global object is `window`, so you can read and set global variables using the `window.variable` syntax. In all environments, the `globalThis` variable (which itself is a global variable) may be used to read and set global variables. This is to provide a consistent interface among various JavaScript runtimes.

# Constants
We can create a read-only, named constant with the `const` keyword.

```javascript
    const PI = 3.14;
```
A constant cannot change value through assignment or be re-declared while the script is running. It must be initialized to a value.

>We cannot declare a constant with the same name as a function or variable in the same scope.
```javascript
    // This will cause an error
    function f() {
        const f = 14;
    }

    //This will cause an error too
    function f() {
        const g = 5;
        var g;
    }
```

However, `const` only prevents re-assignments, but doesn't prevent mutations. the properties of objects assigned to constants are not protected, so the following statement is executed without problems.

```javascript
    const MY_OBJECT = { key: "value" };
    MY_OBJECT.key = "otherValue";
    
    //also, const of an array are not protected, so below statemetn is executed without problems.

    const MY_ARRAY = ["HTML", "CSS"];
    MY_ARRAY.push("JAVASCRIPT");
    console.log(MY_ARRAY); //['HTML', 'CSS', 'JAVASCRIPT'];
```
# Data Structures and types
**Data**
- Seven data types that are primitives:
1. [Boolean](). `true` and `false`.
2. [null](). A special keyword denoting a null value.
3. [undefined](). A top-level property whose value is not defined.
4. [Number](). An integer or floating point number. For example: `18` or `3.14159`.
5. [BigInt](). An integer with arbitary precision. for example: `9007199254740992n`.
6. [String](). A sequence of characters that represent a text value. For example: "John".
7. [Symbol](). A data type whose instances are unique and immutable.

# Data type conversion
JavaScript is a _dynamically typed language_. This means we don't have to specify the data type of a variable when you declare it. It also means that data types are automatically converted as-needed during script execution.
For example:
```javascript
    let answer = 18;
    // Later, we can assign the same variable a string value.
    answer = "Learning JavaScript";

```
# Numbers and the '+' operator
In expressions involving numberic an string values with the `+` operator, JavaScript converts numeric values to strings.

```javascript
    x = "The answer is " + 18; // "The answer is 18"
    y = 18 + " is the answer"; //"18 is the answer"
    z = "37" + 7: //"377"
```

With all other operators, JavaScript does not convert numberic values to strings.

```javascript
    "37" - 7; // 30
    "37" * 7; // 259
```

# Converting strings to numbers
In the case that a value representing a number is in memory as a string, there are methods for conversion.
- `parseInt()`
- `parseFloat()`
