---
tags:
  - nodejs
  - process_env
---
# Node.js NODE_ENV variable use cases

The `NODE_ENV` variable should **not** be mistaken with branching strategies or application environments. Many npm packages and Node.js itself rely on this value to differentiate development and production(operation) mode. Libraries code might act differently for `development` and `production` environments.

Node.js assumes it's always running in a development environment. Therefore, only `NODE_ENV=production` is a valid value to signal Node.js to operate in production mode. For more details, read [Node.js, the difference between development and production](https://nodejs.org/en/learn/getting-started/nodejs-the-difference-between-development-and-production).
