---
title: "Notes (OFVB 07/31): When Things Go Wrong"
author: jcb
date: 2018-10-04
---

see  `wrong.ml`

Reworked `take` and `drop` to use pattern matching rather than nested `if`s.

# Questions

## 2

Trying and catching here seems not as good as just using a fold with a `0`
default.

## 5

In my opinion, pure code is easier to reason about than impure code. Exceptions
are inherently impure, and therefore are much better suited to IO than to e.g.
the math examples in this chapter. In such cases, it is better to restrict the
domain of function inputs, than extend the range of function outputs. A Natural
number type is a better solution to the `sqrt_floor` problem, than a
`NegativeArgument` exception. The former reduces the complexity of our code, the
latter adds to it. Sometimes the only way to solve a problem is by adding
complexity, but as a genral rule of thumb, the lowest complexity approach is
usually best.
