---
tags:
  - nodejs
  - security
---
Event Loop allows Node.js to handle large number of requests inside a single process. It's a huge [[node-js-non-blocking|benefit]] of the platform. However, at the same time, it creates a security issue. All users' data is being handled in the same address space. If someone finds a way to exploit our application code, it has the potential to damage all clients
# Methods for Isolating Code Execution (From Heavy to Lightweight)
- process
- thread
- v8::Isolate
- v8::Context
