---
title: 'Python, three years later'
description: 'Languages are tricksy beasts.'
pubDate: 'Sept 28 2023'
---

I recently had occasion to come back to Python, which I last wrote three years ago.
My daily language for work is JavaScript/TypeScript, and it's the one I'm most fluent in now.

Languages, it turns out, are tricksy beasts.
Each is lovely and expressive in its own way, but sometimes, you forget its little personality quirks and pet against the grain of its fur.

Some quirks (good and bad) that I'm reacquanting myself with:

1. Explicit passing of `self` to methods.
   I like it.
   JavaScript's `this` is a powerful tool, liable to turn in the hand of its holder.
   Part of the problem is its global nature: it always refers to *something*, even if you're in strict mode and that something is `undefined`.
   You can always write it, but you don't always get what you think you're writing.
   Another is its implicitness.
   Of the four methods for binding a call site, three are implicit.[^1]
   `self` (which needn't be called self, it's just a function parameter) keeps things contained and clear.

1. Some things get clearer and others get muddier.
   Creating a new variable and reassigning an existing one use the same syntax (a simple `=`), so you have to be careful which you're doing.
   Python opts for `nonlocal` and `global` to mark scope, which *implicitly* affects what `=` means.
   It could be creating a new local variable or reassigning one in an outer scope.
   (Or even creating a variable in the global scope, while hiding inside your local function.)
   Maybe it's a matter of what I'm used to, but it takes my head for a bit of a spin.[^2]

1. Sorting of numbers works more or less as expected.
   JavaScript's quirks shine through whenever type coercion enters the conversation, and that's as true for sorting arrays as for that pesky `==` operator.
   I do not, in general, want to sort an array of numbers by Unicode order of their string representation.
   Python gets that.

##### Footnotes

[^1]: In order: (1) calling a function with `new`, (2) explicitly binding with `call`/`apply`/`bind`, (3) calling as a method on an object, and (4) the default.
[^2]: JavaScript is no stranger to strange scoping rules, but shush, let us forget the dark days.
