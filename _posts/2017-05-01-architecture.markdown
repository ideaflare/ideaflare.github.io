---
published: false
title: Practical refactoring
layout: post
---
#What makes Architecture

-> Linear dependencies
-> Single purpose modules
-> Messages instead of shared state (Queues, Actors) 'Think in the small like you think in the large'-Rich Hickey
-> A functional core with strong domain boundaries at the edges of any (sub-) system:

#[The Four Horsemen of the Catapocalypse](https://cdsmith.wordpress.com/2012/04/18/why-do-monads-matter/)
 * Failure
 * Destruction
 * Uncertainty
 * Dependence
