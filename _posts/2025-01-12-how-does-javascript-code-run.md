---
title: How Does JavaScript Code Run?
date: 2025-01-12 22:40:46 +0530
categories: [javascript]
tags: [javascript, deep-dive]     # TAG names should always be lowercase
---

# How JavaScript Works and Execution Context Work

JavaScript is synchronous single threaded language.

- Synchronous => Meaning it can execute only one command at a time. 

### Execution Context 

**Memory [Variable Environment] =>** A place where variable and its value are stored as a key-value pair 

**Code [Thread of execution] =>** Where each piece of code is run synchronously. 

![Execution Context JavaScript](/assets/images/how-does-javascript-code-run/Execution%20Context%20JavaScript.svg)


Let's take a sample code:

```javascript
var n = 2;
function square(num) {
  var ans = num * num;
  return num;
}
var square2 = square(n)
var square4 = sqaure(4)
```



### Phase 1 [**Memory Creation Phase**]

**Memory creation phase** => Allocate memory to variables and function

- Variable memory allocation : Undefined (placeholder) for the variable value 

- Function memory allocation: Stores the entire code.

![Memory Phase](/assets/images/how-does-javascript-code-run/Memory%20Phase.svg)


### Phase 2 [**Code Execution Phase**]

**Code Execution Phase**  **=>** 

```javascript
var n = 2; // Stores the value
function square(num) {
  var ans = num * num;
  return num;
}
var square2 = square(n)
var square4 = sqaure(4)
```

- Line 1 -> store the value for that variable

- Line 2 - 5 -> Nothing to execute as of now as the function hasn't been invoked yet. 

- Line 6 -> Function will be called which will create its own execution context.

    - Memory Phase -> creates `num` and `ans` with undefined as value

    ![Function Memory Execution Context](/assets/images/how-does-javascript-code-run/Function%20Memory%20Execution%20Context.svg)


    - Code Execution Phase

        - Line 2 -> Upon function call `param` is assigned to `num`  (i.e. `n = 2`)

        - Line 3 -> `ans` will be replaced by the value of `num * num` (i.e. 4)

        - Line 4 -> After `return` it will give the result and control back to the parent execution context.

        - After returning the entire execution is deleted

    ![Function Code Execution Phase](/assets/images/how-does-javascript-code-run/Function%20Code%20Execution%20Phase.svg)


- Line 7 -> We have `square` function call with parameter value being `4`. Another entirely new execution phase is created.

    - Memory Phase -> creates `num` and `ans` with undefined as value

    ![Function Memory Execution Context](/assets/images/how-does-javascript-code-run/Function%20Memory%20Execution%20Context.svg)


    - Code Execution Phase

        - Line 2 -> Upon function call `param` is assigned to `num`  (i.e.  4)

        - Line 3 -> `ans` will be replaced by the value of `num * num` (i.e. 16)

        - Line 4 -> After `return` it will give the result and control back to the parent execution context.

        - After returning the result.

        - Entire function level execution context is deleted

    ![Function Code Execution Phase (1)](/assets/images/how-does-javascript-code-run/Function%20Code%20Execution%20Phase%20(1).svg)

- After Line 7 -> The entire program's execution context is deleted.



