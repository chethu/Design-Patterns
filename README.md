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

Gang of Four Definition 
Define an interface for creating an object, but let subclasses decide which class to instantiate. The Factory method lets a class defer instantiation it uses to subclasses

Factory pattern is one of the most used design patterns in real world applications. Factory pattern creates object without exposing the creation logic to the client and refer to newly created object using a common interface

Implementation Guidelines

We need to choose Factory Pattern when
1. The Object needs to be extended to subclasses
2. The Classes doesn’t know what exact sub-classes it has to create
3. The Product implementation tend to change over time and the Client remains unchanged
