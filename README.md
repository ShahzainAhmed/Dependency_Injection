## Dependency Injection in Flutter

### What is Dependency Injection?

DI is a design pattern in which a class requests dependencies from external sources rather than creating them. It means the dependent objects are injected or supplied to your class. The class doesn’t have to do any initialization by itself. It will get what it wants from the injector.

### Loose coupling: 
When an object gets the object to be used from external sources, we call it loose coupling. In other words, the loose coupling means that the objects are independent.

### Tight coupling: 
When a group of classes is highly dependent on one another, it is called tight coupling.

Dependency injection is one of the most practical design patterns that allow developers to write loosely coupled code. It also helps to keep our code more testable.

### Example:

When some class Jungle needs class Animal to perform its operation, class Jungle is called Dependent, and class Animal is called Dependency.

```
class Jungle {
  Animal _animal = Animal();

  void check() {
    _animal.who();
  }
}

class Animal {
  void who() {
    print("I am an animal.");
  }
}

void main() {
  Jungle jungle = Jungle();
  jungle.check(); // prints "I am an animal."
}
```
