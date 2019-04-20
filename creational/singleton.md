# Singleton Pattern

Singleton creational design pattern restricts the instantiation of a class to a single object.

## Implementation

```js
class Singleton {
  constructor() {
    console.log(Singleton.instance)
    if (!!Singleton.instance) {
      return Singleton.instance
    }

    Singleton.instance = this
  }
}
```

## Usage

```js
const i = new Singleton()
const j = new Singleton()

console.log(i) // Singleton {}
console.log(j) // Singleton {}

console.log(i === j) // true
```

## Caveats

- Singletons represent a global state and may reduces testability.
