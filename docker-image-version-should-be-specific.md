---
tags:
  - docker
  - dockerfile
  - devops
---
In software development, the best practice is to specify a fixed image version with the exact major and minor parts to ensure stability.
# Real case scenario
It worked fine before Node.js was updated to 18.18:
```Dockerfile
FROM node:18-alpine
```

Fixed version:
```Dockerfile
FROM node:18.17-alpine
```