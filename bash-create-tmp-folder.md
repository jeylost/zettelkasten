---
tags:
  - bash
---
Sometimes writing a bash script you need a temporary directory or file to do stuff. Its primary purpose is to ensure that the temporary file or directory it creates does not already exist, thereby preventing potential conflicts with existing files.

```bash
mktemp -d 
# returns absolute path
```
-d -- directory instead of file