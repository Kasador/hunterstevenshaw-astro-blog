---
title: 'TypeScript'
description: 'Guide to using TypeScript'
pubDate: 'Jul 15 2022'
heroImage: '/typescript.jpg'
---

TypeScript is a strongly typed superset of JavaScript that adds static typing. It helps catch errors early, provides better developer tooling, and improves code readability.

## Why Use TypeScript?

- Catches errors at compile time
- Enables better autocompletion and refactoring
- Makes large codebases easier to maintain
- Encourages documenting with types

---

## Getting Started with TypeScript

### Installation

To install TypeScript globally:

```bash
npm install -g typescript
```

To add it to your project:

```bash
npm install --save-dev typescript
```

---

### tsconfig.json

Initialize TypeScript configuration:

```bash
npx tsc --init
```

A basic `tsconfig.json`:

```json
{
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "jsx": "react-jsx"
  },
  "include": ["src"]
}
```

---

## Basic TypeScript Syntax

### Variable Types

```ts
let count: number = 5;
let name: string = "Hunter";
let isActive: boolean = true;
```

### Arrays and Tuples

```ts
let fruits: string[] = ["apple", "banana"];
let tuple: [string, number] = ["age", 29];
```

### Enums

```ts
enum Direction {
  Up,
  Down,
  Left,
  Right
}
```

### Functions with Types

```ts
function greet(name: string): string {
  return `Hello, ${name}`;
}
```

### Interfaces

```ts
interface User {
  id: number;
  username: string;
}

const user: User = {
  id: 1,
  username: "max"
};
```

---

## TypeScript in React

### Setup in React Project

To create a new React + TypeScript project:

```bash
npx create-react-app my-app --template typescript
```

Or add TypeScript to an existing React project:

```bash
npm install --save typescript @types/react @types/react-dom
```

---

### Functional Component with Props

```tsx
type GreetingProps = {
  name: string;
};

const Greeting: React.FC<GreetingProps> = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};
```

---

### useState with Type

```tsx
const [count, setCount] = useState<number>(0);
```

---

### useRef with Type

```tsx
const inputRef = useRef<HTMLInputElement>(null);
```

---

### Event Handling

```tsx
const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
  console.log(e.target.value);
};
```

---

### useEffect with Cleanup

```tsx
useEffect(() => {
  const timer = setTimeout(() => console.log("Hi!"), 1000);
  return () => clearTimeout(timer);
}, []);
```

---

## React Component Types Summary

| Usage             | Syntax Example                                      |
| ---------------- | -------------------------------------------------- |
| Functional Props  | `type Props = { name: string }`                    |
| FC Component      | `const Comp: React.FC<Props>`                      |
| State Hook        | `useState<number>(0)`                              |
| Ref Hook          | `useRef<HTMLInputElement>(null)`                  |
| Event             | `onChange={(e: React.ChangeEvent<HTMLInputElement>) => {}}` |

---

## Utility Types

```ts
type PartialUser = Partial<User>;       // Makes all props optional
type ReadonlyUser = Readonly<User>;     // Makes all props readonly
type PickUser = Pick<User, "id">;       // Picks just the id
type OmitUser = Omit<User, "id">;       // Omits the id
```

---

## Conclusion

TypeScript improves developer experience in both JavaScript and React. By typing your components and variables, you gain confidence in your code and reduce runtime errors. Over time, it leads to cleaner and more scalable applications.
