# Object Orientated Programming

OOP is a programming paradigm that revolves around the concept of objects, which are instances of classes. It provides a way to organize code into reusable and modular structures, making it easier to manage and maintain larger software systems. OOP focuses on four main principles: encapsulation, inheritance, abstraction, and polymorphism.

[Back to main](../Index/index.md)

## Table of Contents

[Sources and Further Reading](#sources)

---

## Class

>A class is like a blueprint or a recipe that tells you how to create something. For example, a class called "Car" would tell you how to build a car.

A class is a blueprint or a template that defines the structure and behavior of objects. It encapsulates data (attributes) and behaviors (methods) that objects of that class can have. Objects are instances of a class.

## Object

>An object is like a thing you can see and touch, such as a toy or a pet. In programming, an object is like a thing that can store information and do things based on its characteristics.

An object is an instance of a class. It represents a specific entity or concept. Objects have state (attribute values) and behavior (methods) defined by the class they belong to. You create objects from a class and work with them to perform various operations.

## Constructors

>Constructors are like special magic words that make an object come to life. When you create an object, constructors are there to give it the right starting values.

Constructors are special methods that are used to initialize objects of a class. They are called when an object is created. Constructors typically set initial values for the object's attributes or perform other setup operations.

## Method

>A method is like a special ability or action that an object can do. It's like a superpower that allows the object to perform specific tasks.

A method is a function defined within a class. It represents the behavior or actions that objects of that class can perform. Methods can manipulate the object's data and interact with other objects or the system.

## Access Modifiers

>Access modifiers are like security guards that decide who can enter certain places. They control whether others can see or use the things inside a class.

Access modifiers (e.g., public, private, protected) determine the accessibility of class members (attributes and methods) from other parts of the program. They enforce encapsulation and define the level of visibility and interaction with class members.

## Association, Aggregation, and Composition

>Association is like having friends you can hang out with, aggregation is like having Lego blocks that you can put together to build something, and composition is like having organs that make up a body and cannot exist independently.

These are different types of relationships between classes:

* Association: Represents a relationship where objects of one class are connected to objects of another class.

* Aggregation: Represents a "has-a" relationship, where objects of one class contain objects of another class as parts.

* Composition: Stronger form of aggregation, where the composed object cannot exist independently without the container object.

## The Four Pillars

### Encapuslation

>Encapsulation is like keeping a secret diary. You can write things in it and lock it with a key. Only you can access or change what's inside, and others can only see what you choose to show them.

Ecapsulation involves creating a "capsule" or module. In OOP, it refers to the bundling of data and methods (or functions) that operate on that data within a single unit, called an object. It allows you to hide the internal implementation details of an object and expose only the necessary interfaces or methods to interact with it. Encapsulation provides benefits like data protection and code organization, promoting code reuse and making it easier to maintain and understand.

#### **Methods to achieve Encapsulation**

Access Modifiers
    : Access modifiers, such as public, private, and protected, control the visibility and accessibility of class members (attributes and methods) from other parts of the program. By using appropriate access modifiers, you can restrict access to certain members, making them private and accessible only within the class itself. This ensures that the internal implementation details are hidden from external access, promoting encapsulation.

```typescript
class Person {
  private _age: number; // Private member

  constructor(public name: string) {
    this._age = 0;
  }

  get age(): number {
    return this._age;
  }

  set age(value: number) {
    if (value >= 0 && value <= 120) {
      this._age = value;
    } else {
      console.log("Invalid age!");
    }
  }
}

const person = new Person("John");
person.age = 25;
console.log(person.age); // Output: 25
person.age = 150; // Output: Invalid age!

```

Getters and Setters
    : Getters and setters, also known as accessor and mutator methods, provide controlled access to the private attributes of a class. Getters allow other parts of the program to retrieve the values of attributes, while setters allow modification of those values. By encapsulating the attributes and providing public methods to access and modify them, you can enforce data encapsulation and maintain control over how the attributes are accessed and modified.

```typescript

class Circle {
  constructor(private radius: number) {}

  get area(): number {
    return Math.PI * this.radius * this.radius;
  }

  set diameter(value: number) {
    this.radius = value / 2;
  }
}

const circle = new Circle(5);
console.log(circle.area); // Output: 78.53981633974483
circle.diameter = 10;
console.log(circle.area); // Output: 78.53981633974483

```

Data Validation
    : Encapsulation involves protecting the integrity of the data within a class. To achieve this, you can implement data validation logic within the setters or separate validation methods. This ensures that the data being set meets certain criteria or constraints. By validating and controlling the data from within the class, you maintain the integrity and consistency of the object's state.

```typescript

class BankAccount {
  private _balance: number;

  constructor(public accountNumber: string) {
    this._balance = 0;
  }

  get balance(): number {
    return this._balance;
  }

  set balance(value: number) {
    if (value >= 0) {
      this._balance = value;
    } else {
      console.log("Invalid balance!");
    }
  }
}

const account = new BankAccount("123456789");
account.balance = 1000;
console.log(account.balance); // Output: 1000
account.balance = -500; // Output: Invalid balance!

```

Information Hiding
    : Encapsulation aims to hide the internal details and implementation of a class. To achieve information hiding, you can expose only the necessary interfaces or public methods that allow other parts of the program to interact with the object. By hiding the implementation details, you maintain control over how the object's methods are used, providing a clear and well-defined interface for external interactions.

```typescript
class Product {
  constructor(public name: string, private _price: number) {}

  calculateFinalPrice(): number {
    return this._price * 1.1;
  }
}

const product = new Product("Book", 20);
console.log(product.name); // Output: Book
console.log(product._price); // Error: Property '_price' is private
console.log(product.calculateFinalPrice()); // Output: 22
```

Immutable Objects
    : Creating immutable objects is another way to achieve encapsulation. Immutable objects are those whose state cannot be modified once they are created. By making the attributes of a class immutable, you eliminate the risk of unwanted changes or side effects. Immutable objects ensure that the object's state remains consistent and cannot be altered externally, promoting encapsulation.

```typescript
class ImmutablePerson {
  constructor(private readonly name: string, private readonly age: number) {}

  getName(): string {
    return this.name;
  }

  getAge(): number {
    return this.age;
  }
}

const person = new ImmutablePerson("John", 25);
console.log(person.getName()); // Output: John
console.log(person.getAge()); // Output: 25

// Trying to modify the object will result in an error
person.name = "Jane"; // Error: Cannot assign to 'name' because it is a read-only property
person.age = 30; // Error: Cannot assign to 'age' because it is a read-only property

```

### Inheritance

> Inheritance is like passing down family traits. Children inherit characteristics from their parents, like hair color or height. In programming, it's similar. A class can inherit properties and behaviors from another class.

Inheritance is a mechanism in OOP where one class inherits properties and methods from another class, known as the parent or base class. The class that inherits is called the child or derived class. Inheritance facilitates code reuse and promotes the concept of hierarchical relationships between classes. By inheriting from a base class, the child class gains access to its attributes and behaviors, allowing you to extend or modify them as needed. This way, you can create specialized classes that inherit common features from a more general class. For example, you could have an "Animal" base class with common attributes and behaviors, and then specific animal classes like "Lion" or "Elephant" that inherit from it.

### Abstraction

> Abstraction is like using a remote control. You don't need to know how it works inside. You only need to know how to press the buttons to make it do what you want.

Abstraction refers to the process of simplifying complex systems by breaking them down into smaller, more manageable units. In the context of OOP, abstraction is achieved through abstract classes and interfaces. An abstract class is a class that cannot be instantiated directly but serves as a blueprint for its derived classes. It can contain both concrete and abstract methods. Abstract methods are declared but not implemented in the abstract class, leaving the implementation details to the derived classes. On the other hand, an interface is a contract that defines a set of methods that a class must implement. It provides a way to achieve multiple inheritance in languages that don't support it directly. Both abstract classes and interfaces promote code modularity, allowing you to define common behaviors or contracts that different classes can adhere to.

### Polymorphism

>Polymorphism is like a shape-shifting power. It allows objects to change their form and behavior, adapting to different situations or roles.

Polymorphism refers to the ability of objects to take on different forms or exhibit different behaviors depending on the context. In OOP, polymorphism allows you to write code that can work with objects of different classes, as long as they share a common interface or base class. This is achieved through method overriding and method overloading. Method overriding occurs when a derived class provides its own implementation of a method inherited from the base class. This allows you to use the same method name but customize the behavior based on the specific class. Method overloading, on the other hand, involves having multiple methods with the same name but different parameters within a class. The appropriate method to be called is determined by the number and types of arguments provided. Polymorphism enhances flexibility and extensibility, as you can write code that can handle various objects without knowing their specific types.

---

## Sources

[Back to Top](#object-orientated-programming)
