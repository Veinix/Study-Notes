# NodeJS

Imagine you're at a restaurant, and the waiter is the person who takes your order, goes to the kitchen, waits for the cook to prepare your meal, brings it back to you, and then repeats this for every other person in the restaurant. This is how most web servers work, but it's not very efficient because while the waiter is waiting for your meal, he can't do anything else.

Now, Node.js is like a restaurant where the waiter takes your order, goes to the kitchen, leaves your order there, then immediately goes to take someone else's order. The waiter can take lots of orders without waiting for the meals to be cooked. When each meal is ready, a bell rings and the waiter picks it up and delivers it to the right table. This is why Node.js is very powerful: it allows the server to handle many requests at the same time without waiting, making it very efficient.

[Back](../jsLibrariesMain.md)

## Table of Contents

- [Introduction](#introduction)
- Second
- Third

[Link to Sources](#sources)

---

## Introduction

### What is NodeJS?
Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that executes JavaScript code outside a web browser. It's built on Chrome's V8 JavaScript engine. Node.js allows you to run JavaScript on your server - which is a big deal because, before Node.js, JavaScript could only effectively be run in the browser.

One of the key advantages of Node.js is its non-blocking, event-driven architecture. In a traditional synchronous environment, each operation blocks the thread until it completes, with the thread potentially sitting idle when it could be doing useful work. However, Node.js uses a callback-driven model, allowing it to handle many concurrent connections with a single server. This makes Node.js a good choice for applications that require real-time interaction or collaboration, such as online gaming, chat rooms, or other web apps that need to process high volumes of short messages requiring low latency.

### How to use it?
Using Node.js involves writing JavaScript that can be run by the Node.js runtime. You can start by downloading and installing Node.js from the official website. Once installed, you can create a new ".js" file and write your JavaScript code in it.

For example, you can create a simple HTTP server in Node.js like so:

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(3000, '127.0.0.1', () => {
  console.log('Server running at http://127.0.0.1:3000/');
});
```

### What can it do?

With NodeJS it is possible to do many things including:

- **Create Real-Time Applications:** Node.js excels at real-time applications: online games, collaboration tools, chat rooms, or anything where you need to see a lot of network traffic. Its event-driven, non-blocking I/O model makes it ideal for this kind of environment.

- **Build API servers:** Node.js, in combination with Express.js, is commonly used to build RESTful APIs. Its non-blocking nature allows it to handle many requests simultaneously, making it great for working with databases or other I/O operations.

- **Server-Side Web Application:** With the help of Express.js, or other similar frameworks, you can build server-side rendered web applications just like in other server-side languages like PHP, Ruby, or Python.

- **Microservices:** Node.js is often used to build microservices, small, independent services that work together to form a larger application. Its ability to handle many connections simultaneously and its efficient use of resources make it well-suited for this kind of architecture.

- **Command Line Applications:** Node.js can be used to build command-line applications. For example, you can build tools to automate your workflow, or even build complex systems like web scrapers or automation bots.

- **Desktop Applications:** With frameworks like Electron.js, you can use Node.js to build cross-platform desktop applications. Major applications like Visual Studio Code and Slack are built with this technology.

- **Internet of Things (IoT):** Node.js is lightweight and efficient, making it perfect for IoT devices which may not have a lot of computational power or memory.

- **Data Streaming:** Node.js's streams make it excellent for handling data streaming, which is the continual flow of data. This is useful for features like audio or video encoding and proxying between different data sources.

---

## Next Topic

---

## Sources

[W3 Schools - NodeJS Intro](https://www.w3schools.com/nodejs/nodejs_intro.asp)

[W3 Schools - NodeJS Tutorial](https://www.w3schools.com/nodejs/)

[NodeJS Documentation](https://nodejs.org/en/docs)

[NodeJS Tutorial](https://nodejs.dev/en/learn/)

[Back to top](#nodejs)
