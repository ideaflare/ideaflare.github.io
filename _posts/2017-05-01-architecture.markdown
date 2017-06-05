---
published: false
title: Architecture
layout: post
tags: [cleancode, refactoring]
categories: [code, design]
---
# What makes Architecture

## Separation of Concerns
 * Linear dependencies
   * Pure -> Impure
   * General -> Specific
   * Domain Models -> Functions -> More Functions -> Implementations
 * Single purpose modules
   * Small & Simple : Easy to test and maintain
   * Reusable
 * Decouple behaviour and data  'Think in the small like you think in the large'-Rich Hickey
   * Decouple types and functions
   * Messages instead of shared state (Queues, Actors)
 * A functional core with strong domain boundaries at the edges of any (sub-) system:
   * Minimize impure functions (side-effects, persistance dependency, etc..)

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
