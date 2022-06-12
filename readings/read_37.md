# 37 - React 1

## [ES6 Syntax and Feature Overview] 

ECMAScript 2015, also known as ES6, introduced many changes to JavaScript.

### [Variables and Constant Feature Comparison] 

Keyword | Scope | Hosting | Reassignable | Redeclarable
--------|-------|---------|--------------|-------------
`var` |	Function | scope |	Yes |	Yes |	Yes
`let` |	Block | scope |	No |	Yes |	No
`const` |	Block | scope |	No |	No |	No

### [Constant Declaration] 

ES6 introduced the const keyword, which cannot be redeclared or reassigned, but is not immutable.

### [Arrow Functions] 

The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.

### Template Literals

#### [Concatenation/String Interpolation] 

Expressions can be embedded in template literal strings.

#### [Multi-Line Strings] 

Using template literal syntax, a JavaScript string can span multiple lines without the need for concatenation.

### [Implicit Returns] 

ES6 introduces a shorter notation for assigning properties to variables of the same name.

### [Method Definition Shorthand] 

The function keyword can be omitted when assigning methods on an object.

### [Destructuring (Object Matching)] 

Use curly brackets to assign properties of an object to their own variable.

### [Array Iteration (Looping)] 

A more concise syntax has been introduced for iteration through arrays and other iterable objects.

### [Default Parameters] 

Functions can be initialized with default parameters, which will be used only if an argument is not invoked through the function.

### [Spread Syntax] 

Spread syntax can be used to expand an array, or for function arguments.

### [Classes/Constructor Functions] 

ES6 introducess the class syntax on top of the prototype-based constructor function.

### [Inheritance] 

The extends keyword creates a subclass.

### Modules ([Export] 

Modules can be created to export and import code between files.

### Promises/Callbacks

Promises represent the completion of an asynchronous function. They can be used as an alternative to chaining functions.