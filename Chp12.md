# Class and Object

Classes and objects are fundamental concepts in object-oriented programming. <br/>
Object-oriented programming (OOP) is a programming paradigm that revolves around the concept of objects. <br/>
An object is a data structure that contains attributes (properties) and methods (behaviors) that define the characteristics and actions of that object. <br/>
OOP is widely used in software development, and it has many benefits such as modularity, reusability, and maintainability. 
Therefore, it is essential to understand the concepts of classes and objects when learning OOP. <br/>

## What is an object?

An object is a specific instance of a class that contains data and behavior. <br/>
In simpler terms, an object is a unique thing that has specific characteristics (attributes) and actions (methods) that it can perform. <br/>
For example, a dog can be an object of the class Dog, which has attributes like its breed, age, and weight, as well as methods like "bark" and "eat". <br/>

```python
# Example of an object (a dog)
dog = {
    "name": "Rocky",
    "breed": "Telomian",
    "age": 3,
}

# Accessing object properties (attributes)
print(dog["name"])     # Output: Rocky
print(dog["breed"])     # Output: Telomian

# Modifying object properties (attributes)
dog["age"] = "5"
print(dog["age"])    # Output: 5
```

## What is a class?

A class, on the other hand, is a blueprint or template that defines the properties (attributes) and behaviors (methods) that objects of that class will have. <br/> 
It's like a mold that can be used to create multiple objects with the same characteristics and actions. <br/>
For example, the class Animal can define the attributes and methods that all animals have in common, such as their species, habitat, and ability to move, eat, and make sounds. <br/>

```python
# Example of a class (Dog)
class Dog:
    def __init__(self, name, breed, age):
        self.name = name
        self.breed = breed
        self.age = age

    def bark(self):
        print("Woof!")

# Creating two instances (object) of the class
my_dog = Dog("Max", "Labrador Retriever", 2)
your_dog = Dog("Rocky", "Telomian", 5)

# Accessing object properties (attributes)
print(my_dog.name)       # Output: Max
print(my_dog.age)        # Output: 2
print(your_dog.name)     # Output: Rocky
print(your_dog.breed)    # Output: Telomian

# Calling object method (behavior)
my_dog.bark()            # Output: Woof!
your_dog.bark()          # Output: Woof!
```

## Inheritance

Inheritance is a way of creating a new class that is a modified version of an existing class. <br/>
The new class, called the child class or subclass, inherits the properties and methods of the existing class, called the parent class or superclass, and can also add new properties and methods or modify existing ones.

The benefits of inheritance are:<br/>
- Code reusability: Inheritance allows you to reuse the code that has already been written in the parent class. You don't need to write the same code again in the child class, which can save time and effort.
- Modularity: By using inheritance, you can break down complex problems into smaller, more manageable pieces. You can create a hierarchy of related classes, each with its own set of properties and methods, that work together to solve a larger problem.
- Flexibility: Inheritance allows you to easily modify or extend the functionality of an existing class without changing its original code. You can create new classes that are similar to existing ones, but with added or modified features, without having to rewrite everything from scratch.
- Polymorphism: Inheritance is a key feature of polymorphism, which allows objects of different classes to be used interchangeably. By inheriting from a common parent class, child classes can share similar methods and properties, which makes it easier to write code that works with a variety of objects.

In Python, you can create a child class by inheriting from a parent class and defining any additional properties or methods that the child class needs. <br/>
You can also override or modify the properties and methods of the parent class in the child class. <br/>

```python
# Example of a base class (Animal)
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def eat(self):
        print("Nom nom nom...")

# Example of a derived class (Cat)
class Cat(Animal):
    def __init__(self, name, breed, age):
        super().__init__(name, species="Cat")
        self.breed = breed
        self.age = age

    def meow(self):
        print("Meow!")

# Creating an instance (object) of the derived class
my_cat = Cat("Fluffy", "Persian", 3)

# Accessing object properties (attributes) from the base class
print(my_cat.name)       # Output: Fluffy
print(my_cat.species)    # Output: Cat

# Accessing object properties (attributes) from the derived class
print(my_cat.breed)      # Output: Persian
print(my_cat.age)        # Output: 3

# Calling object method (behavior) from the base class
my_cat.eat()             # Output: Nom nom nom...

# Calling object method (behavior) from the derived class
my_cat.meow()            # Output: Meow!

```

## Polymorphism

Polymorphism is the ability of objects of different classes to be used interchangeably, even if they have different data types or behaviors. <br/>
This means that you can write code that works with a variety of objects, without having to know their exact data types or how they are implemented. <br/>
Polymorphism is a key feature of object-oriented programming and is supported by many programming languages, including Python, C#, etc.. <br/>

The benefits of polymorphism are: <br/>
- Flexibility: Polymorphism allows you to write more flexible code that can work with different types of objects. You can create a hierarchy of related classes, each with its own set of methods and properties, and write code that works with any object that inherits from a common parent class.
- Modularity: Polymorphism allows you to break down complex problems into smaller, more manageable pieces. You can write code that works with a variety of objects, without having to know the details of their implementation, which makes it easier to write modular, reusable code.
- Extensibility: Polymorphism allows you to easily extend the functionality of existing classes by creating new classes that inherit from them. You can create new classes that add or modify the behavior of existing classes, without having to change the original code.
- Ease of use: Polymorphism makes it easier to write code that works with a variety of objects, without having to write separate code for each object type. This can save time and reduce the amount of code you need to write and maintain.

In Python, you can use polymorphism by defining a common interface or set of methods that all objects in a hierarchy must implement, and then using those methods to work with objects of different types. <br/>
You can also use inheritance and method overriding to create new classes that inherit from existing ones and modify or extend their behavior. <br/>

```python
# Example of a base class (Animal)
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def make_sound(self):
        print("Generic animal sound")

# Example of a derived class (Dog)
class Dog(Animal):
    def __init__(self, name, breed, age):
        super().__init__(name, species="Dog")
        self.breed = breed
        self.age = age

    def make_sound(self):
        print("Woof!")

# Example of another derived class (Cat)
class Cat(Animal):
    def __init__(self, name, breed, age):
        super().__init__(name, species="Cat")
        self.breed = breed
        self.age = age

    def make_sound(self):
        print("Meow!")

# Creating a list of objects (instances) of the derived classes
my_animals = [Dog("Max", "Labrador Retriever", 2),
              Cat("Fluffy", "Persian", 3),
              Dog("Charlie", "Beagle", 4)]

# Calling object method (behavior) from the base class
for animal in my_animals:
    animal.make_sound()  # Output: Woof! Meow! Woof!
```

## Summary

To create an object in Python, you need to first define a class. <br/>
The class is then used to instantiate (create) objects that belong to that class. <br/>
Each object is independent and can have its own unique set of values for the attributes defined in the class. <br/>

In summary, an object is a specific instance of a class, while a class is a blueprint or template that defines the properties and behaviors that objects of that class will have. <br/>
By using classes and objects, you can write more flexible, efficient, organized and modular code that can be easily extended, reused and modified. <br/>
