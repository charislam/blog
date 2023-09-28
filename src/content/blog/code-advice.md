---
title: 'Code advice considered harmful'
description: 'Learning to ignore is just as important as learning to listen.'
pubDate: 'Sept 21 2023'
---

The first code style book recommended to me was Clean Code.
The first code I wrote after reading it was heavily class-based, full of one-line functions with long and descriptive names.

A few months later, I read Mastering JavaScript Functional Programming.
The first code I wrote after that was full of tiny, pure functions, often curried.

Those things weren't necessarily bad.

Classes turned out to be the right tool for the first problem: modelling site pages, which came in different but related flavors.
Extending a base class made it easy to add new page types.
Likewise, pure functions made it easy to debug finicky time conversions and interval comparisons.

But they also weren't entirely good.

Going back to the first code six months later, I found those descriptively named one-liners not so descriptive after all.
Maybe it was a naming problem.
(*Two hard problems in computer science, etc.*)
But I think it was a chunking problem.

We encapsulate code into new functions (in part) to take the load off our short-term memory.[^1]
When we have too many tiny details to track, we lose sight of the larger structure, the higher level of abstraction.
Plotting 1 000 000 individual trees on a tiny map makes a mess.

But when the number of details is small, the abstraction itself becomes pure overhead.
I needed to know exactly what those one-liners did to make the changes I intended.
So I jumped back and forth between function call and definition, function call and definition...
The jumping was more distracting than reading the inlined function would have been.

Sometimes, if code is small enough to fit in your head, you just want to put it in your head.
Descriptive names are good, but they're not a substitute for the real thing.
(And if the name is long enough and the function short enough, is it easier to parse the name or the function?)

This isn't an argument that one-liner functions are always bad.
Exactly the opposite.
My point is that you shouldn't listen to me either.
Or rather, listen, but be prepared to ignore.[^2]

In our drive to improve ourselves, to listen to "best practices" and "the voice of experience", we can be too easily influenced.
Especially when the voice of experience is particularly dogmatic (*cough* Robert Martin *cough*).

But advice, even from the best of people, isn't always good.
Even once-good advice grows stale.
Tech is a fast-changing discipline.
And good, fresh advice might fit 99% of problems, but not yours.
(For every good recommendation, there's often an equally good recommendation that suggests the exact opposite.
If every piece of advice was unconditionally true, the world would make no sense.)

Being too easily influenced is as much a problem as never listening at all.

So how do we listen without being easily swayed?
How do we stand on the shoulders of giants, but learn to jump off when we see the stake-filled trap ahead?

Paradoxically, part of the answer is to listen more.
I was particularly swayed by Clean Code because it was the first book I'd read specifically about clean coding style.
Read more differing perspectives on every topic, and it quickly becomes apparent that they can't all be right.

A second answer is to read more, specifically more code.
Examples in books and blog articles are, by necessity, short and impractical.
There are no genuine trade-offs, no overarching context.
Real projects contend with complex issues and pressing requirements.
They bring theory down to the muddy world of reality, where nothing is ever quite pure.
And fortunately, there's more battle-tested real code (with decisions and debates documented in issues and PRs) on the Internet than anyone could read in one lifetime. 

The last antidote is experience.
It's unfortunate, because we should be able to shortcut our learning from others' experience, right?
That's what "shoulders of giants" is all about!
But in practice, maintainable code is in part about taste.
(Perhaps that's why we talk about code *smells*.)
And taste is visceral.

Be surprised by a lot of your own code after six months (works whether the surprise is good or bad), and you develop a reflexive reaction.
Crucially, that reaction encloses context on your particular problem and path: you followed this advice one time, and it didn't go so well, but it worked another time.
You went your own way, and that was both disaster and victory.

I like to summon that visceral experience, as much as I can.
"Imagine that I'm me, working on this code in six months. Which choices will make me kick myself, and which will make me pat myself on the back?"[^3]

Don't think about having to write clean code in the moment, divorced from the passage of time.
It's too academic.
Everything is understandable when you first write it, and all theories sound good when everything is understandable.
Summon the you who's polluted by time, who's confused and cursing yourself, or who's in the flow, dropping seamlessly back into code from a year ago.
Write for that you.
That you doesn't care what pattern or theory you used, so long as their life is easy when their time comes.

My flock of imaginary mes and I are much less easily influenced these days.
Which means, despite the title of this post, I don't consider any advice harmful.
Bring it at me; I'd love to hear your comments.[^4]

[^1]: There are other reasons, of course: easier testing, limiting the blast radius of changes and refactors, making code DRY.
[^2]: Granted, you were probably readier to ignore a random blogger on the Internet than one of the opuses of the field.
[^3]: Of course, we write code for other people to read too. But we are selfish creatures locked within our own perspectives, which makes it much easier to sense these things in terms of our own experience. Besides, code written by you, sufficiently long ago, might as well have been written by someone else.
[^4]: I haven't built a comment function for this blog yet, but the [GitHub repo](https://github.com/charislam/blog) is open source and open to discussion!
