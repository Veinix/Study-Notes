# Data Types and Structures

## [Links to sources, and more reading](#sources)

> Do I look like I know what a .jpeg is?

Programming languages all have built-in data structures, but these often differ from one language to another. JavaScript is a dynamic language with dynamic types. Variables are not directly associated with a value type, and any variable can be assigned values of all types. It is also a weakly typed language, allowing implicit type conversion when an operation involves mismatches types. For Symbols and BigInts, JavaScript has intentionally disallowed certain implicit type conversions.

---

## Table of Contents

1. [Data Types](#data-types)
2. [Reference Type and Value Type](#reference-type-and-value-type)

---

## Data Types

### Primitive Types

All types except `Object` define immutable values represented directly at the lowest level of the language otherwise known **primitive values**. All primitive types, except `null`, can be tested by the `typeof` operator. `typeof` null returns "object", so one has to use === null to test for null.

All primitive types, except `null` and `undefined`, have their corresponding object wrapper types, which provide useful methods for working with the primitive values. For example, the `Number` object provides methods like `toExponential()`. When a property is accessed on a primitive value, JavaScript automatically wraps the value into the corresponding wrapper object and accesses the property on the object instead. However, accessing a property on `null` or `undefined` throws a _TypeError_ exception, which necessitates the introduction of the optional chaining operator.

* Number
    : Represents numeric values, both integers and floating-point numbers. `Eg. 42, 3.14`

* BigInt
    : Represents integers with arbitrary magnitude. A BigInt is created by appending n to the end of an integer or by calling the BigInt() function. `Eg. const x = BigInt(Number.MAX_SAFE_INTEGER) x + 1n === x + 2n;`
  
* String
    : Represents a sequence of characters enclosed in single quotes (') or double quotes ("). `Eg. 'Hello', "JavaScript"`

* Boolean
    : Represents a logical value, either true or false, which is used for making decisions or comparisons.

* Null
    : Represents the intentional absence of any object value. It is a primitive value type. `Eg. null`

* Undefined
    : Represents a variable that has been declared but not assigned a value. It is also a primitive value type. `Eg. undefined`

* Symbol
    : Represents a unique and immutable value used as an identifier for object properties. Symbols are often used for defining object keys. Symbols were introduced in ECMAScript 2015 (ES6).

## Objects

The "opposite" of a primitive type in JavaScript is an object type. While primitive types represent single values directly, object types are used to store and manipulate complex data structures. They are a reference type that can hold properties and methods.

* Object
    : Represents a collection of key-value pairs and can include functions and arrays. Objects are complex data types that can be created using object literals {} or the new keyword. `Eg. { name: 'John', age: 30 }`

* Array
    : Represents an ordered list of values. Arrays can contain elements of any data type, including other arrays and objects. Arrays are created using square brackets []. `Eg. [1, 2, 3]`

* Function
    : Represents a reusable block of code that performs a specific task when invoked. Functions can be assigned to variables, passed as arguments, and returned as values

* Date
    : An object type used for working with dates and times.

* RegExp
    : An object type used for working with regular expressions. Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects

## Reference Type and Value Type

### Value Type or Primitive Type

In JavaScript, a value type refers to a data type that is copied by value when assigned or passed as an argument. The value itself is stored directly in a variable or passed to a function. Changes made to a value type variable do not affect other variables holding the same value.

Example:

```javascript
let age = 30;
let age1 = age; // Pointing to age
  
console.log(`age = ${age}  age1 = ${age1}`);
// age = 30  age1 = 30
  
age = 31; // Pointing to new address
  
console.log(`age = ${age}  age1 = ${age1}`);
//  age = 31  age1 = 30
```

### Reference Type

JavaScript provides three types of Reference values that include Array, Object, and Function. The size of a reference value is dynamic.

In JavaScript, a reference type refers to a data type that is not stored directly in a variable but rather as a reference to an object in memory. When you assign or pass a reference type variable, you're actually copying the reference to the object rather than the object itself. Multiple variables can reference the same object, and modifications made to the object through one variable will be reflected in all variables referencing that object.

Example:

```javascript
let info = {
    Name :"Abc",
    Age :10
}
console.log(`Name : ${info.Name} Age : ${info.Age}`);
// Name : Abc Age : 10
  
let info1 = info;
info1.Age = 14; // Change the Age of original object
console.log(`Name : ${info.Name} Age : ${info.Age}`);
// Name : Abc Age : 14
```

---

## Sources

[MDN Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
