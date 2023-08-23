#ts 

```typescript
export type ActionModule = typeof import('./constants');

export Action = ActionModule[keyof ActionModule];
```


