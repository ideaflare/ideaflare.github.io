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

### [The Four Horsemen of the Catapocalypse](https://cdsmith.wordpress.com/2012/04/18/why-do-monads-matter/)
 * Failure
 * Destruction
 * Uncertainty
 * Dependence
 
 What makes architecture different from guidelines for writing good code ?
 A thought of the business functions and services, goals and strategic direction of the business and maybe also costs of decisions ?
