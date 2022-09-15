# dex-burst-typescript-workshop

### Exercise: Part 1

1) Create a new node project and install typescript
2) Create a new file `DeliveryPromiseService.ts`
3) Write a program that will return a delivery date for a given zip

   - _Parse the sample file_
   - _Define an interface for a schedule_
   - _return a delivery date for a given zip_

4) Test the program, using Jest
    - _Install with:_ `npm i jest ts-jest @types/jest`
    - _Configure typescript with:_ `npx ts-jest config:init`
    - _run test files with:_ `npx jest <file>` _(hint: add to your package.json)_
    - https://jestjs.io/docs/getting-started
    - https://jestjs.io/docs/asynchronous

### Exercise: Part 2

1) Setup a Koa server
2) Expose an API endpoint to get a promise date for a zip code
3) Add middleware to log the request
4) Add a new POST endpoint to add a promise to a schedule


Sample code below:

### Setup
```node
// start a project
npm init

// install packages
npm install typescript

// initialize typescript
npx tsc --init

// compile typescript to javascript
npx tsc index.ts

// execute javascript
node index.js
```

### package.json

`start: npx tsc & node index.js`

### Primitives

```ts
const color = "red";
const isTrue = true;
const favNumber = 120;

// redefining variables
let color2 = "blue";
color2 = "green";
```


### Strings
```ts
// Single quotes, or double quotes
const first = "Tyler";
const last = 'Post';

// String interpolation uses backticks and $
const myName = `My name is ${first} ${last}.`;
```

### Functions
```ts
function exampleFunction(name: string): void {
  "Hello" + name;
}

const arrowFunction = (): string => {
  return "Hello world";
}

const arrowFnImplicit = (name: string) => `Hello ${name}`;
```


### Iteration
```ts
const numbers = [1, 2, 3];

numbers.forEach((number) => {
  console.log(number)
});

numbers.map(number => number + 1)
```


### Objects
```ts
const user = {
  firstName: 'Tyler',
  color: 'red',
};

console.log(user.firstName)

// destructuring
const { firstName, color } = user;
console.log(firstName);

// spread
const fullUser = {
  ...user
  company: 'Shopify
};

//shorthand
const myKey = "asdf";
const myObject = { mykey, }

```


### Import/Export

By default everything is private to a module (file)
```ts
// file1.ts
export const myFunction = () => "Hello World"
```

```ts
// index.ts
import { myFunction } from './file1'
```

### Classes

```ts
class Car
  color: string
  
  constructor(color: string) {
    this.color = color
  }
  
  getColor() {
    return this.color
  }
  
  public static getClassName() {
    return "CAR"
  }
  
  private method2() {
    ...
  }
}

const myCar = new Car('red')
```

### Typescript

```ts
// Enums
export enum Color {
  Red = "red",
  Blue = "blue"
}

// Union Types
export type vehicles = 'car' | 'bus' | 'truck';

// Interfaces
export interface User {
  name: string;
  color: Color;
  vehicle?: vehicle
}

// Type Generics
// Usually represented by <T>, possibly <T, U, V>
Array<T>

// escape hatches
function(arg1: any) {
  return arg1 as any;
}
```

### Async


Javascript code doesn't necessary execute in the order of the lines
```ts
const asnycExample = () => {
  console.log(1)
  
  setTimeout(() => {
    console.log(2),
  }, 0)

  console.log(3)
}

asnycExample()
```

Promises represent a value that will eventually be resolved.
The `.then` and `.catch` methods allow us to process results of promises
```ts
import axios from 'axios'
function getUsers() {
  axios.get("https://reqres.in/api/users")
    .then((reponse) => {
      console.log(response.data)
    })
    .catch((error) => {
      console.log(error.response.data)
    })
}

// You can also handle promises with the Async keyword
async function getUsers2() {
  try {
    result = await axios.get("https://reqres.in/api/users")
    console.log(result.data)
  } catch (e) {
    console.log(e.response.data)
  }
}


// Use Promise.all to process multiple things at the same time
async function asnycExample4() {
  const [res1, res2] = await Promise.all([
    axios.get('https://reqres.in/api/users/1'),
    axios.get('https://reqres.in/api/users/2')
  ]);
}
```


### Reading files
```
import fs from 'fs';

async function main() {
  const fileContents = await fs.promises.readFile('./content.txt')
  console.log(fileContents.toString())
}

main().catch(err => console.log(err))
```




### Setup Koa
`npm i koa @types/koa`

```ts
import Koa from 'koa'
const app = new Koa();

app.use((ctx) => {
  ctx.body = "Hello World"
})

app.listen(3000)
```

`npm i @koa/router @types/koa__router`

```ts
import Router from @koa/router
const router = new Router()

router.get('/hello', (ctx) => {
  ctx.body = 'World'
})

app.use(router.routes)
```






