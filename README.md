# namaste_nodejs_notes
Namaste 🙏 NodeJs is a playlist by Akshay Saini. These are the notes I've made when I was learning NodeJs from Scratch using the playlist.

# 📘 Node.js - Chapter 1: Introduction (Quick Notes)
🧠 Run JavaScript everywhere, not just in browsers
⚙️ JS Runtime built on Chrome’s V8 engine
🌐 Cross-platform & open-source
🏢 Maintained by OpenJS Foundation
🌍 Executes JS outside the web browser
🔁 Uses event-driven & non-blocking (async) I/O
👨‍💻 Created by Ryan Dahl in 2009

# 🛠️ The Journey
- JS always needs a JS engine to run
- Initially used SpiderMonkey (Firefox), then V8 (Chrome)
- Ryan worked with Joyent, named it web.js at first
- Built Node.js to improve over blocking servers like Apache
- First built for Mac/Linux, Windows support came in 2011
- In 2012, Isaac (creator of npm) took over
- 2014, fork called io.js was made by Fedor
- In 2015, Node.js & io.js merged
- In 2019, JS Foundation + Node.js Foundation = OpenJS Foundation

# 2. JS on Server 🌐
- JavaScript used to run only in browsers
- After Node.js, JS can run on servers
- Now JS developers can code for both client & server
- Remote CPU = running code on a server
- V8 Engine (from Chrome) is written in C++
- V8 is just code, can be embedded into any C++ app
- Node.js is a C++ app with V8 + server APIs
- Together, this becomes a JS Runtime (Node.js)
- Code execution flow:
High-level (C++) → Machine Code → Assembly → Binary

# 3. Let's Write Code 🧑‍💻
- Install Node.js
- Check versions:
node -v
npm -v
- Run Node in terminal → REPL
(Read, Evaluate, Print, Loop)
- Just type node in terminal → write JS code directly
- Using VS Code: Create app.js
- Run with: node app.js
- Explore built-in global:
console.log(global);        // superpowers like setTimeout, setInterval

console.log(this);          // empty object {}

console.log(global === globalThis); // true

# 4. module.exports & require() 📦
- Node uses CommonJS Modules (CJS) by default
- To import a file: require('./xyz.js');
- By default, modules are private
- To share/export a function:
- module.exports = calculateSum;
- To import: const calculateSum = require('./xyz.js');
- To Export multiple things: module.exports = { x, calculateSum };
- To Import: const obj = require('./xyz.js');
obj.calculateSum();
console.log(obj.x);
- Or use destructuring: const { x, calculateSum } = require('./xyz.js');
- Variable scope remains safe across files – no conflicts
- ES Modules (mjs format):
- Add to package.json: { "type": "module" }
- Export: export function greet() {}
- Import: import { greet } from './file.js';
- Organizing many files: Create index.js inside folder
- Import in index.js: const fn = require('./file1');
- Then export everything: module.exports = { fn, xyz };
- In app.js, import all at once: const { fn, xyz } = require('./folder/index');
