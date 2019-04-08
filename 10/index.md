# 10: New Kinds of Data

[see `data.ml`](/10/data.ml)

Yes, now we learn about the option type which is the equivalent of Haskell's
`Maybe`, and is a great way to replace impure exceptions with pure types.

Interesting that `(*)` is parsed as a comment, and `( * )` is parsed as the
multiplication function.

## Questions

### 5

So looks like in OCaml there's no special distinction between tuples and product
types syntactically. So any constructor of a product is written like its a
constructor of a tuple. I kind of like this, because, yes, product types and
tuples are isomorphic. On the other hand, it's a little syntactically messy
compared to Haskell.

### 7

Interesting that this way of doing `safeEval` returns `None` rather than `Some
None`. Exceptions just throw away their context, but I wonder if there's
a way to handle them while preserving the context.


