#ts 

```json
{
	"target": "es2022",
	"noUncheckedIndexedAccess": true,
	"strict": true,
	"skipLibCheck": true,
}
```

# Description
`noUncheckedIndexedAccess` - prevent issue when object is possible undefined
```typescript
export const myObj: Record<string, string[]> = {};

myObj.foo.push("bar"); // without noUncheckedIndexedAccess = true won't be an error 
```

`strict` -  Enable all strict type-checking options

`skipLibCheck` - Skip type checking of all `.d.ts` files. This enhances performance as TypeScript doesn't perform type checking on npm package types.

[Centralized Recommendations for TSConfig bases](https://github.com/tsconfig/bases)
