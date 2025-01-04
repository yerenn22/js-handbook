

# Programming Paradigms

### **1. Major Programming Models**

| **Model**                                         | **Description**                                                                    | **Key Features**                                                   | **Example**                                                    |
|--------------------------------------------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------|---------------------------------------------------------------|
| **Imperative Programming**                       | Code describes a **sequence of steps** to accomplish a task.                      | Loops, conditions, step-by-step approach, mutable data.            | `for (let i = 0; i < arr.length; i++) { sum += arr[i]; }`     |
| **Declarative Programming**                      | Code describes **what needs to be done**, not how.                                | `map`, `filter`, SQL, React (JSX), minimizing side effects.        | `const sum = arr.reduce((acc, val) => acc + val, 0);`         |
| **Structured Programming**                       | Code is organized into logical blocks: sequence, branching, loops.                | Function division, loops instead of `goto`.                        | `if (x > 0) { doSomething(); } else { doSomethingElse(); }`   |
| **Functional Programming**                       | Code is built around functions, avoiding mutations and side effects.              | Pure functions, composition, currying, `map`, `reduce`.            | `const squared = arr.map(x => x ** 2);`                       |
| **Logic Programming**                            | Focuses on rules and facts rather than algorithms. Solutions are inferred logically. | Used in Prolog, relational databases.                              | `man(X) :- human(X), male(X).`                                |
| **Object-Oriented Programming (OOP)**            | Code is organized around objects, their state, and methods.                       | Classes, encapsulation, inheritance, polymorphism.                 | `class Animal { speak() { console.log("Sound"); } }`          |
| **Component-Oriented Programming**               | Code is built from independent and reusable components.                           | Used in React, Angular, Vue.                                       | `<Button text="Click me" />`                                  |


### **2. Approaches and Techniques**

| **Approach/Technique**                          | **Description**                                                               | **Derived from**                | **Example**                                                                                            |
|-------------------------------------------------|-------------------------------------------------------------------------------|---------------------------------|--------------------------------------------------------------------------------------------------------|
| **Structured Programming**                      | Divides code into blocks: sequence, branching, loops.                         | -                               | `if (x > 0) { doSomething(); } else { doSomethingElse(); }`                                            |
| **Procedural Programming**                      | Divides programs into procedures/functions for reuse.                         | Imperative Programming          | `function greet() { console.log('Hello!'); } greet();`                                                 |
| **Applicative Programming**                     | Uses higher-order functions and composition.                                  | Declarative Programming         | `const squaredSum = compose(square, sum);`                                                             |
| **Generic Programming**                         | Uses universal solutions suitable for various data types.                     | -                               | Generics in TypeScript: `function identity<T>(arg: T): T { return arg; }`                              |
| **Recursion**                                   | A function calls itself.                                                      | -                               | `function factorial(n) { return n === 1 ? 1 : n * factorial(n - 1); }`                                 |
| **State Machine Programming**                   | Organizes logic using finite state machines.                                  | -                               | `state = 'idle'; if (event === 'click') state = 'active';`                                             |
| **Event-Driven Programming**                    | Code reacts to events.                                                        | -                               | `document.addEventListener('click', () => console.log('Clicked!'));`                                   |
| **Component-Oriented Programming**              | Code is built from independent components.                                    | -                               | `<Header title="Welcome" />` in React.                                                                |
| **Literate Programming**                        | Code is intertwined with text explaining its purpose.                         | -                               | A narrative description is followed by its implementation, e.g., Jupyter Notebook.                     |


### **3. Key Terms**

| **Term**                         | **Description**                                                                             | **Example**                                            |
|-----------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------|
| **Pure Function**                 | A function that does not modify external data and always returns the same result.          | `const add = (a, b) => a + b;`                        |
| **Data Mutation**                 | Changing data "in place."                                                                  | `arr.push(4); // modifies the array`                  |
| **Immutability**                  | Instead of modifying data, new copies are created.                                         | `const newArr = [...arr, 4]; // creates a new array`  |
| **Currying**                      | Transforming a function into a chain of calls with single arguments.                       | `multiply(2)(3); // 6`                                |
| **Function Composition**          | Combining functions into one larger function.                                              | `compose(f1, f2, f3)(data);`                          |
| **Idempotence**                   | An operation that can be repeated without changing the result.                             | `Math.abs(-10);`                                      |
| **Side Effect**                   | Any change outside the function: logging, modifying global state.                          | `console.log('Logging something');`                   |