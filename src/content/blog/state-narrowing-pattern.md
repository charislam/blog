---
title: 'The state narrowing pattern'
description: ''
pubDate: ''
draft: true
---

In React, view is a function of state.
If your state changes, what your user needs to see changes, and a rerender is triggered to display it.

Levels of state management:
- `useState`
- `useReducer`
- Stately

Between `useState` and `useReducer`: the state narrowing pattern

## The state narrowing pattern

I'm not going to pretend this is a new discovery, but I've never seen it blogged about before.

## Isn't this just an inlined custom hook?

Well...yes.

And if you prefer to write it that way, you could.
In fact, if you're going to reuse the logic, you probably should.

All you need to do is: