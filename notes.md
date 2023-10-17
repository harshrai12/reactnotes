#React js NOTES

#### Pure function and impure function differences?
The main difference between pure and impure functions lies in their behavior and the impact they have on the application:

1. **Output Predictability:**
   - Pure functions: Always produce the same output for the same input, ensuring predictability and reliability in the application.
   - Impure functions: Can produce different results for the same input, making the behavior less predictable and potentially causing unexpected issues.h

2. **Side Effects:**
   - Pure functions: Do not cause any side effects, such as modifying variables outside their scope, making network requests, or altering the DOM.
   - Impure functions: Can cause side effects, modifying variables outside their scope, interacting with the DOM, making API calls, or updating global state.

3. **State Management:**
   - Pure functions: Do not directly interact with the application's state, making them ideal for implementing logic that depends solely on the provided input.
   - Impure functions: Often directly interact with the application's state, potentially leading to complex state management and unintended consequences.

4. **Maintainability and Debugging:**
   - Pure functions: Easier to maintain and debug due to their predictable behavior and lack of side effects.
   - Impure functions: Harder to maintain and debug, as their behavior might depend on external factors and they could cause unexpected issues that are difficult to trace.

In the context of React, understanding the distinction between pure and impure functions is crucial for writing efficient and maintainable code. React promotes the use of pure functions, especially when defining components and handling state. This approach helps ensure that the application remains predictable, easy to debug, and performs optimally during rendering.


Pure functions
```javascript
 function greet(name) {
     console.log(`Hello, ${name}!`);
 }
 greet('John');
```
impure function

```javascript
let counter = 0;
const incrementCounter = () => {
  counter++;
  console.log(`Counter value: ${counter}`);
};

```

#### Stateless and Stateful component differences?

In React, components can be broadly classified into two types based on how they handle and manage data: stateless components and stateful components.

1. **Stateless Components (Functional Components):** These components are mainly responsible for presenting UI and accepting props as input. They do not manage any state within themselves and are pure functions of their props. They are generally simpler and more lightweight.

Here's an example of a stateless component in React:

```jsx
import React from 'react';

const Greeting = (props) => {
  return <div>Hello, {props.name}!</div>;
};

export default Greeting;
```

2. **Stateful Components (Class Components or Components with Hooks):** These components manage their own state and can have more complex logic. They are used when a component needs to manage and maintain its own data that can change over time.

In the above example, the `Counter` component maintains its own `count` state and provides a method to update it.

In recent versions of React, with the introduction of hooks, functional components can also manage state. Here's an example of a stateful component using hooks:

```jsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={incrementCount}>Increment</button>
    </div>
  );
};

export default Counter;
```

In this example, the `Counter` component uses the `useState` hook to manage the `count` state and provides a method to update it.

Understanding the differences between stateless and stateful components is crucial in React development as it helps in making informed decisions about how to structure and manage components in your application.
