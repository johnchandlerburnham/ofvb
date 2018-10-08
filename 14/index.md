---
title: "Notes (OFVB 14/31): The Other Numbers"
author: jcb
date: 2018-10-07
---

Okay, here's one thing I find a little strange. Tuples are to be polymorphic
with respect to each element (so `(a,b)` is the product of `a` and `b`). In
Haskell, if we want a monomorphic pair, we can either make an `(a,a)`
tuple, or better yet we declare a type constructor:

```haskell
data Pair a = Pair a a`.
```

But in OCaml, we're limited to doing:

```ocaml
type 'a pair = Pair of 'a * 'a
```

But when we want to make a `Pair` in OCaml, we write `Pair (1,2)` with syntax
that looks like tuples, vs Haskell's `Pair 1 2`.

I wonder if this is because OCaml only has rank-1 parametric polymorphism, since
the `Pair` constructor can't be partially applied like it can in Haskell:

```haskell
> data Pair a = Pair a a
> :t Pair 'c'
Pair 'c' :: Char -> Pair Char
```

We can make a function in OCaml that mimics this:

```ocaml
type 'a pair' = Pair of 'a * 'a
# fun x -> Pair ('c',x);;
- : char -> char pair' = <fun>
```

Actually, I think that specific example is due to OCaml being strict and Haskell
being lazy. The difference in parametric polymorphism rank is:

```haskell
> data Pair a b = Pair a b
> :k Pair
Pair :: * -> * -> *
> :t Pair 'c'
Pair 'c' :: b -> Pair Char b
> type PairOfChar = Pair Char
> :k PairOfChar
* -> *
```

And in Ocaml:

```ocaml
# type ('a,'b) pair' = Pair of 'a * 'b;;
type nonrec ('a, 'b) pair' = Pair of 'a * 'b
# type 'a pairOfChar = PairOfChar of  char * 'a ;;
type 'a pairOfChar = PairOfChar of char * 'a
```

So very similar! Except all kinds in Ocaml are `* -> *` and higher-rank
polymorphism is simulatedc with `(*, *) -> *` instead of `* -> * -> *`

---

Are we seriously using `+.` for floating point addition? Really? There isn't
some way to overload `+` to do what we want? smh, OCaml.

# Questions

## 5

I dislike how IO heavy this exercise is. Like, I guess I could do this in a
totally pure way with recursion, but the language really seems to want to make
it easy to use refs and loops more than making it easy to recurse.

I ran into an `Invalid argument: Bytes.create` exception, and it was rather
unclear at first why that would be.  Apparently, `String.make` uses
`Bytes.create` under the hood, but this was not apparent from the exception.

OCaml seems focused on using exceptions to communicate issues rather than using
types.


