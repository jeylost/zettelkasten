---
tags:
  - architecture
  - grasp
---
GRASP - General responsibility assignment software patterns

> [!INFO]
> First was proposed by Craig Larman in his book "Applying UML and Patterns"

## Principles
- [[arch-grasp-low-coupling|Low Coupling]]
- [[arch-grasp-information-expert|Information Expert]]
- [[arch-grasp-controller|Controller]]
- [[arch-grasp-pure-fabrication|Pure Fabrication]]
- [[arch-grasp-protected-variations|Protected Variations]]
- [[arch-grasp-high-cohesion|High Cohesion]]
- [[arch-grasp-creator|Creator]]
- [[arch-grasp-polymorphism|Polymorphism]]
- [[arch-grasp-indirection|Indirection]]

### Creator
Problem: Who should create instance(who should hold and destroy link)

Solution: Who contains or aggregate instances, who use them heavily, who has all the information for initialization.

Why: to low coupling

Examples: constructor, factory, pool
