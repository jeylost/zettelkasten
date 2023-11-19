---
tags:
  - nginx
  - javascript
---
The Nginx team developed the `njs` module, which allows writing scripts in JavaScript inside Nginx configurations. Previously, to extend Nginx configurations, you could only use Lua or Perl. This module works in both HTTP and TCP/UDP contexts. See examples in the [docs](https://nginx.org/en/docs/njs/).
# Performance concerns
The Nginx team developed its own interpreter engine. This engine is dedicated to working inside the Nginx request context; therefore, it deliberately doesn't contain:
- JIT Compilation
- Garbage collector(Interpreter has its own VM contexts similar to [[nodejs-code-execution-isolation|V8 context]]. Each request executes in its own isolated context. VM is destroyed at once when execution is finished)
- Redundant API(in terms of Nginx context)
# How fast is it, actually?
As all computing happens inside the virtual machine context, the main goal of the Nginx team was to make the operation of creating/destroying context as fast as possible. To achieve this, the Nginx team made the following decisions:
- Bytecode compilation at start time
- Use Registry based VMs(small memory footprint)
- Copy-on-write cloning of compiled VM for each request(Fast creating and destroying of VMs)
- Use UTF8 strings, byte strings optimizations(EcmaScript specs require UTF-16)
- Disable Garbage collector(Instead cloned VM is destroyed at once)

![[nginx_njs_vm_perf.png]] Benchmarks provided by the Nginx team at Nginx Conf 2018

## The virtual machine (VM) is destroyed. Should I load the same file into memory each time?
As the VM context lifecycle ends with the request's lifetime, your code has to load all prerequisites for each request. For example, your code may load a file from the disk. To optimize and prevent context-less operations from occurring with each request, the Nginx team provides shared memory called `preloaded_object`. This shared memory doesn't allow the value to change over time; it's read-only to prevent any race conditions from happening. More information can be found [here](https://nginx.org/en/docs/njs/preload_objects.html).
