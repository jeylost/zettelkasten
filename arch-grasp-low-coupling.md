---
tags:
  - architecture
  - grasp
---
modules/classes/functions should know about the properties of other modules/classes/functions only as much as they need to. The less they know, the more readable your code becomes, and it becomes easier to extend and modify. This principle also relates to defining architecture boundaries.

The middleware concept is a good example of a violation of this principle. Each middleware can modify the HTTP `request`/`response`. Often, middlewares should be executed in a specific order because one middleware can add a new field to the `request` object while another one relies on the existence of this field.
