
# TypeScript

TypeScript is a superset of JavaScript, providing static checking and additional features. It is often used for larger codebases where static analysis can catch potential errors before runtime.

## Static Checking

Many programming languages, such as Java and Go, incorporate built-in static checking. TypeScript brings this feature to JavaScript by analyzing the code as it is written, enforcing type safety. For static checking, TypeScript utilizes TSX, an extension of JSX, commonly used with React.

```typescript
let user = { name: "sukh", age: 29 };
let email = user.email; // Error: Property 'email' does not exist on type '{ name: string; age: number; }'.
```

In the example above, TypeScript catches the error, providing valuable feedback during development.

## Installation

### Global Installation

Before installing TypeScript, ensure Node.js is installed on your system. Visit the Node.js website to download and install Node.js. Afterward, execute the following command for global TypeScript installation:

```bash
npm install -g typescript
```

This installs TypeScript globally, making the `tsc` command available in the terminal.

## TypeScript Usage

Once TypeScript is installed, you can create TypeScript files with a `.ts` extension. For example:

```typescript
let user = { name: "sukh", age: 10 };
console.log("hello");
console.log(user.age);
```

This code, written in TypeScript, will not run in a production environment. To convert it to JavaScript, use the TypeScript compiler (`tsc`):

```bash
tsc yourfile.ts
```

This compiles the TypeScript code into JavaScript, allowing it to be executed.

##Types : 

there are many types available in the typescript
###number string boolean Null undefined void Object Array Tuples never unknown 

##syntax

```typescript
let varableame: type = value
```









