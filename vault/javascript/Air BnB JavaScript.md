---
id: pxzli0styd6c4gs9c7417qw
title: Air BnB JavaScript
desc: 'Air BnB JavaScript Style Guide'
updated: 1664385417460
created: 1664384817175
---
# TOC
1. Types
   1.1 Primitives: When you access a primitive type you work directly on its value
    - `string`
    - `number`
    - `boolean`
    - `null`
    - `undefined`
    - `symbol`
    - `bigint`
  ```
  const foo = 1;
  let bar = foo;

  bar = 9;

  console.log(foo, bar); // => 1, 9
```
- Symbols and big ints cannot be faithfully polyfilled, don't use when targeting browsers that don't support them natively

    1.2 Complex: When accessing a complex type you work on a reference to its value
    - `object`
    - `array`
    - `function`
  ```
  // continued from 1.1
  const foo = [1, 2];
  const bar = foo;
  bar[0] = 9;

  console.log(foo[0], bar[0]); // => 9, 9
```
