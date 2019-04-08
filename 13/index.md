# 13 Putting Things in Boxes

[See `boxes.ml`](/13/boxes.ml)

This mix of functional and imperative is really interesting.

There is an erratum in the the `file_statistics` declaration:
`file_statistics_channel` should be `channel_statistics`.

I kind of like the way mutation and array syntax works. It's very imperative,
but very accessible.  In Haskell, we'd do something with `Vector`, `MVector` or
`MVar`, which are all a little more conceptually complicated. I suspect that
complexity is actually just inherent in mutation, so learning the various
Haskell mutation types `IORef`, `MVar`, `TVar`, are actually really useful,
whereas I suspect the OCaml abstraction might be trading off immediate ease of
use for complexity wrinkles later on. That's only a supposition though,
we'll see how that plays out as I learn more.


## Questions

### 1

References `x` and `y` have been created. Initial values are `!x = 1`, `!y = 2`,
final values are `!x = 2`, `!y = 4`. The expression evaluates to `6` with type
`int`.

### 2

The difference is that in the first case we have a list of two different
references, whereas the second is a list of two identical references. So
updating either reference in the second list changes the value the other ref
points to, because both refs point to the same place.

```ocaml
utop # updateRefListHead twoRef 6;;
- : int ref list = [{contents = 6}; {contents = 5}]
utop # updateRefListHead oneRef 6;;
- : int ref list = [{contents = 6}; {contents = 6}]
```

### 3

We could just use recursion or a `while` with an explicit iteration variable.

### 4

- `int array`
- `bool array`
- `int array array`
- `int list array`
- `int`
- `unit`

### 5

So we could do this in a pure way with a fold, but it feels like OCaml wants me
to use a `ref` and a `for` with an imperative style and I don't want to fight the
language too much while I'm learning it.

### 7

Interesting! `Array.make` is a reference! So, `Array.make n (Array.make n 0)`
actually only makes an array of references to the same array! So we'll use
`Array.make_matrix` instead.

### 8

Ascii upper and lower characters only differ by a single bit (the second high
bit), which we can flip by adding or subtracting by `2^5 = 32`.

### 9

This `channel_statistics` function is going to undercount the number of words if
words don't end with spaces, but with tabs, newlines or an EOF.

### 10

So to fix the word undercounting we can count the words per line with
`(List.length (String.split_on_char ' ' line))`.
