
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
# map function in typescript 

```typescript
const heros =['skhtiman',"spidormon","ironman"]
heros.map(heros=>{ return `heros is ${heros}`})
```
if we hover over map function it automatically predicts  that hero is going to be the type of string because this array is of type of string 

if we change array 

`heros = [1,2,3]`

it will show us automatically changes the type of array as number 

## but one thing which you should be really careful is the return type of this method 

```typescript
const heros =['skhtiman',"spidormon","ironman"]
heros.map((heros):string =>{
return 1 )
```
here it's give us error because we define the return type as string 

it's a good practice to explicitly mention whoever is using this function knows more about the defination of the funciton
so if the function returns void  that means it's not going to return anything ever 

#### never 
neither it's void because void means return nothing , but there is never as well, which never return a value very close to void but it's use to handle some kind of error 

a function user never as return type, `throw` an exception or terminates execution of the program 

### example 

```ts
function hello(errmsg:string):never{
  throw Error(errmsg)
}
```

## objects

```
const usr ={
    name:"sukh",
    email:"sukh@gmail.com",
    isActive:true
}
```

desigining an object like this doesn't really make sense and you won't be using it too much . the use case of the object is through the functions you have to actullay pass the objects into the funtions or you have to return some objects through the function 

```
function user({name:string, ispaid:boolean}){  
}

user({name:"sukh",ispaid:true})
```

now we can see a function returning a object here it is 
```
createCourse():{}{}
```
the first {} is return type  and second {} is for function defination  


function example 

```
function createCourse():{name:stirng, price:number}{
    return {name:"reactjs",price:300}
}
```


this is not ecceptable 
```
createCourse({name:"sukh",price:233,email:"sukh@gmail.com"})

```
we can only pass the parameters that function accepts this is not allowed 

### odd behaviour (bad behaviour of object) :-
```
let newuser = {name:"sukh",ispaid:false,email:"s@s.com"}

createuser(newuser)
```

here this time i am able to pass much more information than what is expected in the function defination previously it was giving error 


-----------

# type alias

 it’s common to use the same type more than once and refer to it by a single name. it's a keyword in typescript 

```ts
type User ={
    name: string;
    email:string;
    isActive:boolean 
}
```
advantage of craeting a type like this is whenever there are methods like
 ```js
function createUser(user:User):User{
    return {name:"",email:"",isActive:ture}
}

createUser({name:"",email:"",isActive:true})
```  

the return type of the function should also the User


  we want all the information to pass  what we are doing interlly is kind of creating the data types here 


-----------
# read only and optional

readonly is the keyword you can just put it on to anyoene and now you won't be able to change that 
 
```ts
type User ={
    readonly _id: string
    name: string;
    email:string;
    isActive:boolean 
    creditDetail?: number // This property is optional
}

let myUser : User ={
    _id : "123",
    name : "sukh",
    email : "s@gmail.com",
    isActive : ture,
}

// we cam say that 

myUser.email = "sukh@gmail.com"

// but in case of 

myUser._id = 123


```

`creditDetail?: number`
is the syntax to make optional 

---
## array

```ts
/**
 * Array Declarations:
 */

// An array of strings representing superheroes.
const heroes: string[] = [];

// An array of numbers representing the powers of superheroes.
const heroPower: number[] = [];

// An alternative syntax using the Array type to declare an array of numbers representing hero abilities.
const heroAbility: Array<number> = [];

// Adding elements to arrays.
heroes.push("spiderman");
heroPower.push(33);

/**
 * Two-Dimensional Array:
 */

// A two-dimensional array representing colors and numerical values.
const twoDimensionArray: number[][] = [
    [255, 255, 255],
    [24, 2, 3]
];

type User = {
    name: string;
    email: string;
};

// An array of users.
const allUsers: User[] = [];

// Adding a user to the array.
allUsers.push({
    name: "sukh",
    email: "sukh@gmail.com"
});

```
---

## union 

instead of using any its highely recomend to use union datatype , which allows you to be into situation where we are not sure what type of data come in it might be a number or a string a combination of two three or more types of data you can include into a variable or an array 

```ts

let score : number|string = 33

score = "string"

//now score can use either  string or a number
// don't add more than three datatypes 

```
---
## Using Union for types 

```ts

type admin = {
    username : string,
    id : string
}
type user = {
    name : string ,
    password : string
}

//user sukh can be a user and a admin  

let  sukh  : user | admin = {name:'sukh',password:"123"}

```
#### one more example 

```js
function DbConnection(id: string|number)
{
    return console.log(`db id is ${id}`); 
}

DbConnection("3")
DbConnection(2)
```


we can use `|` for make union 

# Union in Arrays
We can use union types in arrays by specifying the valid data types within parentheses and separated by `|`

## Example: Array with Union Types
typescript
```ts
const data3: (string | number | boolean)[] = ["2", "2", 3, true];
```

---
here we can assign `string` `number` `boolean` in array

syntax of using union 

```js
(string|number|...more)
```

---
# tuple

it's just an array a kind of specialized array that is given to us by `typescript` with some restrictions on it 

tuples are used when we want data in precise order usually in `API` call because the `API` structure data is always in a very specific fomat 


```ts
let User :(string|number)[] = ["1",2]

// here is the example of tuple 

let Tuple:[string,boolean,number]=["sukh",true,2]

// we can use push method even we try tuple 
Tuple.push(true)

// at index[0] string index[1] boolean index[2] number 

// we can't chage the order 
```

## enum 


In TypeScript, enums (short for enumerations) allow you to define a set of named constants, making it easier to work with a set of related values. Enums are a way to create a named set of numeric or string constants. Here's a basic overview of how to use enums in TypeScript:



when i hover on the first it's say it's an enum member and the `SeatChoice.first` is having value of zero (0) , it's a default value 
we can change it there maybe need where we want to start from a particular no we just change `first = 10` or any number we want , the next value will be 11, 12 and so on for some reason we can break the series by just put `second = 22` yes it's allowed rest of the values follow up 

---
#### we can assign number strings to enum 
---

what kind of code is being produced when we write this kind of `typescript` into the `javascript` when we compiled as soon as i declared this `enum` and `IIFE` is being created for me given below 

### example 

```ts 
"use strict";
var SeatChoice;
(function (SeatChoice) {
    SeatChoice[SeatChoice["first"] = 0] = "first";
    SeatChoice[SeatChoice["second"] = 1] = "second";
    SeatChoice[SeatChoice["third"] = 2] = "third";
})(SeatChoice || (SeatChoice = {}));
const plainSeat = SeatChoice.first;
console.log(plainSeat);

```

it's generate too much insase amout of crazy code for the javasciprt , in that case we just put `const` before the `enum` and this will not generate crazy code tis will just generate whatever is necessary 

### example

```ts

//adding const

const enum SeatChoice {
    first ,
    second  ,
    third
}

const plainSeat :SeatChoice = SeatChoice.first
console.log(plainSeat)

```
### after compiling 

```js
"use strict";
const plainSeat = 0 /* SeatChoice.first */;
console.log(plainSeat);
```

## Interfaces 

interface is more like a class but lose form of class very broad overview , interface does't have details of how it will work but these are basic overview of that whenever you're creating a user for example these are the fill which are compulsory these are the methods which ae the compulsory now how to implement them that is so totally up to you , `type` and `interface` shares lot of similarity 

#### example syntax 

```ts
interface User{
    readonly dbId : number
    email : string,
    userId : number
    googleid?: string 
}

const sukh:User = {dbId : 22, email:"sukh@gmail.com",
userId:123}

```

we can use `readonly` and `optional :?` in interface also as we discuss these erlier same as that 

#### what really makes interface intersting is the defination of the function 

```ts

interface User{
    startTrail():string
    getCoupon(couponName:string):number
}

const sukh:User = {
startTrail:()=>{
    return "trail is started"
},

getCoupon:(name:"sukh")=>{
return 10
}

}
```

here we don't need to match `couponName` or we can say we write anything we like no need to replicate `name:"sukh"` we are providing it is just a reference that you providing a coupon name which should be string if we give it a number it will show us error , all are the compulsory parameters that we are given in funciton defination

### reopening the interface 

interface also comes with an extension which some people call it as reopening the interface that's nothing just adding more properties into this let's see what reopening is 

### example 
```ts
interface One{
    readonly UserId: string
    emil: string
    isActive : boolean
}
```

we can write user again and it is totally allowed and here we can 

```ts
interface One{
    githubToken : string
}
```

## Inheritance in interface 

extend keyword is used for inheritance you get all the properties that are there for admin but you also have your own see the example given below 

### example 

```ts
interface User{
    name : string
    email : string
    readonly userId: number
}

interface Admin extends User{
    Role : "Student" | "Admin"
}
```

Certainly! Let's improve the formatting and language for better readability:

---

## Difference Between Type Aliases and Interfaces in TypeScript

According to the original `TypeScript` documentation:

### Interfaces:

- **Extending an Interface:** To extend an interface, simply use the `extend` keyword.

    ```typescript
    interface Animal {
        name: string;
    }

    interface Bear extends Animal {
        honey: boolean;
    }
    ```

- **Modifiability:** Interfaces are mutable; you can add new fields to an existing interface after its creation.

### Type Aliases:

- **Extending a Type via Intersections:** When extending a type, you can use intersections.

    ```typescript
    type Animal = {
        name: string;
    }

    type Bear = Animal & {
        honey: boolean;
    }
    ```

- **Immutability:** A type cannot be changed after being created. However, you can add new fields to an existing type.

---

Certainly! Let's enhance the explanation and make the code snippet more readable:

---

# Classes in TypeScript

In TypeScript classes, we can clearly define the types of properties in advance. Consider the following example:

```typescript
class User {
    email: string;
    name: string;

    constructor(email: string, name: string) {
        this.email = email;
        this.name = name;
    }
}
```

Here, we explicitly specify that both `email` and `name` should be of type string.

### Type Declaration in Constructor:

In the constructor, we refer to the predefined types:

```typescript
constructor(email: string, name: string) {
    this.email = email;
    this.name = name;
}
```

This approach ensures that `email` and `name` must be strings when creating an instance of the `User` class.

### Creating an Object:

To instantiate an object from the class, we don't need to specify the parameter names if a constructor is defined:

```typescript
const sukh = new User("sukh@gmail.com", "sukh");
```

With the constructor, we directly provide the string values without the need for explicit parameter names, resulting in cleaner and more concise code.

---

# Public and Private Members in TypeScript Classes

If there's a need to restrict access to certain class members, TypeScript provides the `private` and `public` keywords.

### Private Member:

For instance, if we want to make the `email` property not accessible from outside the class, we can declare it as `private`:

```typescript
class User {
    private email: string;
    name: string;

    constructor(email: string, name: string) {
        this.email = email;
        this.name = name;
    }
}
```

Attempting to access `sukh.email = "sukh"` would result in an error, and hovering over it would show: 
- **Property 'email' is private and only accessible within class User**

### Public Members:

By default, class members (excluding those marked as `private`) are considered `public`. An alternative, more concise way to declare properties is by using shorthand notation in the constructor:

```typescript
class User {
    constructor(public email: string, public name: string) {
    }
}
```

In this shortcut notation, both `email` and `name` are implicitly marked as `public`. This makes the code cleaner and more readable.

---

## getter and setter 


In TypeScript, getter and setter methods allow you to control the access and modification of class properties. You can use the `get` and `set` keywords to define **getter** and **setter** methods within a class.
- Here's an example:

```ts
class MyClass {
    private _myProperty: string = "";
  
    // Getter method
    get myProperty(): string {
      return this._myProperty;
    }
  
    // Setter method
    set myProperty(value: string) {
      if (value.length > 5) {
        this._myProperty = value;
      } else {
        console.log("Value must be longer than 5 characters.");
      }
    }
  }
  
  // Create an instance of MyClass
  const myObject = new MyClass();
  
  // Use the setter method
  myObject.myProperty = "Hello, World!";
  
  // Use the getter method
  console.log(myObject.myProperty); // Output: Hello, World!
  
  // Trying to set a value with length less than 5
  myObject.myProperty = "Hi"; // Output: Value must be longer than 5 characters.
  ```

### NOTE 
- ***a 'set' accessor canot hava a return type annotation***

#### private methods :-

- example 
```typescript 
  class Tokens{
    private deleteToken(){
            console.log("delete")
    }
  }
  const dlt = new Tokens()

  dlt.deleteToken()

// Property 'deleteToken' is private and only accessible within class 'Tokens'.

  ```

  getter and setters are designed so that any private method can be exposed outside but with some additional restrictions 

## class inheritance and protected access modifier 


- **In `TypeScript`, you can use the `extends` keyword to create a class that inherits from another class. This is known as class `inheritance`. The derived class (subclass or child class) inherits properties and methods from the base class (superclass or parent class).**
---

**its only extends the properties and methods that are public or marked as protected in superclass** 

---

```typescript 

  class secondClass extends MyClass{
    myProperties(){
        this._myProperty = "house"
    }
  }
```
Error: Property '_myProperty' is private and only accessible within class 'MyClass'.
Trying to access the private member directly will result in a compilation error. this._myProperty = "house";

Instead, use the public interface provided by the getter and setter:
    `this.myProperty = "house";`
or we just add a `protected` keyword  to access `_myproperty`
in child class 

- Protected properties and methods of the base class are accessible in the derived class.
- They are not directly accessible outside the base class or the derived class.

## abstract classes 

if we declare a class as `abstract` class no new object can be created form this class , they are excatly the blue print for creating an object we need to `extend` it's the responsibilty to create object from this class as `abstract` class we can declare abstract method , abstract function don't have any defination 

---
```ts
abstract class takePhoto{
    constructor(
        public cameraMode : string,
        public takePhoto: string
    ){}
    
    abstract getToken (): void 

    getreeltime():number{
        return 8
    }
}

class instagram extends takePhoto{
    getToken(): void {
        console.log("token is =");
    }
    constructor(
        public  cameraMode: string,
        public takePhoto : string,
        public burstPhoto : number,
    ) {
        super(cameraMode,takePhoto)
    }

}
const sukh = new instagram("vivid","click",3)

```
---

the `super()` keyword is used to call the constructor of the base class (`takePhoto`) within the constructor of the derived class (`Instagram`). This is necessary to ensure that the properties of the base class are properly initialized when creating an instance of the derived class.


## Generics 

Generics in programming refer to a feature that allows you to write functions, classes, and interfaces in a way that they can work with different data types while maintaining type safety. Generics enable you to create flexible and reusable components that can work with a variety of data types without sacrificing type checking at compile time.

#### advantage of using the generics over any is because once we pass the value type is locked for the reference like if i give number as an input the value function accepting is going to be a number and return type also becomes a number automaticlly 

##### syntax for generics funtions :-

```typescript
const indentity = <T>(val:T):T => {
  return val ;
}
indentity(3)
indentity("3")
```

if you want to pass your own data types how we can pass lets' see in the following example 

```typescript 
interface whatsApp {
    messeage: string,
    time : number
}

indentity<whatsApp>({messeage:"hello",time:22.22})

```

more on return type and parameters 

```typescript 
function getKey<t>(val: t[]):t{
    return val[1]
}
```
arrow function syntax 

```typescript 
const getName = <t>(n: t[]): t => {
    return n[1]
}
```

if we are using array as an argument we can use array methods as well 

```typescript
const getData = <T, V>(value: T, value2: V): object => {
    return {
        value
        , value2
    }
}

getData(3,"4")
```

The function `getData` you provided is a generic function in TypeScript, and it takes two parameters of types `T` and `V`, respectively. The function returns an object with properties named `value` and `value2`, using the parameters passed to the function.
