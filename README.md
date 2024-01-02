
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

## Types : 

## Types

In TypeScript, there are various types that you can use:

- `number`
- `string`
- `boolean`
- `Null`
- `undefined`
- `void`
- `Object`
- `Array`
- `Tuples`
- `never`
- `unknown`

## syntax

```typescript
let varableame: type = value
```
### example

```typescript
let greeting: string = "hello ji"
console.log(greeting)
```
Running the file with `tsc` will create a new JavaScript file. To avoid the error "cannot redeclare block-scoped variable 'greetings'", add `exports {}` at the end of the file.


later on if we assign number to the greeting it's not allowed in the typescript 
and if we add dot . in greetings it's show all the methods of the string it's actuaclly gives suggestions if we write wrong in methods 

#number 

how to define no 

```typescript
let userId: number = 333333
```
use `userId.` and use any method suggested there 
like `userId.toFixed()`

even you don't need to put : everytime ts is smart enough to detect the type 

if we simply use 

```typescript
let userId = 33333
```
### it's automatically detects its a number 

#boolean 

```typescript
let isloogedIn: boolean = false
```

# any 
## it's a not a good practise to use any keyword 

### exmple here
```typescript

let hero ;
function getHero(){
return "shaktimaan"
}
hero = gethero()

// here when we hover on the hero it's show's the type as any
we relly want to avoid these cases 
```
### when in such situations where typescript can-not find out what value came up later on in future , it puts that as any which is a kind of a gateway from doing the things any is used whenever you don't want a particular value to cause typechecking errors. it's is  not a special type we assign not a string not a boolean it's simply a marker in the TS it's basically of the typechecking 


```typescript

let hero: string ;
function getHero(){
return "shaktimaan"
} 
hero = gethero()

```

# how functions are defined ?

### example : - 
```typescript 
function addTwo(num){
return num +2 
}
addTwo(5)
```
it might be ok we add a number to it 
but the problem is if we hover over it it show us --any--

 ```typescript 
function addTwo(num){
num.toUpperCase()
return num +2 
}
addTwo(5)
```
### like here we can simply assign values like toUpperCase() to  a number 

in the case of variables , it's optional , it infers 
the type really nicely so there is no problem , in the case of functions, it is really compulsory to define the type

## if we have multiple parameters we are simply define type to the individuls
like we done in signUpUser funciton given below :

```typescript
function signUpUser(name: string , email: String, password:string ){
 console.log(name,password,email)
}

signUpUser("sukh","sukh@email.com","1234")
```

### if we want to pass only two values ? how can we pass the default value ?

```typescript 
function signUpUser(name: string , email: String, isPaid:boolean = false ){
    console.log(name,isPaid,email)
   }
   
   signUpUser("sukh","sukh@email.com")
```

simply provide the default value 
here is the new question arrived 
see the following code 

```typescript 
function addTWo(num: number){
    return "hello"
}
addTWo(6)
```
here we can't get any error which is concern for us this will break entire application since we return a string that's why typescript used 

**how to solve ?** 
```typescript
 function add(num:number):number{
    return "hello"

//we can't just return string here

   }
   console.log(add(2))
```

**how we do it in an arrow function ???**

-`here is how :-`

```typescript
 const getHello(s:string):string => {
 return "" }
```



 
























