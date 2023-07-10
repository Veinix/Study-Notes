# Console Notes

Within each browser we have a console that displays errors and can also display information that we log to it

[Back to JavaScript Menu](./jsMain.md)

[Links to sources, and more reading](#sources)

---

## Methods

- `console.log(data, ...args)` - Logs "data" to the console

- `console.info(data, ...args)` - Equivalent to console.log() but normally with emphasised formatting (Firefox puts a little i and chrome highlights in blue)
- `console.error(data, ...args)` - Equivalent to console.log(), but the output is directed to the stderr (error) stream
- `console.warn(data, ...args)` - The same as console.error(), except a yellow background is normally applied to indicate the less severe warning status
- `console.table(data, ...args)` - Emmits tabulated data to the console
- `console.assert(bool exp, data)` - Conditionally outputs data to console if boolean expression evaluates to false
- `console.group(optionalLabel) and console.groupEnd(optionalLabel)` - Visually groups sections of output with an indentation
- `console.count(optionalLabel) and console.countReset(optionalLabel)` - Internal, named counter
- `console.time(optionalLabel) and console.timeEnd(optionalLabel)` - Operation timing according to the time elapsed between each method. Not high accuracy. console.timeEnd() emits to the console the time elapsed
- `console.clear() and console.dir(obj, options) and console.trace() and console.profile()` - Utility methods which help you manage your output

## Format Specifiers

Arguments with printf-compatible format specifiers defined by a string in "data":

- `%s` – Format as a string
- `%i` – Format as an integer
- `%f` – Format as a floating point value
- `%O` – Format as a JavaScript object
- `%o` – Format as a DOM element
- `%c` – Format as a CSS rule, which is applied to the emitted log line

## Adding Images

Using the CSS format specifier, it’s possible to include images in console output. This works in browsers but won’t be supported in CLI environments (eg. Node.js)

Example:

```javascript
 const css = [
 "background-image: url(https://example.com)",
 "background-size: cover",
 "height: 100px",
 "padding: 15px",
 "width: 100px"
 ];

 console.log("%cI'm An Image!", css.join(";"));
 ```

## Tabulated Output

`console.table(data, ...args)`

JavaScript includes built-in support for emitting tabulated data to the console. Use console.table() with an array of uniform objects. The column headers will be determined automatically, based on the properties common to each object

## Conditional Output

`console.assert(boolean expression, data)`
Conditional output on the value of an expression. Reduces code by avoiding prefacing console.log with a boolean. The message will only be logged if the expression evaluates to false. An expression evaluting to true will result in nothing being emitted

The function does not affect runtime. No error will be thrown if the assertion fails; your expression is used solely to determine whether to log to the console

## Message Groups

`console.group()` and `console.groupEnd()`

You can visually group sections of output together with `console.group()`. This will apply an automatic indent to subsequent lines using a predefined number of spaces

`console.group()` can be called multiple times before `console.groupEnd()` to create deeply nested output. `console.groupEnd()` reverts the indentation by one step at a time, so you’ll need to match the number of `group()` and `groupEnd()` calls before you get back to the default level

## Counters

`console.count(label)` and `console.countReset(label)`

Creates internal counter with "label" name. Name is not required – the default label is "default". You can reset counters to 0 using `console.countReset(label)`

## Timers

`console.time()` and `console.timeEnd()`

The console has built-in support for operation timing. Elapsed time is measured in milliseconds and emitted in seconds (e.g. “1.234s”); it’s not guaranteed to be high-accuracy. Timers support optional labels in the same way as counters. This lets you manage multiple timers simultaneously when timing different aspects of your code

## Utility Methods

`console.clear()` and `console.dir(obj, options)` and `console.trace()` and `console.profile()`

`console.clear()`
: Clears the console of all visible output. The effects will vary by execution environment

`console.dir(obj, options)`
: Emits a list of all the enumerable property/value pairs of the object obj. You can customise the recursion depth using the depth property of the options object

`console.trace()`
: Emits a stack trace to the current point in your code, enabling straightforward debugging of the execution path taken

`console.profile()`
: Non-standard method (engine-dependent). Widely available but with differing implementations. In browsers, it generally invokes high-accuracy profiling to help you diagnose performance issues

---

## Sources

[How to Geek - Formatting Output](https://www.howtogeek.com/devops/ways-to-format-console-output-in-javascript/)

[Mozilla MDN - Console API](https://developer.mozilla.org/en-US/docs/Web/API/Console_API)

[Mozilla MDN - Console Object](https://developer.mozilla.org/en-US/docs/Web/API/Console)

[Back to top](#console-notes)
