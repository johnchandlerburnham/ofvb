# 12: In and Out

[See `io.ml`](/12/io.ml)

## Questions

### 2

I wonder why `()` has to be passed to functions that do `IO`.

### 3
Using `^D` as `EOF` seems appropriate here. But this takes some creative piping
and needs us to define a `result` type:

```ocaml
 type ('a, 'e) result = Ok of 'a | Error of 'e
```

which lets us raise the exceptions generated in the inner reads in the outer
`with` block.

### 4

This is tricky! I decided I needed string concatenation, so I added an `open
String` at the top of the file.

My `range` function is pretty bad though, I'm definitely missing Haskell's
laziness and ability to just take from infinite lists.

### 5

My exception raising trick with the `result` type is useful!

### 6

It's interseting that the file doesn't actually write until the output channel
is closed.
