---
published: false
title: Practical refactoring
layout: post
---
#What is refactoring ?

It's about improving code. Highlights being:

* Good communication _via_
  * Removing duplication 
  * Improving names

* Easy to understand, test and re-use _via_
  * Making everything (classes, methods, services, etc..) small so they have a single purpose
  * Decoupling and minimizing the number of dependencies

#Why refactor ?

> Refactoring reduces the risk of change, while improving the ease of change.

Refactoring makes extending software easy, maintaining existing code less dreadful, hunting bugs less frequent and easier to isolate. Working in clean code is **fun**; it makes you more productive and [happy](http://stackoverflow.com/research/developer-survey-2016#developers-who-code-are-happy-developers).

#When to refactor ?

**Now** is always the best time. There often won't be time to do it later, and refactoring after the work has been completed is _subjective_.

##Wait, _subjective_ ?

> They boy scout rule - "Always leave the campground cleaner than you found it"

Taking pride in your work feels really great - to know you did your best. This isn't true for everyone, not all developers are passionate about what they do or want to be 'software craftsmen'. Saying "just get rid of all the plain developers and hire great ones!" is a cop-out, that doesn't actually address the root of the problem: 

Adding new features or changing existing behavior of software increases it's complexity, and the system becomes more and more difficult to change each time. The only way to keep software from rotting is by recognizing the need to reduce complexity. So, the **value** of refactoring, irrespective of human emotion, is to support a sustainable pace of development - so that you (or the next person) in a future not too far from now can work on the software with continued momentum.

> Clean code is minimizing the time spent from looking at code for the first time, until you can make a confident change.

But how do you know what parts of code to clean, how can you predict where to change next ? Wouldn't it be great if there was an *objective* way that provides feedback and takes out the guesswork of where refactoring will help the most ?

#Where to refactor

You have the most information about *where* to streamline the moment you interact with them. This applies to the code you just wrote, but equally so to existing code. By following "If you touch it, clean it." the same code that gets worked on many times won't be a hindrance and code that doesn't get worked on frequently won't be refactored more than what is practically meaningful. When touching the same code many times, think about how you can [separate the parts that change from the parts that stay the same](https://en.wikipedia.org/wiki/Open/closed_principle). If you refactor while you code, you also have a much better idea of *how* to improve the code because you still have the context fresh in your mind.

# In conclusion

> Prefer floss refactoring over root canal refactoring.

Clean as you go, even if it's just renaming a variable or deleting unused code.

##### - Christoph Alrich [@ideaflare](twitter.com/ideaflare)