---
title: "Notes (OFVB 04/31): Making Lists"
author: jcb
date: 2018-10-03
---

see `lists.ml`

Inner recursion functions shouldn't be exposed outside of the scope of the
function they're being used for. Beter to define `go` function with a `let`.

Making `take` and `drop` total functions only requires adding an additional
pattern to match on. Nested matching is a little clunkier than how Haskell does
it though, so I hope there's more advanced syntax to learn later on.


# Questions

[see `lists.ml`](https://github.com/johnchandlerburnham/ofvb/blob/master/04/lists.ml)

## 1

Type of `evens` is `a' list -> a' list`

## 2

We certainly can write a tail-recursive version of this, but I think it's more
interesting to use an inner function to give us an explicit accumulator. Really
this should be done with a fold, but we haven't covered that yet.

## 4

Here's a case where tail recursion makes sense.

## 6

Type of `make_set` is `a' list -> a' list`

## 7

`rev` is inefficient because `@` is `O(n)` with respect to the length of t,
every time it's called. Because `@` gets called on every `::`, this makes `rev`
`O(n^2)`.

My `reverse` function in `lists.ml`, is `O(n)` with respect to the length of the
list since it calls `::` (which is `O(1)`) once for every list element.

