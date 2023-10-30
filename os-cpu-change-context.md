---
tags:
  - cpu
  - kernel
  - os
---
The kernels of operating systems distribute CPU time between processes and threads by pausing the execution of the current process, saving its computed state, and switching the CPU to another process to work on. This switching between processes is considered a 'heavy' operation