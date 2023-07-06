# JSDocs Notes

## [Links to Sources](#sources)

---

## Tags

`@returns` tag - Documents the value that a function returns.

Example:

```javascript
/**
 * @returns {type} text the explains what is returned
*/
```

Can accept many types:

* Basic Data Types:
  * string: Represents a string value.
  * number: Represents a numeric value.
  * boolean: Represents a boolean value (true or false).
  * null: Represents a null value.
  * undefined: Represents an undefined value.

* Object Types:
  * { } or Object: Represents a generic object.
  * { key: valueType }: Represents an object with specific key-value pairs.
    * Example: { name: string, age: * number }.

* Array Types:
  * Array`<elementType>`: Represents an array of a specific element type.
    * Example: Array`<number>` represents an array of numbers.

* Custom Types:
  * Custom type names that you define in your codebase.

* Union Types:
  * type1 | type2: Represents a value that can be one of the specified types.
    * Example: string | number represents a value that can be either a string or a number.

* Function Types:
  * (param1: type, param2: type) => returnType: Represents a function type with specific parameter types and a return type.
    * Example: (name: string, age: number) => void represents a function that takes a string and a number as parameters and does not return any value.

* Promise Types:
  * Promise`<resolvedType>`: Represents a Promise that resolves to a specific type.
    * Example: Promise`<number>` represents a Promise that resolves to a number.

* Void:
  * void: Represents a function that does not return a value.

---

## Sources

[JSDocs Documentation](https://jsdoc.app/)
