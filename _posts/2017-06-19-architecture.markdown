---
published: true
title: Architecture
layout: post
tags: [cleancode, acrhitecture, refactoring]
categories: [code, design]
---
# Software Architecture

>  "Think in the small like you think in the large." _-Rich Hickey_

Qualities of good code also apply to the bigger picture. Software architecture is about the orginisation of code.

## Separation of Concerns

 * Single purpose components (at all levels - companies,systems,services,..,modules,functions)
   * Small & Simple : Easy to test and maintain
   * Reusable
 * Decouple behaviour and data  
   * Decouple types and functions
   * Messages instead of shared state (Queues, Actors)
 * Pure core with an imperative shell aka Onion / Hexagonal architecture
   * Shell : Limit side-effects to exist only at the domain boundries of a (sub-) system
   * Core  : Minimize impure functions (side-effects, persistance, dependency, errors, etc..) It's possible to have a 100% pure core. 

## Strong domain boundaries
 * Interfaces, abstractions, plug-ins, Web API
 * Messaging systems, Queues
   
## Known (Preferably linear) dependencies
 * Discoverability - how a new developer finds what changes to make on which system(s)
 * Predictability - knowing the impact of software changes throughout a system (domino effect of data streams)
 * Linearity. Languages support this in various degrees - in C# you cannot have a project that is referenced by a project it references in the same solution. Circular dependencies sound convoluted - because they are! In F# the same is true at an even more granular level, where files and code needs to be ordered in order of dependency, akin to how C/C++ would be without the use of forward references. Generic functions and Simple datastructures at the highest level of the system reduce overall complexity. Prefer Composition over Inheritance: Domain Models -> Functions -> More Functions -> Implementations.
 
>  "It is better to have 100 functions operate on one data structure than 10 functions on 10 data structures." _-Alan J. Perlis_

### Leading Architectural patterns / Good reading

#### [Railway Oriented Programming](https://fsharpforfunandprofit.com/rop/)
#### [Event Sourcing / CQRS](http://cqrs.nu/Faq)
   * Structure changes more often than behaviour.
   * Save events, create different projections from events for new views of the data
   * Insert & Read only
   * Most of code is queries (PURE functions) - Optimize your system for reading data, not saving (3NF is over-rated)
#### SOA / Microservices
  * Each subsystem has it's own data
  * Well defined inputs and outputs of each system
  * Request/Response model
#### [Reactive Manifesto](http://www.reactivemanifesto.org/)
 * Responsive
 * Resilient
 * Elastic
 * Message Driven
#### [Clean Architecture](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html)
#### [Ports and Adapers](http://blog.ploeh.dk/2016/03/18/functional-architecture-is-ports-and-adapters/)

# Software Architect

So you want to be an Architect ?

This is the thing most junior developers say as a career progression they want to do after coding. Being a software architect is not about the organisation of code. Some architects claim to write code more than 70% of the time (small companies), however most architects I've spoken to do not write any code at all (usually large companies). The role of an Architect varies greatly from company to company, or within business units (very large companies).
 
What makes architecture different from guidelines for writing good code - is that you give thought of the other services, goals and strategic direction of the business. *In some cases* you have to factor the costs of decisions. For example, when you decide to sign a yearly contract for a 3rd party integration service, or even more fixed - when failure is expensive like in aerospace projects, these decisions are referred to as "hard to change".
 
 ## Software Architect != Software Architecture
 * Think about all stakeholders involved
 * Other aspects than just maintanability, for example:
   * Security
   * Stability
   * Scaling (performance and new software)
   * Operations (mainetance, possible downtime, monitoring)
   * Testing. *Side-note: Interesting approach to testing - Instead of the normal testing pyramid, have much less integration tests (the middle part of the pyramid), and have fantastic operations monitoring that also serve as system tests.*
   * Disaster Recovery   
 * Represent other (smaller) systems in meetings, think about how they will be impacted by changes.
 * Saying No. (Tongue in cheeck) One of my buddies is a Software Architect at a large bank, and reports being a Software Architect is just saying "No" 70% of the time. There is merit in that he cannot simply say yes to any proposals, as there are a lot of things to consider.
 * Never delete e-mails
 * Negotiate
 * Documentation
 * A mediator between business strategy, operations and developers.

> “Truth can only be found in one place: the code.” -_Robert C. Martin_
##### - Christoph Alrich [@ideaflare](https://twitter.com/ideaflare)
