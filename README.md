# javascript-imp-concepts

### Scope & Lexical Environment 

**Lexical Environment :**

In JavaScript, a lexical environment is an internal data structure used by the JavaScript engine to track and manage variables and their scopes during the execution of code. It consists of two main components: **an environment record** and a **reference to the outer environment**.

**1. Environment Record**: The environment record is a record of all the variables and functions defined within the current scope. It stores the identifier bindings and their corresponding values. There are different types of environment records, such as declarative environment records (used for variables declared with `let` and `const`) and object environment records (used for variables declared with `var`).

**2. Outer Environment Reference**: The outer environment reference points to the lexical environment of the parent scope. It allows for variable lookup in outer scopes, enabling nested and hierarchical scope resolution.

When a function is invoked, a new lexical environment is created. It consists of the function's local variables, function arguments, and a reference to the outer environment (usually the environment in which the function was defined). This mechanism enables lexical scoping, where variables are resolved based on their position in the source code, regardless of the runtime call stack.

Lexical environments are crucial for understanding variable scoping and closures in JavaScript. Closures are created when inner functions maintain references to variables in their outer lexical environments, even after the outer function has completed execution.

JavaScript engines use lexical environments to ensure proper variable scoping and efficient variable lookup during code execution. They are an essential part of JavaScript's runtime environment.

Sure! Let's consider an example to illustrate how lexical environments work in JavaScript:

```javascript
function outer() {
  var outerVariable = 'I am from the outer function';

  function inner() {
    var innerVariable = 'I am from the inner function';
    console.log(outerVariable); // Accessing outerVariable from the outer lexical environment
    console.log(innerVariable); // Accessing innerVariable from the inner lexical environment
  }

  inner(); // invoking the inner function
}

outer(); // invoking the outer function
```

In this example, we have an outer function called `outer` that defines a variable `outerVariable` and an inner function called `inner` that defines a variable `innerVariable`. 

When the `outer` function is invoked, a new lexical environment is created for that invocation. It includes the `outerVariable` variable and a reference to the outer environment, which in this case is the global environment (or any other outer scope if `outer` was nested within another function).

Inside the `outer` function, we define the `inner` function. When `inner` is invoked within the `outer` function, a new lexical environment is created for that invocation as well. It includes the `innerVariable` variable and a reference to the outer environment, which is the lexical environment of the `outer` function.

Within the `inner` function, we can access both the `outerVariable` from the outer lexical environment and the `innerVariable` from the inner lexical environment. This is possible because each function maintains a reference to its outer lexical environment, allowing for nested scope resolution.

By utilizing lexical environments and the concept of closures, the `inner` function can access and use variables from its outer scope, even after the `outer` function has finished executing.

So, when we run the code, it will print:

```
I am from the outer function
I am from the inner function
```

This demonstrates how lexical environments enable variable scoping and the ability to access variables from different levels of nested functions.


Reference: 
https://dev.to/abdulazizcode/scope-lexical-environment-4pdd
https://javascript.plainenglish.io/scope-chain-and-lexical-environment-in-javascript-eb1f6e60997e
