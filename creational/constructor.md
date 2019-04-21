# Constructor Pattern

The constructor pattern allows you to create multiple instances of the same object.

## Implementation

```js
const Person = function(name, age) {
  this.name = name;
  this.age = age;

  this.sayName = () => {
    return `Hello, my name is ${this.name}`;
  };
};
```

## Usage

```js
const jane = new Person('Jane', 28);
const john = new Person('John', 32);

console.log(jane instanceof Object); // true
console.log(john instanceof Object); // true

console.log(jane instanceof Person); // true
console.log(john instanceof Person); // true

console.log(jane.sayName === john.sayName); // false
```

## Caveats

- Methods are created for each instance by constructors. Both `jane` and `john` have a method called `sayName`, but those methods are not the same instance of Function. It is possible to work around this limitation by moving the function definition outside of the constructor.
