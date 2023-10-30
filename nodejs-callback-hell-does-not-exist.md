---
tags:
  - nodejs
  - issue
---
Using named functions instead of anonymous once and store them in global scope resolves "callback hell".

Instead of this:
```javascript
setTimeout(() => {
  console.log('Step One');
  
  setTimeout(() => {
    console.log('Step Two');
    
    setTimeout(() => {
      console.log('Step Three');
    }, 1000);
    
  }, 1000);
  
}, 1000);
```

Do this:
```javascript
function stepThree() {
  console.log('Step Three');
}

function stepTwo() {
  console.log('Step Two');
  setTimeout(stepThree, 1000);
}

function stepOne() {
  console.log('Step One');
  setTimeout(stepTwo, 1000);
}

setTimeout(stepOne, 1000);
```

Even though "callback hell" doesn't exist, using async/await is the best approach for writing application code.
