# SOLID Principles

## Content
 - [Single Responsibility](#single-responsibility)
 - [Open Close Principle](#open-close-principle)
 - [Liskov Substitution principle](#liskov-substitution-principle)
 - [Interface Segregation principle](#interface-segregation-principle)
 - [Dependency Inversion principle](#dependency-inversion-principle)
 
 ## Single Responsibility
  - A class should have only one reason to change.
 
 ## Open Close Principle
  - Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
 
 ## Liskov Substitution principle
  - Subtypes must be substitutable for their base types.
  - Matt was supposed to design a class to count the number of products in a shopping cart and calculate the cost of these products. He chooses
to create the Cart class by extending the ArrayList class, and overrides the size method to count the number of different products. Which
principle/concept can best explain why this is a bad idea?
 
 ## Interface Segregation principle
  - Clients should not be forced to depend on methods that they do not use.
 
 ## Dependency Inversion principle
  - High-level modules should not depend on low-level modules. Both should depend on abstractions.
  - Abstractions should not depend on details. Details should depend on abstractions.
