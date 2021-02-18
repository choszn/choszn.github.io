---
category: code
layout: post
title: "TypeScript Guide"
date:   2021-2-13 16:58:41 -0800
tags: [💧, js]
---

# TypeScript Guide

Variable syntax:

{name of variable} : {name of type} = {value of variable}

TypeScript types:

1. any -- can be anything
2. Built-in -- 
   1. *number*
   2. *string*
   3. *boolean*
   4. *void*
   5. *null*
   6. *undefined*
3. User-defined
   1. *enum*
   2. *class*
   3. *interface*
   4. *array*
   5. *tuple*

```typescript
let myVariable: any = 'This is a string'
let num: number = 5;  
let name: string = 'Alex';  
let isPresent: boolean = true;
```

```typescript
class Car {

// fields  
  model: String;  
  doors: Number;  
  isElectric: Boolean;

constructor(model: String, doors: Number, isElectric: Boolean) {  
    this.model = model;  
    this.doors = doors;  
    this.isElectric = isElectric;  
  }

displayMake(): void {  
    console.log(`This car is ${this.model}`);  
  }

}
```

To make a new instance of class Car:

```typescript
const Prius = new Car('Prius', 4, true);  
Prius.displayMake(); // This car is Prius
```

