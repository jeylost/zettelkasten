#ts
Better to avoid using of enums

Reasons:
1. Runtime object is not that plain "key-value" pair as it in TS
2. Enums is working as [[ts-nominal-type-system|nominal type system]]. That means we have to import it everywhere, and won't be able pass value as simple string:
```ts
log('Hey', 'DEBUG');
```
# Alternative
Use plain object with [[ts-const-assertion|const assertion]]:
```ts
const LogLevel = {
	DEBUG: 'DEBUG',
	WARNING: 'WARNING',
	ERROR: 'ERROR',
} as const

type ObjectValues<T> = T[keyof T];

type LogLevel = ObjectValues<typeof LogLevel>;

function log(message: string, level: LogLevel) {
}  

log('Hey', 'DEBUG');
```

[[Matt Pocock|Matt Pocock's]] video: https://www.youtube.com/watch?v=jjMbPt_H3RQ&list=WL&index=6