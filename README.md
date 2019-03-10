# Design-Patterns

## What are Design Patterns 
Design patterns are reusable solutions to the problems that we encounter in the day to day programming. They are generally targeted at solving the problems of object generation and integration. In other words, Design patterns acts as templates which can be applied to the real-world programming problems.

## History and evolution of design Patterns
The four authors of the book famously know as Gang of four are the ones who brought the concepts of design patterns in their book “Elements of reusable Object-Oriented software” . 
 
Gang of Four has divided the book into two parts with first part explaining about the pros and cons of object oriented programming and the second part describes the evolution of 23 classic software design patterns.
 
For more details, please refer to the following wikipedia article
https://en.wikipedia.org/wiki/Design_...


## Types of Design Patterns
Gang of Four have categorised the design patterns in to 3 types based on different problems encountered in the real world applications. They are Creational, Structural and Behavioural.
 
1. Creational design patterns : These patterns deal with object creation and initialization. Creational pattern gives the program more flexibility in deciding which objects need to be created for a given case.
 
 Examples of Creational design patterns category : Singleton , Factory and Abstract Factory etc.

2. Structural design patterns : This pattern deals with class and object composition. In simple words, This pattern focuses on decoupling interface, implementation of classes and its objects. 

  Examples of Structural design patterns category : Adapter,  Facade and Bridge etc.

3. Behavioural design patterns : These patterns deal with communication between Classes and objects. 

  Examples of Behavioural design patterns : Chain of Responsibility, Command and Interpreter etc.
 


## Singleton Pattern
Singleton Pattern belongs to Creational type pattern.  

Gang of four have defined five design patterns that belongs to creational design type category. Singleton is one among them and the rest are Factory, Abstract Factory, Builder and Prototype patterns. As the name implies, creational design type deals with object creation mechanisms. Basically, to simplify this, creational pattern explain us the creation of objects in a manner suitable to a given situation. 

Singleton design pattern is used when we need to ensure that only one object of a particular class is Instantiated. That single instance created is responsible to coordinate actions across the application.


Lazy Initialization in Singleton : GetInstance Property is responsible for the Singleton Instance creation. Singleton object is not instantiated until and unless GetInstance is invoked. Hence, there is a delay in instance creation till the GetInstance is accessed.
This Delay in Instance creation is called Lazy Initialization. 

How to use Multithreads in Singleton : The lazy initialization works perfectly well when we invoke the GetInstance in a Single threaded approach. However, there is a chance that we may end up creating multiple instances when multiple threads invoke the GetInstance at the same time.

This Thread racing situation causes thread safety issues in Singleton Initialization and further the current code ends up in creating multiple instances of Singleton objects in memory.


How to implement a Thread Safe singleton class : Locks are the best way to control thread race condition and they help us to overcome the present situation. 

For more details on double check locking please refer to the below article
https://en.wikipedia.org/wiki/Double-... 


Differences between Singleton and static classes
1. Static is a keyword and Singleton is a design pattern
2. Static classes can contain only static members
3. Singleton is an object creational pattern with one instance of the class
4. Singleton can implement interfaces, inherit from other classes and it aligns with the OOPS concepts
5. Singleton object can be passed as a reference
6. Singleton supports object disposal
7. Singleton object is stored on heap
8. Singleton objects can be cloned

Static class example - Temperature Converter 
We are pretty sure that the formulas for foreign heat to Celsius conversion and vice versa will not change at all and hence we can use static classes with static methods that does the conversion for us. Please refer to the below code for more details.

Real world usage of Singleton : Listed are few real world scenarios for singleton usage
1. Exception/Information logging
2. Connection pool management 
3. File management
4. Device management such as printer spooling
5. Application Configuration management
6. Cache management
7. And Session based shopping cart are some of the real world usage of singleton design pattern


## What is Factory Design Pattern : 
 
Define an interface for creating an object, but let subclasses decide which class to instantiate. The Factory method lets a class defer instantiation it uses to subclasses

Factory pattern is one of the most used design patterns in real world applications. Factory pattern creates object without exposing the creation logic to the client and refer to newly created object using a common interface

Implementation Guidelines

We need to choose Factory Pattern when
1. The Object needs to be extended to subclasses
2. The Classes doesn’t know what exact sub-classes it has to create
3. The Product implementation tend to change over time and the Client remains unchanged


## What is Abstract Factory Design Pattern
 
Gang Of Four Definition : "The Abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme without specifying their concrete classes"

The Abstract Factory Pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes

Abstract Factory pattern belongs to creational patterns and is one of the most used design patterns in real world applications

Abstract factory is a super factory that creates other factories

Implementation Guidelines

We need to Choose Abstract Factory Pattern when
1. The application need to create multiple families of objects or products
2. We need to use only one of the subset of families of objects at a given point of time
3. We want to hide the implementations of the families of products by decoupling the implementation of each of these operations

## Builder Design Pattern Introduction

Builder Pattern belongs to creational pattern

Definition: “Separate the construction of a complex object from its representation so that the same construction process can create different representations”

Builder Pattern solves the situation of increasing constructor parameters and  
Constructors of a given class by providing a step by step initialization of 
Parameters. After step by step initialization, it returns the resulting constructed
Object at once

Implementation Guidelines

We need to Choose Builder Design Pattern when
1. We need to break up the construction of a complex object
2. We need to create a complex object and it should be independent of the parts that make up the object
3. The construction process must allow multiple representations of the same class


## Structural Design Patterns

Definition : "Structural Design Patterns are Design Patterns that ease the design by identifying a simple way to realize relationships between entities"

• Structural patterns define how each component or entity should be structured so as to have very flexible interconnecting modules which can work together in a larger system. 
• A structural design pattern also describes how data moves through the pattern. 
• Structural patterns describe how classes and objects can be combined to form larger structures
• These patterns describe how objects can be composed into larger structures using object composition, or the inclusion of objects within other objects

Gang of four has defined 7 Structural Design Patterns 
• Adapter 
• Bridge 
• Composite 
• Decorator 
• Facade  
• Flyweight 
• Proxy
  
## Adapter : Match interfaces of different classes
• An adapter allows two incompatible interfaces to work together.
• The Adapter design pattern allows incompatible classes to interact with each other by converting the interface of one class into an interface expected by the clients.
• Leveraging on Adapter pattern Improves reusability of older functionality.

Implementation Guidelines : We need to Choose Adapter Design Pattern when
1. A class need to be reused that does not have an interface that a client requires?
2. We need to work through a separate Adapter that adapts the interface of an  existing class without changing it
3. Clients don't know whether they work with a Target class directly or through an Adapter with a class that does not have the Target interface

## Bridge : 

Separates an object’s interface from its implementation
• To Simplify this definition, The bridge pattern uses encapsulation, aggregation, and can use inheritance to separate responsibilities into different classes. 
• It Decouples an abstraction from its implementation so that decoupling and abstraction can vary independently".
• The bridge pattern can also be thought of as two layers of abstraction.
• The Bridge pattern is use full when we want to avoid a permanent binding between an abstraction and its implementation.
• Bridge Patterns enables us to separate the interface from the implementation and Improves extensibility.
• Also, it hides implementation details from clients.

## Composite : 

A tree structure of simple and composite objects
• In object-oriented programming, a composite is an object designed as a composition of one-or-more similar objects, all exhibiting similar functionality.
• The Composite pattern enables us to create hierarchical tree structures of varying complexity, while allowing every element in the structure to operate with a uniform interface.
• The composite pattern describes that a group of objects are to be treated in the same way as a single instance of an object.
• The intent of a composite is to "compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets clients treat individual objects and compositions uniformly.

Implementation Guidelines : 

We need to Choose Composite Design Pattern when 
1. Represent part-whole hierarchies of objects.
2. Clients to ignore the difference between compositions of objects and individual objects.

## Decorator : 

Add responsibilities to objects dynamically
• To simplify this, The Decorator pattern enables us to add or remove object functionality without changing the external appearance or function of the object.
• The Decorator pattern attaches additional responsibilities to an object dynamically to provide a flexible alternative to changing object functionality without using static inheritance.
 
Implementation Guidelines : We need to use Decorator Design Pattern when  
1. We need to add responsibilities to individual objects dynamically and transparently,  
2. The extension by sub classing is impractical.  
3. Class definition may be hidden or otherwise unavailable for sub classing.


## Facade : 

A single class that represents an entire subsystem
• The Facade pattern provides a unified interface to a group of interfaces in a subsystem.
• The Facade pattern defines a higher-level interface that makes the subsystem easier to use with only one single interface.
• This unified interface enables an object to access the subsystem using the interface to communicate with the subsystem.
• Reduces coupling between subsystems provided if every subsystem uses its own facade pattern and other parts of the system use the facade pattern to communicate with the subsystem.
• Façade pattern Shields clients from subsystem components.

Implementation Guidelines : We need to use Facade Design Pattern when 
1. We want to provide a simple interface to a complex subsystem. Subsystems often get more complex as they evolve. 
2. There are many dependencies between clients and the implementation classes of an abstraction. 
3. We want to layer the subsystems. Use a facade to define an entry point to each subsystem level.

 
## Flyweight : 

A fine-grained instance used for efficient sharing
• The Flyweight pattern reduces the number of low-level, detailed objects within a system by sharing objects.
• The Flyweight pattern defines a structure for sharing objects and focuses its capabilities for space efficiency.
