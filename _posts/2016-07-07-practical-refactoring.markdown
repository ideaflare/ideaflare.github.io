---
published: true
title: Practical refactoring
layout: post
tags: [cleancode, refactoring, practices, craftsmanship]
categories: [code, practices]
---
## What is refactoring ?

It's about improving code. Highlights being:

* Good communication _via_
  * Removing duplication 
  * Improving names
  * Organizing

* Easy to understand, test and re-use _via_
  * Making everything small so they have a single purpose (classes, methods, services, etc..) 
  * Decoupling and minimizing the number of dependencies

## Why refactor ?

> Refactoring reduces the risk of change, while improving the ease of change.

Working in clean code is **fun**, it makes you more productive and [happy](http://stackoverflow.com/research/developer-survey-2016#developers-who-code-are-happy-developers).

Refactoring makes:

* extending software easier
* maintaining existing code less dreadful
* hunting bugs less frequent and easier to isolate. 

## When to refactor ?

**Now** is always the best time. There often won't be time to do it later, and refactoring after the work has been completed is _subjective_.

### Wait, _subjective_ ?

> They boy scout rule - "Always leave the campground cleaner than you found it"

Taking pride in your work feels really great - to know you did your best. This isn't true for everyone, not all developers are passionate about what they do or want to become 'software craftsmen'. To manage legacy using a strategy like "just hire more developers!" is a cop-out, that doesn't actually address the root of the problem: 

Adding new features or changing existing behavior of software increases it's complexity, and the system becomes more and more difficult to change each time. The only way to keep software from rotting is by recognizing the need to reduce complexity. The **value** of refactoring, is to support a sustainable pace of development - so that you _(or the next person)_ in a future not too far from now can work on the software with continued momentum.

> Clean code minimizes the time spent from looking at code for the first time to making a confident change.

But how do you know which parts of code to clean? How can you predict where to change next? Wouldn't it be great if there was an *objective* way that provides feedback and takes out the guesswork of where refactoring will help the most?

## Where to refactor

You have the most information about *where* to streamline components the moment you interact with them. This applies to the code you just wrote, but equally so to nearby existing code. Follow the principle **"If you touch it, clean it."** In this way the same code that gets worked on/with many times won't be a hindrance. Conversely, code that doesn't get worked on/with frequently won't be refactored beyond what is practically meaningful.

When touching the same code many times, think about how you can [separate the parts that change from the parts that stay the same](https://en.wikipedia.org/wiki/Open/closed_principle). If you refactor while you code, you also have a much better idea of **how** to improve the code while you still have all the context fresh in your mind.

## In conclusion

> Prefer floss refactoring over root canal refactoring.

To keep things simple - cultivate the habit to clean as you go, even if it's just renaming a variable or deleting unused code :)

##### - Christoph Alrich [@ideaflare](https://twitter.com/ideaflare)