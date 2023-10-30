---
tags:
  - nodejs
  - eventloop
  - libuv
---
The killer feature of Node.js is its ability to efficiently handle a large number of I/O operations within a single thread. For example, PHP, C#, and Java runtimes create additional instances of the application within separate threads or processes for each request, which significantly [[os-cpu-change-context|exhausts]] the machine's resources.