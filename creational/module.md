# Module Pattern

The Module pattern is a creational and structural design pattern which simulates the concept of public/ private methods (encapsulation) and avoids polluting the global scope.

## Implementation

```js
// math.js

// Log is not exposed as part of the public `math.js` api
function log(string) {
  if (debug) console.log(string);
}

export default function fibonacci(num) {
  log(num);

  if (num <= 1) return 1;

  return fibonacci(num - 1) + fibonacci(num - 2);
}
```

## Usage

```js
// controller.js
import fibonacci from 'math';

console.log(fibonacci(20)); // 10946
```

## Caveats

- JavaScript has had modules for a long time. However, they were implemented via libraries, not built into the language. ES6 is the first time that JavaScript has built-in modules.
- ES6 modules are stored in files. There is exactly one module per file and one file per module.
