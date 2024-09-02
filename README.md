### Dependency Injection in Flutter

### What is Dependency Injection?

Dependency Injection is a design pattern in which a class requests dependencies from external sources rather than creating them. It means the dependent objects are injected or supplied to your class. The class doesn’t have to do any initialization by itself. It will get what it wants from the injector.

### Loose coupling: 
When an object gets the object to be used from external sources, we call it loose coupling. In other words, the loose coupling means that the objects are independent.

### Tight coupling: 
When a group of classes is highly dependent on one another, it is called tight coupling.

Dependency injection is one of the most practical design patterns that allow developers to write loosely coupled code. It also helps to keep our code more testable.

### Example:

When some class Jungle needs a class Animal to perform its operation, class Jungle is called Dependent, and class Animal is called Dependency.

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

- In the above example, our class, Jungle, is tightly coupled. It means the class Jungle is highly dependent on the dependency Animal.
- If we want to add a new animal Tiger, then there is no way to change the animal to Tiger as we have hardcoded Jungle and Animal classes.

Now using dependency injection to solve our problem.

```
void main() {
  final tiger = Tiger();
  final jungle = Jungle(tiger);
  jungle.check(); // prints "I am tiger."
}

class Jungle {
  final Animal _animal;

  Jungle(this._animal);

  void check() {
    _animal.who();
  }
}

class Animal {
  void who() {
    print('I am an animal.');
  }
}

class Tiger implements Animal {
  @override
  void who() {
    print('I am a tiger.');
  }
}
```
