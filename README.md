# javascript-imp-concepts

### Scope & Lexical Environment 

Reference: https://dev.to/abdulazizcode/scope-lexical-environment-4pdd

**Chat GPT :**

In JavaScript, a lexical environment is an internal data structure used by the JavaScript engine to track and manage variables and their scopes during the execution of code. It consists of two main components: **an environment record** and a **reference to the outer environment**.

**1. Environment Record**: The environment record is a record of all the variables and functions defined within the current scope. It stores the identifier bindings and their corresponding values. There are different types of environment records, such as declarative environment records (used for variables declared with `let` and `const`) and object environment records (used for variables declared with `var`).

**2. Outer Environment Reference**: The outer environment reference points to the lexical environment of the parent scope. It allows for variable lookup in outer scopes, enabling nested and hierarchical scope resolution.

When a function is invoked, a new lexical environment is created. It consists of the function's local variables, function arguments, and a reference to the outer environment (usually the environment in which the function was defined). This mechanism enables lexical scoping, where variables are resolved based on their position in the source code, regardless of the runtime call stack.

Lexical environments are crucial for understanding variable scoping and closures in JavaScript. Closures are created when inner functions maintain references to variables in their outer lexical environments, even after the outer function has completed execution.

JavaScript engines use lexical environments to ensure proper variable scoping and efficient variable lookup during code execution. They are an essential part of JavaScript's runtime environment.

