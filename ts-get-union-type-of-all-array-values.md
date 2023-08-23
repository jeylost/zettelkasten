#ts 

```typescript 
const Letters = ["a", "b", "c", "d"] as const;
type Letter = typeof Letters[number];
```

[[Matt Pocock|Matt Pocock's]] video: https://www.youtube.com/watch?v=sswUBXaoXSI&list=PLIvujZeVDLMx040-j1W4WFs1BxuTGdI_b&index=24