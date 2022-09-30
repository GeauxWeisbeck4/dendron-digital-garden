---
id: ktoj3necwp5wb2sdqtrp0il
title: Eslint
desc: 'ESlint notes'
updated: 1664425707489
created: 1664425274249
---
# ESLint
Find and fix problems in your JS code - analyzes yoru code and quickly finds problems
* ESLint uses Espree for JavaScript parsing.
* ESLint uses an AST to evaluate patterns in code.
* ESLint is completely pluggable, every single rule is a plugin and you can add more at runtime.

```
$ npm init @eslint/config

// after initializing you can run ESLint on any file or directory:

$ npx eslint yourfile.js

# or

$ yarn run eslint yourfile.js
```


### [Espree](https://github.com/eslint/espree)
-ESLint relies on Esprima's tokens and comment attachment features
