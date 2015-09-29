---
layout: post
title: Use console.table()
---
##Use `console.table` to print **nested** objects and arrays to the console. 

```
var me = [
  {
  firstname: "Tim",
  lastname: "Scheys"
  },
  {
  firstname: "Keith",
  lastname: "Anderson"
  },
  {
  firstname: "John",
  lastname: "Yung"
  }
];
console.log(me);
console.table(me);
var fruits = [
  ["apple", "orange", "banana"],
  ["peach", "pear", "melon"]
];
console.log(fruits);
console.table(fruits);
```
The above code will result in the following console messages: 
![console.table() statements](https://tscheys.github.io/images/consoleStatements.png)

As you can see this is approximately 100 times better than a standard `console.log`

This works in Chrome, Firefox and Opera.