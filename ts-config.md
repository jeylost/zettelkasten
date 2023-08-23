#ts 

```json
{
	"noUncheckedIndexedAccess": true
}
```

# Description
`noUncheckedIndexedAccess` - prevent issue when object is possible undefined
```typescript
export const myObj: Record<string, string[]> = {};

myObj.foo.push("bar"); // without noUncheckedIndexedAccess = true won't be an error 
```

