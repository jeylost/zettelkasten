---
tags:
  - nodejs
  - async
  - modules
---
Top level await allows to do async things on the top file level without wrapping into async function.

## Example
```js
// fetch request
const colors = await fetch("../data/colors.json");

export default colors;
```

But it's only possible when you using the EcmaScript modularity system due to its asynchronous nature. For CommonJS modules you still need to wrap everything in async function:
```js
async () => {
 await db.connect();
})();
```

CommonJS is designed to be synchronous, and it's the sole reason why module resolution can be delayed, particularly in cases of circular dependencies. Enabling top-level `await` in CommonJS would break this design principle. There is an ongoing discussion on GitHub that covers all the details: [https://github.com/nodejs/node/issues/21267](https://github.com/nodejs/node/issues/21267)