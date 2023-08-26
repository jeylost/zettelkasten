#ts 
# Interface use cases
- Declaration merging. Fits for npm packages. interfaces will allow simply add new properties to it:
```typescript
interface A {
	a: string;
};

interface A {
	b: string;
}

// result: interface A { a: string; b: string; }
```
- Classes can be typed with `implements` keyword
- Interfaces can extends each other
# Type use cases
- Use types unless you need a specific feature of interfaces. Because declaration merging is an implicit feature that leads to bugs that hard to debug