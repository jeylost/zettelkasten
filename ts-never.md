#ts 

# Use cases

## Ensure all switch-cases  are covered
```typescript
function unknownColor(x: never): never {
    throw new Error("unknown color");
}


type Color = 'red' | 'green' | 'blue'

function getColorName(c: Color): string {
    switch(c) {
        case 'red':
            return 'is red';
        case 'green':
            return 'is green';
        default:
            return unknownColor(c); // Argument of type 'string' is not assignable to parameter of type 'never'
    }
}
```


## Partially disallow [[ts-structural-type-system|structural typing]]
Problem:
```typescript
type VariantA = {
    a: string,
}

type VariantB = {
    b: number,
}

declare function fn(arg: VariantA | VariantB): void


const input = {a: 'foo', b: 123 }
fn(input) // TypeScript doens't complain but this shouldn't be allowed for our use case
```

Resolver:
```typescript
type VariantA = {
    a: string
    b?: never
}

type VariantB = {
    b: number
    a?: never
}

declare function fn(arg: VariantA | VariantB): void


const input = {a: 'foo', b: 123 }
fn(input) // ❌ Types of property 'a' are incompatible
```


Based on article(contains additional examples): https://www.zhenghao.io/posts/ts-never