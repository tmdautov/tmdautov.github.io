---
title: "What is Hoisting"
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["js-theory"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: true
description: "What is Hoisting in JavaScript"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

# Hoisting

> Hoisting is a Javascript default behavior of moving functions, variables or classes declarations on top of the module/function level scope before executing the code.

In hoisting, it seems that the declaration has moved up in the program, the actual thing that happens is that the `function and variable declarations are added to memory during the compile phase`.

## Variables Hoisting

**var**

Variables declared with `var` are hoisted to the top of the function or global scope with a value of `undefined`.

```js
console.log(a); // undefined
var a = 5;
console.log(a); // 5
```

**let and const**

Variables declared with `let` and `const` are also hoisted, but they remain in a "temporal dead zone" until the line where they are declared, meaning you can't access them before their declaration line.

```js
// console.log(b); // Throws an error: Cannot access 'b' before initialization
let b = 10;
console.log(b); // 10
```

## Function Hoisting

It's essential to understand the difference between `function declaration` and `function expression`.

**Function declaration**
Function declarations are hoisted to the top of their scope with their body.

```js
foo(); // Outputs: "Hello!"
function foo() {
  console.log("Hello!");
}
```

**Function expression**
Function expressions, on the other hand, are not hoisted because they involve variable initializations. The variable declaration will be hoisted, but the assignment of the function to the variable will not.

```js
// bar(); // Throws an error: bar is not a function
var bar = function () {
  console.log("Hello from bar!");
};
bar(); // Outputs: "Hello from bar!"
```

## Summary

- Hoisting is a Javascript default behavior of moving functions, variables, or classes declarations on top of the scope before executing the code.
- Variables hoisting: var/let/const
- Function declaration are hoists while function expressions are not
- Declare and initialize variables and functions at the top of their scope
