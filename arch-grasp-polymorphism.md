---
tags:
  - architecture
  - grasp
---
Polymorphism is a fundamental principle in designing how a system is organized to handle similar variations. A design based on assigning responsibilities by Polymorphism can be easily extended to handle new variations. New implementations can be introduced without affecting clients.
## Signs for using Polymorphism
- method contains a lot of if/else
- method contains switch-case
## Related Patterns or Principles
- [[arch-solid-liskov-substitution-principle|LSP]]
- [[arch-solid-open-closed-principle|OCP]]
- [[arch-grasp-protected-variations|Protected Variations]]