#ts 

- no literal types in that expression should be widened (e.g. no going from `"hello"` to `string`)
- object literals get `readonly` properties
- array literals become `readonly` tuples

# Usage
- [[ts-enums]]

docs: https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-4.html#const-assertions