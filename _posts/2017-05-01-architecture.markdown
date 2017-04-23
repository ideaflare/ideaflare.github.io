---
published: false
title: Architecture
layout: post
tags: [cleancode, refactoring]
categories: [code, design]
---
# What makes Architecture

 * Linear dependencies
   * Pure -> Impure
   * General -> Specific
   * Domain Models -> Functions -> More Functions -> Implementations
 * Single purpose modules
   * Small
   * Simple
   * Reusable
 * Messages instead of shared state (Queues, Actors) 'Think in the small like you think in the large'-Rich Hickey
 * A functional core with strong domain boundaries at the edges of any (sub-) system:

#[The Four Horsemen of the Catapocalypse](https://cdsmith.wordpress.com/2012/04/18/why-do-monads-matter/)
 * Failure
 * Destruction
 * Uncertainty
 * Dependence
