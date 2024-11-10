---
tags:
  - css
---

By default, the `min-width` and `min-height` properties for flex items are not set to `0`. Instead, they are equal to the minimum size required for the content to be fully displayed. This behavior ignores the defined `min-width` and `min-height` of the parent element.

To address this, you can manually set `min-width` or `min-height` to `0`. It's important to review all flex items in the HTML structure—both up and down—to determine if they require an override for `min-width`, `min-height`, or overflow properties.

## References

- [Automatic Minimum Size of Flex Items](https://www.w3.org/TR/css-flexbox-1/#min-size-auto).
- [Stack Overflow issue](https://stackoverflow.com/questions/36247140/why-dont-flex-items-shrink-past-content-size).
