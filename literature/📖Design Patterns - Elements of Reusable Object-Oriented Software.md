---
aliases: []
tags:
  - SoftwareDevelopment
---

# 📝Summary
**🎯Intent**
What does this book for?

**✏The Book in 3 Sentences**
1...
2...
3...

**🧠Impression**
I feel ...

**🏁Progress**
|             | Read? | Document? |
| ----------- | ----- | --------- |
| Chapter ... |       |           |
|             |       |           |
|             |       |           |





# 0.Principles of Object-Oriented Design

<div align="center">
<h3>Program to an interface, not an implementation.</h3>
<h3>Favor object composition over class inheritance.</h3>
</div>






# 1.Introduction

📌**How does design pattern help?**

It aims to tackle Déjà Vu which you have solved a problem before but not knowing exactly where or how.

📌**Purpose of this Book**

The purpose of this book is to record **experience** in designing object-oriented software as **design patterns**.

📌**Design Pattern in Chinese**

将面向对象编程经验**可复用**的东西抽象成设计模式。

:smile:**Fun Fact**

The design pattern in Software Development actually was affected by an architect Christopher Alexander where he addressed that "*Each pattern describes a problem which occurs over and over again in our environment, and then **describes the core of the solution to that problem**, in such a way that you can **use this solution a million times over**, **without ever doing it the same way** twice*".



## 1.1. What Is a Design Pattern?

📌 **4 essential elements** for a design pattern

- 1️⃣**pattern name**, a handle to **describe** a design problem
- 2️⃣**problem**, elaborate the problem with its context and include **a list of conditions to check** before applying design patterns(see if fits?)
- 3️⃣**solution**
  - :heavy_check_mark:it is **an abstraction and template** to solve such problem(抽象结局方案)
  - ❌ it is NOT a particular design or implementation(不具体实现) 
- 4️⃣**consequence**, the result and **trade-off** applying such design pattern



📌**Design Pattern Definition(.fml)**

The design patterns are *description of communicating objects and classes that are customized to solve a general design problem in a particular context*.



## 1.2. Design Pattern in MVC

In this section, we take MVC as an example to see which kinds of design patterns it applied.

📌**What is MVC?**

MVC is <u>**Model / View / Controller**</u>.

> ​	The Model is the application object.

> ​	The View is its screen presentation. 

> ​	The Controller defines the way the user interface reacts to user input.

MVC **decouples** <u>views</u> and <u>models</u> by establishing a **subscribe/notify** protocol between them.

📌**Diagram of application used MVC**

<img src="img/image-20211214162317094.png" alt="image-20211214162317094" style="zoom: 80%;" />

📌**MVC & MVVM**

A great analogy is MVC and MVVM.

| MVC                                                          | MVVM                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| An architectural pattern                                     | A software architectural pattern                             |
| Model View Controller                                        | Model View ViewModel                                         |
| Model -> data<br/>View -> user interface<br/>Controller -> handles request | Model -> entities and domain objects<br/>View -> user interface layer<br/>View Model-> describes binding between view and model |
| Used by ASP.NET, Java, Spring                                | Used by Angular JS, Microsoft WPF                            |

From my point of view, the MVVM is a subset or an explicit implementation(实现) of MVC. MVC can be more abstract.



📌**What kinds of design pattern applied in MVC?**

<u>OBSERVER</u>: 

> ​	the methodology of observer is to **decouple objects** so that changes to one can affect any number of others without requiring the changed object to know details of the others.
>
> ​	e.g. The model and view is separated. If some data is changed in Model, the View can apply the changes to other views.

<u>COMPOSITE</u>:

> ​	the methodology of composite is to "**compose**" objects into **tree structures** to represent part-whole hierarchies.
>
> ​	e.g. create a big class including 
>
> ​			A. subclasses define primitive objects (e.g., Button)
>
> ​			B. other classes define composite objects (CompositeView) that **assemble the primitives into more complex objects**.

<u>STRATEGY</u>:

> ​	the methodology of strategy is to select an algorithm at runtime
>
> ​	e.g. a view can be disabled so that it doesn't accept input simply by giving it a controller that ignores input events.





## 1.3. Describing Design Patterns:star:

The following is a template to describe design patterns in a unique sense.

📌**Pattern Name and Classification**

> ​	The name is the essence of the pattern.

📌**Intent**

> ​	A short description what does this pattern do?

📌**Also Known As**

> ​	Alias for this pattern (if any).

📌**Motivation**

> ​	A scenario that illustrates a design problem and how the class and object structures in the pattern solve the problem.

📌**Applicability**

> ​	What are the situations in which the design pattern can be applied?

📌**Structure**

> ​	A graphical representation of this design pattern.

📌**Participants**

> ​	The participated classes and/or objects and their responsibility.

📌**Collaborations**

> ​	How the participants work together?

📌**Consequences**

> ​	The trade-off and results.

📌**Implementation(实现)**

> ​	What pitfalls, hints, or techniques should be aware of implementing the pattern?

📌**Sample Code**

> ​	Code fragments

📌**Known Issues**

> ​	Examples

📌**Related Patterns**

> ​	The closest pattern to current one, what are their differences?



## 1.4. The Catalog of Design Patterns:star:

The following is the design patterns. //TODO write with your own words after finished this book,

📌**Abstract Factory**

> ​	Provide an interface for creating families of related or dependent objects without specifying their concrete classes.

📌**Adapter**

> ​	Convert the interface of a class into another interface clients expect. Adapter lets classes work together that couldn't otherwise because of incompatible interfaces.

📌**Bridge**

> ​	Decouple an abstraction from its implementation so that the two can vary independently.

📌**Builder**

> ​	Separate the construction of a complex object from its representation so that the same construction process can create different representations.

📌**Chain of Responsibility**

> ​	Avoid coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. Chain the receiving objects and pass the request along the chain until an object handles it.

📌**Command**

> ​	Encapsulate a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations.

📌**Composite**

> ​	Compose objects into tree structures to represent part-whole hierarchies. Composite lets clients treat individual objects and compositions of objects uniformly.

📌**Decorator**

> ​	Attach additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

📌**Facade**

> ​	Provide a unified interface to a set of interfaces in a subsystem. Facade defines a higher-level interface that makes the subsystem easier to use.

📌**Factory Method**

> ​	Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.

📌**Flyweight**

> ​	Use sharing to support large numbers of fine-grained objects efficiently.

📌**Interpreter**

> ​	Given a language, define a representation for its grammar along with an interpreter that uses the representation to interpret sentences in the language.

📌**Iterator**

> ​	Provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation.

📌**Mediator**

> ​	Define an object that encapsulates how a set of objects interact. Mediator promotes loose coupling by keeping objects from referring to each other explicitly, and it lets you vary their interaction independently.

📌**Memento**

> ​	Without violating encapsulation, capture and externalize an object's internal state so that the object can be restored to this state later.

📌**Observer**

> ​	Define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

📌**Prototype**

> ​	Specify the kinds of objects to create using a prototypical instance, and create new objects by copying this prototype.

📌**Proxy**

> ​	Provide a surrogate or placeholder for another object to control access to it.

📌**Singleton**

> ​	Ensure a class only has one instance, and provide a global point of access to it.

📌**State **

> ​	Allow an object to alter its behavior when its internal state changes. The object will appear to change its class.

📌**Strategy **

> ​	Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from clients that use it.

📌**Template Method**

> ​	Define the skeleton of an algorithm in an operation, deferring some steps to subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm's structure.

📌**Visitor **

> ​	Represent an operation to be performed on the elements of an object structure. Visitor lets you define a new operation without changing the classes of the elements on which it operates.



## 1.5. Categorizing Design Patterns:star:

Categorizing the design patterns with certain rules is of tremendous importance. 

There are **2** criteria:

1️⃣**Purpose**, it reflects what a pattern does

- `creational patterns`, concern the process of object creation.

- `structural patterns`, deals with the composition of classes or objects
- `behavioral patterns`, characterize the interaction and responsibility of classes and objects

2️⃣**Scope**, it specifies whether the pattern applies to classes or objects

- `class patterns`, deal with relationship between classes and subclasses, they are static - fixed at runtime.
- `object patterns`, deal with object relationship, they are dynamic - changed at runtime.



<img src="img/image-20211216154058477.png" alt="image-20211216154058477" style="zoom: 67%;" />



📌**How to see these patterns?**

The pattern can be defined as [Purpose]-[Scope]. 



📌**Example - interpret the pattern**

> ​	<u>Purpose</u> = Structural,

> ​	<u>Scope</u> = Class,

`Structural class` patterns use inheritance to **compose classes**.



> ​	<u>Purpose</u> = Structural,

> ​	<u>Scope</u> = Object,

`Structural object` patterns describe ways to **assemble objects**.



## 1.6. How Design Patterns Solve Design Problem

- `1.6.1.` illustrates what is an object (in abstraction, in configuration)
- `1.6.2.` defines how "abstract" the object is



### 1.6.1. Finding Appropriate Objects

📌**Why object is important?**

Object-oriented programs are made of objects.



📌**Insight of object**

In short, object's internal state is said to be **encapsulated**.

![image-20211216171150589](img/image-20211216171150589.png)



📌**Hard part of OOP**

It is HARD to **decompose a system into objects** in object-oriented design. Why is hard? It MUST take followings into consideration.

- encapsulation
- granularity
- dependency
- flexibility
- performance
- evolution
- reusability



📌**Design Pattern can help**

Design patterns help you to identify an appropriate object with abstraction.



### 1.6.2. Determining Object Granularity

📌**What is Granularity?**

Granularity is a level of details(LOD).  [颗粒度 in CHN]



📌**Why Granularity matters?**

It corresponds to memory-consuming. For example, you have the following in your program:

- trees in game landscape
- characters in document
- power points in cad application

If you will create separate object for each tree/character/power-point it could be very memory-consuming. Recall the days I played with Rendering and Forest in 3dsMax.



📌**Design Pattern can help**

It helps you decide what should be an object(in which level of details).



### 1.6.3. Specifying Object Interfaces

📌**What is signature?**

The signature is composed of <u>parameters</u> and <u>return types</u>.

```c++
int addOne(int num);
```



📌**What is interface?**

The **interface is the set of all the signatures defined by an object**. You can say this object supports following interface.



📌**What is a type?**

A type is a name used to **denote a particular interface**. We speak of an object as having the type "Elephant" if it accepts all requests for the operations defined in the interface named "Elephant".



📌**What is dynamic binding?**

The run-time association of a request to an object and one of its operations is known as dynamic binding.



📌**What is polymorphism?**

Dynamic binding lets you substitute objects that have identical interfaces for each other at run-time. This substitutability is known as polymorphism.



📌**Why polymorphism is important?**

Polymorphism simplifies the definitions of clients, decouples objects from each other, and lets them vary their relationships to each other at run-time. It is a :star:**KEY** concept in OOP.



📌**Why interface is important?**

You can only achieve polymorphism by interface.



📌**Design Pattern can help**

:one:Design patterns help you define interfaces by **identifying** their **key elements and the kinds of data** that get sent across an interface.

:two:Design patterns also **specify relationships** between interfaces.



### 1.6.4. Specifying Object Implementation

📌**Diagram of Class and Object**

![image-20211217094458982](img/image-20211217094458982.png)

An object's implementation is defined by its **class**.

Object is said to be an **instance** of the class because they are created by **instantiating** a class.



📌**Class Inheritance**

The class inheritance describes a **<u>subclass</u> / <u>derived class</u>** inherits from a **<u>parent class</u> / <u>base class</u>**.

![image-20211217101741383](img/image-20211217101741383.png)



📌**Abstract class and Concrete class**

<u>Abstract class</u>: its main purpose is to **define a common interface** for its subclasses. (it does not have to implement all the operations)

<u>Concrete class</u>: the complement of abstract class is concrete class. (the interface must be implemented!)

![image-20211217103137298](img/image-20211217103137298.png)

Therefore, you can implement the operation defined by *abstract class* elsewhere. 



📌**Mixin Class**

A **mixin** (or **mix-in**) is a class that contains methods for use by other classes without having to be the parent class of those other classes. 

![image-20211217103912064](img/image-20211217103912064.png)





📌**<u>Class Inheritance</u> VS <u>Interface Inheritance</u>**

Personally, I think the design of C# illustrating these concepts very well.

> ​	**<u>Class inheritance</u>** defines an object's implementation in terms of another object's implementation. In short, it's a mechanism for **code and representation sharing**. 

> ​	<u>**Interface inheritance**</u> (or subtyping) describes when an object can be used in place of another.

//TODO a diagram illustrating this would be better.



📌**Program to an interface, not an implementation**:star::star::star:

> ​	This is super IMPORTANT!! PLEASE KEEP IT IN MIND!!!

Don't declare variables to be instances of particular concrete classes. Instead, commit only to an interface defined by an abstract class. 



> ​	Example of Programming to an interface:heavy_check_mark:

```c++
//Base class specifying the interface
class Calculator
{
protected:
	double g_num;

public:
	virtual double AddOperation(double value);
};

//Derived class implementing the interface
class NewCalculator : public Calculator
{
public:
	double AddOperation(double value) override
	{
		this->g_num += value;
	}
};

//Derived class implementing the interface
class OldeCalculator : public Calculator
{
public:
	double AddOperation(double value) override
	{
		this->g_num += value + value;
	}
};
```



> ​	Example of Programming to an implementation:x:

```c++
class Calculator
{
private:
	double g_num;

public:
	double AddOperation(double value)
	{
		this->g_num++;
	}
};
```



:star:The former one is **BETTER** because **polymorphism** depends on it.



📌**Why Design patter can help?**

The <u>**creational patterns**</u> help you in specifying the particular implementation of those interfaces somewhere in your system. They are *Abstract Factory*, *Builder*, *Factory Method*, *Prototype*, and *Singleton*.



### 1.6.5. Putting Reuse Mechanisms to Work

📌**Inheritance versus Composition**

In short, you should use *composition* more than *inheritance*!!

> ​	**Inheritance - [White Box]:white_large_square:**

If inherited implementation **not be appropriate** for new problem, the parent class **must be rewritten**!!

> ​	 **Composition - [Black Box]:black_large_square:**

New functionality is obtained by **assembling** or **composing** <u>**objects**</u> to get more complex functionality. Object composition requires that the objects being composed have well-defined interfaces.



I think **intuitive** understanding is even better than text explanation.

<div align="center">
<img src="img/diagram_of_composition.svg" style="width:40%" class="center">
  <figcaption>Diagram of Composition</figcaption>
    <br></br>
    <img src="img/diagram_of_inheritance.png" style="width:40%" class="center">
  <figcaption>Diagram of Inheritance</figcaption>
</div>

Composition is way more flexible than inheritance.





📌**Aggregation vs. Acquaintance**

|                                               | Aggregation                              | Acquaintance                             |
| --------------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| Relationship between objects and owners[DIFF] | close, tight                             | loose, weaker                            |
| Lifetime[DIFF]                                | have identical lifetimes                 | not responsible for each other           |
| Intention[DIFF]                               | permanent                                | dynamic                                  |
| Language Mechanism[COMMON]                    | implemented with pointers and references | implemented with pointers and references |



📌**Why Design patter can help?**

Because aggregation and acquaintance are often related to **compile-time** and **run-time**. Therefore, many design patterns (in particular those that have object scope) capture the distinction between compile-time and run-time structures explicitly. 



### 1.6.6. Designing for Change

📌**Change**

Change is fxxking everywhere. You know that.



📌**Why Design patter can help?**

Design patterns help you avoid this by ensuring that **a ROBUST system can change in specific ways**. 



📌**Common Causes of Redesign** :star::star::star:

The following are the common causes of redesign in Software Development.

> ​	1️⃣*Creating an object by specifying a class explicitly*❌

**Description:page_facing_up:** Specifying a class name when you create an object commits you to a particular implementation rather than a particular interface.

**Solution**✔: create objects indirectly by [Abstract Factory][iAbstract Factory] ,  [Factory Method][iFactory Method],   [Prototype][iPrototype]



> ​	2️⃣*Dependence on specific operations*❌

**Description:page_facing_up:** Commit one way and hardcode of satisfying a request.

**Solution**✔:   create dynamic request at compile-time and at run-time by [Chain of Responsibility][iChain of Responsibility] [Command][iCommand ]



> ​	3️⃣*Dependence on hardware and software platform*❌

**Description:page_facing_up:** (You know that)

**Solution**✔ : design system not to limit its on platform by [Abstract Factory][iAbstract Factory],  [Bridge][iBridge]



> ​	4️⃣*Dependence on object representations or implementations*❌

**Description:page_facing_up:** Clients that know how an object is represented, stored, located, or implemented might need to be changed when the object changes. Hiding this information from clients keeps changes from cascading!:star: (若客户知道一个obj怎么表达，他肯定会根据这个"表达"来修改，因此我们需要隐藏这个"表达"，越抽象越好)。

**Solution**✔: You can make these objects more abstract by  [Abstract Factory][iAbstract Factory] ,[Bridge ][iBridge], [Memento][iMemento ], [Proxy][iProxy ]



> ​	:five:*Algorithmic dependencies*❌

**Description:page_facing_up:** :  Algorithms always change. Objects that depend on an algorithm therefore change.

**Solution**✔: Algorithms that are likely to change should be isolated by [Builder][iBuilder], [Iterator][iIterator], [Strategy][iStrategy], [Template Method][iTemplate Method], [Visitor][iVisitor]



> ​	:six:*Tight coupling*❌

**Description:page_facing_up:** :  Classes that are tightly coupled are hard to reuse in isolation.

**Solution**✔: Develop loosely coupled systems by [Abstract Factory][iAbstract Factory], [Bridge][iAbstract Factory], [Chain of Responsibility][iChain of Responsibility], [Command][iCommand], [Facade][iFacade], [Mediator][iMediator], [Observer][iObserver]



> ​	:seven:*Extending functionality by subclassing*❌

**Description:page_facing_up:** :  Customizing an object by subclassing is **HARD**. Every new class has a **fixed** implementation overhead (initialization, finalization, etc.). Defining a subclass also **requires** an in-depth understanding of the parent class.

**Solution**✔: You can use <u>**object composition**</u> in general and **<u>delegation</u>** in particular provide flexible alternatives to inheritance for combining behavior. by [Bridge][iBridge], [Chain of Responsibility][iChain of Responsibility], [Composite][iComposite], [Decorator][iDecorator], [Observer][iObserver], [Strategy][iStrategy]



> ​	:eight:*Inability to alter classes conveniently*❌

**Description:page_facing_up:** :  Imagine you have to modify a class that can't be modified conveniently because the class is for commercial target.

**Solution**✔: You can solve this by [Adapter][iAdapter], [Decorator][iDecorator], [Visitor][iVisitor]






📌**Changes in 3 classes of software**

> ​	1️⃣*application programs*

required generalization+

required flexibility+

e.g. standalone software

> ​	2️⃣*toolkits*

required generalization++

required flexibility++

e.g. libigl

> ​	3️⃣*frameworks*

required generalization+++

required flexibility+++

e.g. Unreal Engine, NET Framework



## 1.7. How to Select a Design Pattern

Within more than 20 design patterns, it's hard to choose among them. The followings are the approach can help you choose the Design Pattern.

📌**Consider how design patterns solve design PROBLEMS**

Refer to section 1.6.,

<img src="img/image-20211222163645970.png" alt="image-20211222163645970" style="zoom: 80%;" />



📌**Scan Intent Section**

- Quickly scan the intent in [1.4.][#14-the-catalog-of-design-patternsstar] , find the appropriate one.
- Narrow the search by table in [1.5.][#15-categorizing-design-patternsstar]



📌**Study how patterns interrelate**

Refer the relational graph in [1.6.][#16-how-design-patterns-solve-design-problem]  , it will help you understand the relationship in a bigger picture.



📌**Study patterns of like purpose**

Read the essential **intro** of each categories of patterns. :star: 

- [Creational][#3creational-patterns]
- [Structural][#4structural-patterns]
- [Behavioral][#5behavioral-patterns]



📌**Examine a cause of redesign**

When you are **frustrated by a redesign** problem, refer to page [24][#166-designing-for-change] to **avoid causes of redesign**.



📌**Identify the VARIABLE in your design**

Rather than focusing on the causes of redesign, find the "**changes**" instead! The following is a table highlighting those variables.

![image-20211222173535064](img/image-20211222173535064.png)



## 1.8. How to Use a Design Pattern

📌**1.Read the overview:eyes:**

Read the pattern once through for an overview. Pay particular **attention** to the **<u>Applicability</u>** and **<u>Consequences</u>** sections to ensure the pattern is right for your problem.



📌**2.Study the structure, participants, and collaboration section**

Make sure you **understand** the **classes** and **objects** in the pattern and **<u>how they relate</u>** to one another.



📌**3.Sample Code**

Studying the code **helps you** learn **how to implement the pattern**.



📌**4.Choose NAME for pattern participants**

Choose names for pattern participants that are **meaningful in** the application **context**. That **helps** make the pattern more explicit in the **implementation**.



📌**5.Define the classes**

Declare their **interfaces**, establish their **inheritance relationships**.

<img src="img/image-20211222175349089.png" alt="image-20211222175349089" style="zoom: 50%;" />

Define the instance variables that represent **data** and **object references**. 

<img src="img/image-20211222175408276.png" alt="image-20211222175408276" style="zoom: 67%;" />

**Identify existing classes** in your application that the pattern will affect, and **modify them** accordingly.



📌**6.Define <u>application-specific</u> names for operation**

**Denote** the operation in light of <u>responsibilities</u> and <u>collaborations</u>. 

Be **consistent** in your **naming conventions**. For example, you might use the "Create-" prefix consistently to denote a factory method.



📌**7.Implement the operations**

Implement the operations to carry out their **responsibilities** and **collaborations** defined in the pattern.



# 2.A Case Study: Design a Document Editor

This chapter will illustrate Design Patterns with a Case Study, a document editor, Lexi.

<img src="img/image-20211227175550913.png" alt="image-20211227175550913" style="zoom:50%;" />

## 2.1. Design Problems Overview [7/7]

The following are the design problems in this case study.

1️⃣**Document structure**

> ​	It refers to the way we organize the information which will impact the design of the rest of the application.

2️⃣**Formatting**

> ​	How does Lexi actually arrange text and graphics into lines and columns?

3️⃣**Embellishing the user interface**

> ​	UI stuffs

4️⃣**Supporting multiple look-and-feel standards**

> ​	Adapt easily to different look-and-feel standards

:five:**Supporting multiple window systems**

> ​	(you know that)

:six:**User operations**

> ​	the "C" in MVC

:seven:**Spelling checking and hyphenation**

> ​	for grammar shxt



## 2.2 Document Structure [1/7]

📌**What is it?**

A document is ultimately just **<u>an arrangement of basic graphical elements</u>** such as characters, lines, polygons, and other shapes.



📌**Basic Principle**

1️⃣ **Treat them as a unit** rather than a mass of primitive objects.   e.g. click table as a table but a the line or individual text inside of it.

2️⃣  Choose an internal representation that **matches** the **documents' physical structure**.

3️⃣  **No distinguish** between single elements and groups of elements in the **internal representation**.



📌**Recursive Composition**

A common way to represent hierarchically structured information is through a technique called **recursive composition**.



> ​	An intuitive feel:

<img src="img/image-20211228095930670.png" alt="image-20211228095930670"  />

> ​	Objects structure behind:

![image-20211228100039290](img/image-20211228100039290.png)

It's a bit of similar to the stack component in [HumanUI](https://www.food4rhino.com/en/app/human-ui) where you **<u>composite objects in row and/or in columns recursively</u>**.



To implement the preceding principle, there are **2** things should be aware:

- The objects need corresponding classes. (recursive composition)
- These classes must have **compatible interface**. (treat them as a unit)

Therefore, you have the following class hierarchy:

<img src="img/image-20211228100543054.png" alt="image-20211228100543054" style="zoom: 80%;" />



📌**Glyphs**

A **Glyph abstract class** is the <u>very elemental thing</u>[^2] for all objects that can appear in a document structure. Its subclasses define:

- primitive graphical elements (like characters and images)

- structural elements (like rows and columns).



Glyphs have **3** basic responsibilities:

:one:how to draw themselves

:two:what space they occupy

:three:their children and parent.

| Responsibility | Operations                                                   |
| -------------- | ------------------------------------------------------------ |
| appearance     | `virtual void Draw(Window* )`<br/>`virtual void Bounds(Rect& )` |
| hit detection  | `virtual bool Intersects(const Point& )`                     |
| structure      | `virual void Insert(Glyph* , int)`<br/>`virtual void Remove(Glyph* )`<br/>`virtual Glyph* Child(int)`<br/>`virtual Glyph* Parent()` |



We will make an example for each responsibility:



📌**Responsibility - appearance**

The `Window` class **defines graphics operations** for rendering text and basic shapes in a window on the screen. Therefore, the `Draw()` in `Rectangle` class will draw a rectangle in the window by **2** corners.

```c++
void Rectangle::Draw (Window* w) 
{
    w->DrawRect(_x0, _y0, _x1, _y1);
}
```



📌**Responsibility - hit detection**

Hit detection refers to human-computer interaction. It receives a mouse coordinate by `Point&`. If it returns `true`, then it means you are hover over the object.



📌**Responsibility - structure**

You use `Insert()` to add objects while `Remove` to remove objects.

The hierarchy relation can be defined via `Child()` and `Parent()`.



📌**What Design Pattern can help?**

The [Composite][iComposite] pattern **captures the essence of recursive composition** in object-oriented terms.





## 2.3. Formatting [2/7]

📌**What "formatting" really?**

The formatting in this context refers to the following: margin widths, indentation, and tabulation; single or double space; and probably many other formatting constraints.

You can see it as the <u>text</u> and <u>layout styles</u> on InDesign.



📌**Strategy on formatting algorithm**

- <u>**Trade-off**</u>: on <u>compile time</u> and <u>appearance</u>, the authors prefer the former rather than the latter.

- <u>**Dependence**</u>: the authors insist the <u>formatting algorithms</u> should be <u>**independent**</u> from the <u>document structure.</u>



📌**Compositor and Composition**

- Compositor: class for objects that can encapsulate formatting algorithms
- Composition: the children of composition is a glyph subclass which actually does the formatting.



📌**Basic interface of compositor**

| Responsibility | Operations                           |
| -------------- | ------------------------------------ |
| what to format | `void SetComposition(Composition* )` |
| when to format | `virtual void Compose()`             |



📌**Diagram of Compositor and Composition**

In short, 

- composition **defines** <u>what kind of and how many</u> **elements** should be in the documents.

- compositor **regulates** <u>how should</u> <u>each element</u> and <u>elements in total</u> should look like.

<img src="img/image-20220130201021247.png" alt="image-20220130201021247" style="zoom: 67%;" />





📌**What Design Pattern could help?**

The  [Strategy][iStrategy] pattern can help, which encapsulates <u>various strategies</u> regarding <u>different contexts</u>. e.g. apply different formatting algorithms in light of different themes(compositor).



📌**What is the KEY of Strategy pattern?**

The key is designing interfaces for the strategy and its context that are <u>**general enough**</u> to support arrange of algorithms.

For example,  

- [Composition] the `Glyph` interface supports for 
  - child access, 
  - insertion
  - removal
- [Compositor] subclasses therefore can apply different formatting algorithms:
  - Array composing
  - Tex composing
  - Simple composing
- [Outcome] change the document's physical structure accordingly



## 2.4. Embellishing the User Interface[3/7]

📌**What is Embellishment?**

The embellishment[^3] refers to the decoration onto the user interface. e.g. add a border, add a scroll bar



📌**Strategy on Embellishment**

Since embellishment literally refers to "decoration", the user interface object <u>should not be aware of</u> the existence of embellishment.





# 3.Creational Patterns

📌**What creational patterns for?**

Creational design patterns <u>abstract the instantiation</u> process which make a system independent of how its objects are <u>**created**</u>, <u>**composed**</u>, and <u>**represented**</u>.



📌**Main Strategy**

Creational patterns depend more on **<u>object composition</u>** than <u>*class inheritance*</u>.



📌**2 Main Charactersitcs**

There are **2** main characteristics/features of creational patterns:

- They all <u>**encapsulate**</u> knowledge about which concrete classes the system uses.
- They all <u>**hide**</u> how instances of these classes are created and put together.



📌**Case Study **

We will consider the construction process of a computer game. In short, the architecture of a maze. The maze is constructed by the following:

- a set of rooms, walls, doors
- room specify the access in 4 orientations
- door specify the access

<img src="img/image-20211225172030523.png" alt="image-20211225172030523" style="zoom: 80%;" />



Each room has 4 sides.(`enum`)

```c++
enum Direction (North, South, East, West);
```



The `MapSite` is the **<u>primitive</u>** element of this project.

```c++
class MapSite
{
    public:
    virtual void Enter() = 0;
}
```



`Room` is the concrete subclass of `Mapsite` which defines the relationship between components in the maze.

```c++
class Room : public MapSite
{
private:
    MapSite* _sides[4];  //the private member store the 4 sides of object
    int _roomNumber;     //the room number of this room

public:
    Room(int roomNo);                      //constructor
    
    MapSite* GetSide(Direction) const;     //Get the side of a room
    void SetSide(Direction, MapSite*);     //Set the side of a room
    virtual void Enter();                  //Enter function
}
```



`Wall` occurs on each side of a room(maybe).

```c++
class Wall : public MapSite
{
public:
    Wall();                //Constructor
    virtual void Enter();  //Enter function
}
```



`Class` occurs on each side of a room(maybe).

```c++
class Door : public MapSite
{
private:
    Room* _room1;    //door attached to 2 rooms, this is one of them
    Room* _room2;    //door attached to 2 rooms, this is one of them
    bool _isOpen;    //see if it is open
    
public:
    Door(Room* = 0, Room* = 0);    //constructor with 2 rooms
    virtual void Enter();          //Enter function
    Room* OtherSideFrom(Room*);    //Return the other side by pointer
}
```



`Maze` is to represent a collection of rooms.

```c++
class Maze
{
    private:
    //..
    
    public:
    Maze();  //constructor
    void AddRoom(Room*);  //Add room to this maze
    Room* RoomNo(int) const;  //A method look-up a room number by using a linear search, a hash table,or even a simple array.
    
}
```



`MazeGame` is the class to **<u>create</u>** the maze. This is the **KEY** concept of creational patterns! 

:x:You don't explicitly define what is a `Maze` should be.

:heavy_check_mark:Rather you create the `MazeGame` with a method called `CreateMaze` with flexibility to modify the formula in the future.

```c++
Maze* MazeGame::CreateMaze()
{
    Maze* aMaze = new Maze();
    Room* r1 = new Room(1);            //init a room with RoomNo 1
    Room* r2 = new Room(2);            //init a room with RoomNo 2
    Door* doorR1R2 = new Door(r1, r2); //init a door between Room1 and Room2
    
    //Set the 4 sides of Room1
    r1 -> SetSide(North, new Wall());
    r1 -> SetSide(East, doorR1R2);
    r1 -> SetSide(South, new Wall());
    r1 -> SetSide(West, new Wall());
    
    //Set the 4 sides of Room2
    r2 -> SetSide(North, new Wall());
    r2 -> SetSide(East, new Wall());
    r2 -> SetSide(South, new Wall());
    r2 -> SetSide(West, doorR1R2);
    
    //Add the rooms to the maze
    aMaze -> AddRoom(r1);
    aMaze -> AddRoom(r2);
    
    return aMaze;
}
```



The preceding code is with great flexibility. Although you can make it simpler, you will lose the flexibility to modify the maze eventually.

For example, considering the `Room` constructor could initialize the sides with walls ahead of time.

```c++
Maze* MazeGame::CreateMaze()
{
    Maze* aMaze = new Maze();
    Room* r1 = new Room(1, new Wall(), doorR1R2, new Wall(), new Wall());
    Room* r2 = new Room(2, new Wall(), new Wall(), doorR1R2, new Wall()); 
    
    //LOST FLEXIBILITY!!!
}
```

❌:warning:It **hard-codes** the maze layout. Changing the layout means changing this member function, either by overriding it—which means reimplementing the whole thing—or by changing parts of it—which is **<u>error-prone</u>** and **<u>doesn't promote reuse</u>**.







📌**How Creational Design Patterns can help?**

The KEY idea of creational patterns is to **remove explicit references to concrete classes** from code that needs to instantiate them.

- [Factory Method][iFactory Method] - The `CreateMaze` method is <u>**virtual**</u> which allows subclass of `MazeGame` to override it.

- [Abstract Factory][iAbstract Factory] - The `CreateMaze` is passed <u>**an object as a parameter**</u> to create elements[^1] , then you can change the classes of those things by passing a different parameter.

- [Builder][iBuilder] - The `CreateMaze` is passed **<u>an object that can create a new `maze` in its entirety</u>** using operations like adding elements[^1], then you can use <u>inheritance</u> to change parts of the `maze` or the way the `maze` is built.

- [Prototype][iPrototype] - The `CreateMaze` is **<u>parameterized by various prototypical elements</u>**[^1], which it then copies and adds to the `maze`,then you can change the `maze`'s composition by replacing them.

[Singleton][iSingleton], the one not mentioned above, can <u>**ensure there's only one maze per game**</u> and that all game objects have ready access to it—**<u>without resorting to global variables or functions</u>**.





## 3.1. Abstract Factory

🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___









## 3.2. Builder



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 3.3. Factory Method

🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___







## 3.4. Prototype



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___



## 3.5. Singleton

<div align="center">
    <figure>
        <img src="img/singleton.png" style="width:50%" class="center">
        <figcaption>Singleton ©Dive Into Design Patterns</figcaption>
    </figure>
</div>




🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 3.6. Discussion of Creational Patterns



# 4.Structural Patterns

## 4.1. Adapter

<div align="center">
    <figure>
        <img src="img/adapter.png" style="width:50%" class="center">
        <figcaption>Adapter ©Dive Into Design Patterns</figcaption>
    </figure>
</div>




🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___






## 4.2. Bridge



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 4.3. Composite

<div align="center">
    <figure>
        <img src="img/composite.png" style="width:50%" class="center">
        <figcaption>Composite ©Dive Into Design Patterns</figcaption>
    </figure>
</div>




🎯**Intent**

___

Compose objects into **tree structures** to represent part-whole hierarchies. Composite lets clients <u>treat</u> **individual objects** and **compositions of objects** **<u>uniformly</u>**.



:muscle:**Motivation**

___

Suppose you have **2** main things in your application:

- the object
- the composite of object

And you don't want to explicitly create a container for the composite of object. The Composite pattern describes how to **use recursive composition** so that clients don't have to make this distinction.

![image-20211228113358722](img/image-20211228113358722.png)

The **<u>key</u>**:star: to the Composite pattern is:

- an **abstract class** that **represents both primitives and their containers**.
- declares operations that **all composite objects share**.
- primitive object have no child object
- composite is an aggregate of primitive object







:earth_asia:**Real World Analogy**

___

We can see the composite pattern in an army.



<div align="center">
    <figure>
        <img src="img/composite-live-example.png" style="width:20%" class="center">
        <figcaption>Analogy of Composite in the real world ©Dive Into Design Patterns</figcaption>
    </figure>
</div>





:heavy_dollar_sign:**Applicability**

___

Use Composite pattern when:

- You want to => represent **part-whole hierarchies** of objects.
- You want to => **ignore** the **difference** between compositions of objects and individual objects.
- Clients want to => **treat** all objects in the composite structure **uniformly**.







:building_construction:**Structure**

___



![image-20211228114517193](img/image-20211228114517193.png)

The following is a typical composite object structure:

![image-20211228113538944](img/image-20211228113538944.png)









:family_man_woman_girl_boy:**Participants**

___

The followings are the participants of Composite Pattern.



> ​	:black_circle: **Component**  (e.g. The graphic)

It is responsible for the followings:

- **declares** the **interface** for objects in the composition. 

- **implements default behavior** for the interface common to all classes

- declares an **interface** for <u>accessing and managing</u> its **child** components.

- (optional) defines an **interface** for <u>accessing</u> a component's **parent** in the recursive structure



> ​	:black_circle: **Leaf**  (e.g. Rectangle, Line, Text, etc.)

It is responsible for the followings:

- represents <u>leaf objects</u> in the composition. A leaf **has no children**.

- defines **behavior for primitive objects** in the composition.



> ​	:black_circle: **Composite**  (e.g. Picture, etc.)

It is responsible for the followings:

- defines **behavior** for <u>components having children</u>.
- **stores** child components

- implements **child-related operations** in the Component interface



> ​	:black_circle: **Client**

It is responsible for the followings:

- **manipulates objects** in the composition through the Component interface.





For a more transparent and vivid understanding, we layout the comparison:

| Generic Participants | Participants in Lexi                                     | Participants in Maze Game                 |
| -------------------- | -------------------------------------------------------- | ----------------------------------------- |
| Component            | `(abstract class)`  Graphic                              | `(abstract class)`  MapSite               |
| Leaf                 | `(instance)` Rectangle, Line, Text                       | `(instance)`  Wall, Door, Room            |
| Composite            | `(composite of instances)`  Picture, Diagram, Text Block | `(composite of instances)`  Maze1, Maze 2 |
| Client               | User                                                     | Player                                    |







:handshake:**Collaboration**

___

<u>Clients</u> use the <u>Component class interface</u> to **interact with objects** in the composite structure. 

- If the recipient is a <u>Leaf</u>
  - then the request is **<u>handled directly</u>**. 
- If the recipient is a <u>Composite</u>
  - then it usually **<u>forwards requests to</u>** its <u>child</u> components, possibly performing additional operations before and/or after forwarding.



:chart_with_upwards_trend:**Consequence**

___

The Composite pattern:

- ✔  **<u>defines class hierarchies consisting of primitive objects and composite objects</u>**.
  - Primitive objects can be composed into complex objects and recursive objects. 
  - Client codes freely perform on both primitive object and a composite object.
- ✔  **<u>makes the client simple</u>**.
  - Clients treat composite structures and individual objects uniformly.
  - Clients don't and shouldn't know whether they're dealing with a leaf or a composite.
  - therefore avoid write tag-and-case-statement-style functions over the classes that define the composition.
- ✔  <u>**makes it easier to add new kinds of components**</u>.
  - New Composite or Leaf work automatically with existing structures and client code.
  - Clients don't have to be changed for new Component classes
- ✔  **<u>make your design overly general</u>**
  - While there is a side effect, since you are flexible do a composite:arrow_up_small:, it means you are hard to restrict it:arrow_down_small:.
  - Since composite focus on "GENERAL", you have to use run-time checks for constraints.





:computer:**Implementation**

___

There are many issues to consider when **implementing** the Composite pattern

- ✔  <u>Explicit parent references</u>.
  - [**Why**]  simplify the traversal and management of a composite structure
  - [**How**]  
    - define the parent reference is in the Component class
    - implemented the `Add` and `Remove` operations of the Composite class
- ✔  <u>Sharing components</u>







:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 4.4. Decorator



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 4.5. Facade



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 4.6. Flyweight



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 4.7. Proxy



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 4.8. Discussion of Structural Patterns







# 5.Behavioral Patterns



## 5.1. Chain of Responsibility



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 5.2. Command

🎯**Intent**

___



:muscle:**Motivation**

___



:heavy_dollar_sign:**Applicability**

___



:building_construction:**Structure**

___



:family_man_woman_girl_boy:**Participants**

___



:handshake:**Collaboration**

___



:chart_with_upwards_trend:**Consequence**

___



:computer:**Implementation**

___



:keyboard:**Sample Code**

___



:page_with_curl:**Known Issue**

___



:couple:**Related Patterns**

___





## 5.3. Interpreter



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 5.4. Iterator



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 5.5. Mediator

<div align="center">
    <figure>
        <img src="img/mediator.png" style="width:50%" class="center">
        <figcaption>Mediator ©Dive Into Design Patterns</figcaption>
    </figure>
</div>


🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___












## 5.6. Memento



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___







## 5.7. Observer



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___







## 5.8. State



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___







## 5.9. Strategy



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___





## 5.10. Template Method



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___







## 5.11. Visitor



🎯**Intent**

___









:muscle:**Motivation**

___









:heavy_dollar_sign:**Applicability**

___









:building_construction:**Structure**

___







:family_man_woman_girl_boy:**Participants**

___







:handshake:**Collaboration**

___











:chart_with_upwards_trend:**Consequence**

___











:computer:**Implementation**

___











:keyboard:**Sample Code**

___











:page_with_curl:**Known Issue**

___











:couple:**Related Patterns**

___











## 5.12. Discussion of Behavioral Patterns



# End






# 💭Things I don't Know


# 🍂Unorganized


___
# ℹInformation
**✍Authors:**
**🔗Links:**


[^1]: The elements here refer to instances of Wall, Door, Room

[^2]: Glyph是构成这个UI体系最基础的元素
[^3]: embellish in English: to make something more beautiful by adding decorations to it



[iAbstract Factory]: #31-abstract-factory
[iBuilder]: #32-builder
[iFactory Method]: #33-factory-method
[iPrototype]: #34-prototype
[iSingleton]: #35-singleton

[iAdapter]: #41-adapter
[iBridge]: #42-bridge
[iComposite]: #43-composite
[iDecorator]: #44-decorator
[iFacade]: #45-facade
[iFlyweight]: #46-flyweight
[iProxy]: #47-proxy


[iChain of Responsibility]: #51-chain-of-responsibility
[iCommand]: #52-command
[iInterpreter]: #53-interpreter
[iIterator]: #54-iterator
[iMediator]: #55-mediator
[iMemento]: #56-memento
[iObserver]: #57-observer
[iState]: #58-state
[iStrategy]: #59-strategy
[iTemplate Method]: #510-template-method
[iVisitor]: #511-visitor

