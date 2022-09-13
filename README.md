# dex-burst-typescript-workshop

Sample code

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
function exampleFunction(name: string) {
  return "Hello" + name;
}

const arrowFunction = () => {
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
  name: 'Tyler',
  color: 'red',
};

console.log(user.name)

// destructuring
const { name, color } = user
console.log(occupation)

// spread
const fullUser = {
  ...user
  company: 'Shopify
}
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

```
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




### Async

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


