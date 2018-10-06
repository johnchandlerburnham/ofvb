---
title: "Notes (OFVB 11/31): Growing Trees"
author: jcb
date: 2018-10-05
---

see `trees.ml`

Really missing the `Functor` and `Foldable` typeclasses here. My `foldMap` isn't
really a `foldMap`, since it needs a ternary function and an explicit `mempty`,
but it's still useful. You can see how much shorted the `maxDepth` and
`list_of_tree` functions are with `foldMap`.

# Questions

## 5

This is slow, a better way would be to write a `Traversable` instance, or even a
`foldr`. But I'm not going to this here, since that's a lot of plumbing.

## 6

One interesting addition would be a `maxDepth` function on our `polyTree`, but
again, lots of plumbing and I feel like these abstractions are starting to creak
a little bit.


