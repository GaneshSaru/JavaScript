# Introduction To JavaScript
1. JavaScript is a computer programming language which was invented by Brendan Eich in 1995 A.D.
2. JavaScript is one of the popular programming language and backbone of 99.99% websites.
3. Backbone because, from JS we can manipulate differenet element of website, Animate, make dynamic, and interactive websites.
4. JavaScript is highlevel, interpreted, dynamic typed, prototype based, general purpose, object-oriented, multi-paradigm language.

## History of JavaScript
World Wide Web (internet) was launched on April 30, 1993. At the beginning age of Browser, Netscape and Internet Explorer were Popular browsers. They had different Scripting languages for their browser. \
Windows came with JScript whereas Netscape came with Mocha. The problem was the website made using JScript was unable to run on Netscape. Similarly, the website made using Mocha was unable to run on InternetExplorer. \
To solve this, ECMA international came with the standard called ECMA Script, which standardized Script that runs on the Web. \
Later on, All Scripting Languages such as JavaScript, Action Script, JScript began to follow ECMA Standard. \
JavaScript was initially Named Mocha and then LiveScript. Later it was named JavaScript and launched in 1995.


## JS code is Interpreted.
During the parsing of any program it is either compiled or interpreted. 

**Interpretation**: Intrepreter translate the code into machine code line by line and execute at that instance. Slower than compiler as they have to translate to machine code one by one. 
**Language such as: JavaScript, Python, Perl etc.**

**Compilation**: Compiler translates the code into machine code, before they are executed. (all at once). Faster as comapared to interpretor.
    **Language such as C, C++, Go, Rust, etc.**

## Who interprets the JS code?
The interpretation of JavaScript code is done by Web Browser such as Chrome, Firefox, Safari, Brave etc. to be precise, the **javascript engine**.

> JS Engine is software that resides in a web browser that is responsible for converting/parsing JavaScript source code to machine code.
Examples of JS Engine: V8 engine (Chrome), SpiderMonkey (Firefox), JavaScript Core (Safari), Chakra (Internet Explorer).

## JS is Dynamically Typed Language
Generally, there are 2 types of typing discplines, **Static typed** and **Dynamically typed.**

Static Typed: check the types of variables and epressions at compile time. They are faster than dynamically typed. \
Example: C, C++, etc.
``` C
    #include<stdio.h>
    int adder(int a, int b){ // function adder is integer typed
        return a + b;
    }

    void main(){
        int sum = 0;  // variable sum is integer
        sum = adder(1, 2);
    }
```

Dyanmic Typed: check the types of variables and expressions at runtime. \
Example: JavaScript, Python, etc.

``` javascript
    function adder(a, b) { // function adder is not defined to any typed
        return a + b;
    }

    let sum = 0;  // no any typed is defined
    sum = adder(1, 2);
```

> Langugae supporting both types are gradual typed languages. We can do JS statically in TypeScript.

## JS is Object Oriented Language
Just like C++, Java, Python, JavaScript is also Object Oriented Programming Language. In this paradiagram, we map real-world logic and expression in form of classes and object.

Supports various OOP principles such as inheritance, encapsulation, absraction etc.

## JS is Prototyped based Language
In JavaScript everything is object. Taking from Array, functions, strings, and all. This is the weird part of javascript, but not really the weirdest one.

Being that, All object are created based on the prototypes, which are other objects that serve as a template. When you create a new object in JavaScript, you can specify a prototype for that object. The new object will inherit all of the properties and methods of its prototype.

## Object vs Class Object 
Class Object are the runtime instance of the class. \
Whereas, \
JavaScript Object are the one of the datatype of the JavaScript programming language.
