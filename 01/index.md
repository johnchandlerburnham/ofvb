---
title: "Notes (OFVB 01/31): Starting Off"
author: jcb
date: 2018-10-02
---

# Questions

## 1

- `- : int = 17`
- `- : int = 11`
- `- : int = 1`, this shows `/` has left precedence
- `- : bool = true`
- `- : bool = false`, `<>` is "not equal", which is super confusing notation.
- `- : bool = true`
- `- : bool = false`
- `- : bool = false`
- `- : char = '%'`
- error, because `(+)` has type `- : int -> int -> int = <fun>`

## 2

`mod` has higher precedence than `+`

## 3

evaluates to `11`, spaces don't matter

## 4
`max_int + 1` is `min_int`, and `min_int - 1` is `max_int`

## 5

`Exception: Division_by_zero`

## 6

`mod` is just remainder after integer division, with the negative sign following
the dividend (the first arg).

## 7

Because although there is some structural analogy between `{true, false, &&, ||}`
and `{1, 0, *, +}`, the former is closed and the latter is not. E.g. `true ||
true = true`, but `1 + 1 = 2`. The values `1` and `0` live in a bigger space of
values, i.e. the integers. We use types to restrict the space of possible
values in our code, so that if we accidentally call a function expecting an
integer with a boolean argument, we find out our mistake at compile-time rather
than at run-time.

## 8

`'p' < 'q'` is `true`, because `p` comes before `q` in the alphabet. I look
forward to learning how and where OCaml defines the `char` ordering.




