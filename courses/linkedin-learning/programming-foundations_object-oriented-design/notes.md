# Programming Foundations: Object-Oriented Design

[Programming Foundations: Object-Oriented Design](https://www.linkedin.com/learning/programming-foundations-object-oriented-design-3/objects?autoSkip=true&resume=false)

## Object-Oriented Fundamentals

- object-oriented
  - analysis: understand the problem
  - design: plan your solution
  - programming: build your solution
- Procedural vs OOP
- all objects have:
  - identify: e.g. Olivia's coffee mug
  - attributes: color, size, fullness
    - can also be called: properties, characterisitics, state, fields, variables
  - behaviors: fill(), empty(), clean()
    - can also be called: methods
- objects = nouns (things, people, places, ideas, concepts), you can put the word "the" in front of it
- bahaviors = verbs
- classes to create objects
- class: code-template for creating program objects
  - class components:
    - name (or type)
    - attributes (or properties)
    - behaviors (or operations)
      - Method: a program procedure defined as part of a class that can return a value
- 4 fondamental ideas when creating classes (APIE)
  - Abstraction (focus on essential qualities of something)
  - Polymorphism ()
    - dynamic polymorphism: uses the same interface for methods on different types of objects
      - method overriding: inherit a method and override it
    - static polymorphism: method overload, e.g. vtk GetPoint()
      - method overloading: implements multiple methods with the same name but different parameters
  - Inheritance (base a new object or class (subclass) on an existing one (superclass) to inherit existing attibutes and methods)
    - code reuse
  - Encapsulation (restricting access - an object should not make anything about itself, e.g. hide attribute and only accessible with methods) [Black Boxing]
    - to reduce dependencies

## Requirements

- analysis and design approach
  1. gather requirements
  1. describe the app
  1. identify main objects
  1. describe the interactions
  1. create class diagram
- Unified Modeling Language (UML): standardized notation for diagrams to visualize object-oriented systems
- class diagram

    | Name       |
    | ---------- |
    | Attributes |
    | Behaviors  |

- use case diagram
- functional requirements: what must it do?
  - the system/app must do ...
- non-functional requirements: how should it do it? (legal, performance, support, security)
  - the system/app should be ...
- FURPS+ requirements
  - Fonctionality: capability, reusability, security
  - Usability: human factors, aesthetics, consistency, documentation
  - Reliability: avaialability, failure rate & duration, predictability
  - Performance: speed, efficiency, resource comsumption, scalability
  - Supportability: testability, extensibility, serviceability, configurability
  - +: design, implementation, interface, physical

## Uses Cases and User Stories
