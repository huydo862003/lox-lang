# Lox Programming Language

![Status](https://img.shields.io/badge/status-on--hold-orange)

Implementations of the Lox programming language from [Crafting Interpreters](https://craftinginterpreters.com/) by Robert Nystrom, with modifications to the grammar and semantics.

## Implementations

| Implementation | Language | Description |
| -------------- | -------- | ----------- |
| [jlox](jlox/README.md) | Java | Tree-walking interpreter |
| [clox](clox/) | C | Bytecode virtual machine (in progress) |

## Language Features

- Dynamic typing
- First-class functions and closures
- Classes with single inheritance
- Lexical scoping
- Automatic memory management

## Modifications from Original Lox

- JavaScript-style temporal dead zone for variables
- `super` keyword for superclass method access
- All values are objects (including primitives)
- Built-in `toString()` method on all types

## Building

### jlox

```bash
cd jlox
make
java -cp . com.craftinginterpreters.lox.Lox [script.lox]
```

### clox

```bash
cd clox
make
./clox [script.lox]
```

## Example

```lox
class Animal {
  fun constructor(name) {
    this.name = name;
  }
  fun speak() {
    print this.name + " makes a sound";
  }
}

class Dog < Animal {
  fun constructor(name) {
    super(name);
  }
  fun speak() {
    print this.name + " barks";
  }
}

var dog = Dog("Buddy");
dog.speak(); // Buddy barks
```

## References

- [Crafting Interpreters](https://craftinginterpreters.com/) - The book this project is based on
