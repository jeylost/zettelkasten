---
tags:
  - architecture
  - solid
---
Liskov Substitution Principle(LSP) is a [[arch-solid|SOLID]] principle. 

> A program that using an interface must not be confused by an implementation of that interface.

> Subclass should extend superclass behaviour instead of changing it.

Subclass should be able to easily exchange superclass. And don't break the program. 

When Inheriting class next should be considered:
- Parameters types should be the same or more abstracted
- Methods should return same type value or subtypes
- Methods shouldn’t throw exceptions that isn’t common for super class
- Methods shouldn’t strict pre-conditions more than super class
- Methods shouldn’t weaken post-conditions
- Class invariant should be the same
- Change private fields of base class is prohibited