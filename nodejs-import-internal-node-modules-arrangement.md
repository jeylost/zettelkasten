---
tags:
  - nodejs
  - package_manager
---
It's better to use the `node:` prefix to distinguish internal Node.js packages from external libraries.
```js
import * as fs from 'node:fs';
```
