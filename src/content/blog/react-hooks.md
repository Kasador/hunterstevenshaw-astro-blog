---
title: 'React Hooks'
description: 'Guide to using React Hooks'
pubDate: 'Jun 01 2024'
heroImage: '/react-hooks.png'
---

React Hooks allow you to use state and other React features in functional components. They simplify component logic and remove the need for class components in most scenarios.

## What Are Hooks?

Hooks are special functions that let you “hook into” React features. They start with the word `use` and can only be used inside functional components.

---

## 1. `useState`

Allows you to add local state to functional components.

```javascript
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

---

## 2. `useEffect`

Performs side effects like fetching data or subscribing to events.

```javascript
import { useEffect } from 'react';

function Timer() {
  useEffect(() => {
    const interval = setInterval(() => {
      console.log('Tick');
    }, 1000);

    return () => clearInterval(interval); // Cleanup
  }, []);
}
```

---

## 3. `useContext`

Allows you to use the value from a React context.

```javascript
import { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

function ThemedComponent() {
  const theme = useContext(ThemeContext);
  return <div style={{ background: theme.background }}>Hello</div>;
}
```

---

## 4. `useRef`

Returns a mutable ref object that persists for the lifetime of the component.

```javascript
import { useRef } from 'react';

function InputFocus() {
  const inputRef = useRef();

  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>
        Focus Input
      </button>
    </>
  );
}
```

---

## 5. `useMemo`

Memoizes a computed value to optimize performance.

```javascript
import { useMemo } from 'react';

function ExpensiveComponent({ number }) {
  const squared = useMemo(() => {
    return number * number;
  }, [number]);

  return <div>{squared}</div>;
}
```

---

## 6. `useCallback`

Returns a memoized callback function.

```javascript
import { useCallback } from 'react';

function Button({ onClick }) {
  const handleClick = useCallback(() => {
    onClick();
  }, [onClick]);

  return <button onClick={handleClick}>Click</button>;
}
```

---

## 7. `useReducer`

An alternative to `useState` for complex state logic.

```javascript
import { useReducer } from 'react';

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <>
      <p>{state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>
        +
      </button>
    </>
  );
}
```

---

## Rules of Hooks

- Only call hooks at the top level of your component.
- Only call hooks from React function components or custom hooks.
- Do not call hooks inside loops, conditions, or nested functions.

---

## Summary Table

| Hook         | Description                          |
| ------------ | ------------------------------------ |
| `useState`   | Adds local state                     |
| `useEffect`  | Side effects, like fetching data     |
| `useContext` | Consumes context values              |
| `useRef`     | Persists mutable values              |
| `useMemo`    | Caches calculated results            |
| `useCallback`| Caches function definitions          |
| `useReducer` | For advanced state logic             |

---

React Hooks make your code cleaner and more modular. By embracing functional components with hooks, you can write modern, maintainable React applications.
