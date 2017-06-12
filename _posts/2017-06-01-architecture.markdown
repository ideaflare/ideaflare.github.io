---
published: false
title: Architecture
layout: post
tags: [cleancode, acrhitecture, refactoring]
categories: [code, design]
---
# What makes good Architecture

>  "Think in the small like you think in the large." _-Rich Hickey_

If you know qualities of good code, apply the same principles to the bigger picture. A system (or system of systems) is simply a grouping of many components, and it shares many of the same challenges that code has, like how to discover where to add/modify behaviour.

## Separation of Concerns

 * Single purpose components (al all levels - companies,systems,services,..,modules,functions)
   * Small & Simple : Easy to test and maintain
   * Reusable
 * Decouple behaviour and data  
   * Decouple types and functions
   * Messages instead of shared state (Queues, Actors)
 * A functional core with strong domain boundaries at the edges of any (sub-) system:
   * Minimize impure functions (side-effects, persistance dependency, etc..)   

## Strong domain boundaries
 * Queues, interfaces, abstactions
 * Messaging systems
   
## Linear dependencies

Core idea being that data flows in one direction, like a river that only goes down-stream.

Languages support this in various degrees - in C# you cannot have a project that is referenced by a project it references in the same solution. Circular dependencies sound convoluted - because they are! In F# the same is true at an even more granular level, where files and code needs to be ordered in order of dependency, akin to how C/C++ would be without the use of forward references.

  * Pure core -> Impure shell
  * Generic -> Specific
  * Domain Models -> Functions -> More Functions -> Implementations
  
#### Event Sourcing / CQRS when applicable (which is most systems)
   * Structure changes more often than behaviour.
   * Save events, create different projections from events for new views of the data
   * Insert & Read only
   * Most of code is queries (PURE functions) - Optimize your system for reading data, not saving (3NF is over-rated)

### Single purpose

A running program can have various unexpected burps, which too often results in exceptional patch-like code to deal with edge cases. Dealing with the potential problems up-front requires more thought and work, but the result is having much less to think about for surrounding code. The less context you need to understand a component, the easier it is to re-use and compose larger components from smaller ones.

#### [The Four Horsemen of the Catapocalypse](https://cdsmith.wordpress.com/2012/04/18/why-do-monads-matter/)
* Failure
* Destruction
* Uncertainty
* Dependence

 ##### Failure

You can think of this as any exception that is thrown - out of memory, file not found, network timeout - anything! If there is a point where an error can occur that goes unhandled, one (or often multiple duplicated) logic resides elsewhere to deal with unexpected execution. One way to deal with these kinds of errors is to do a try/catch immediately where such an error can occur. Rather than allowing errors to bubble up, return concrete results. 
  
 ##### Destruction
 ##### Uncertainty
 ##### Dependence
 
  Depending on the context - a normal return value can be enough, if you don't care about specific details of failure a Maybe/Option type is could be fine - and if the detail of failure is important a Try (or Either) could be needed too. What's important is that the return type of the function is reliable - otherwise you'll have wrong assumptions based on wrong assumptions throughout the code base.
 
 
 What makes architecture different from guidelines for writing good code ?
 A thought of the business functions and services, goals and strategic direction of the business and maybe also costs of decisions ?
