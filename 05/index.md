---
title: "Notes (OFVB 05/31): Sorting Things"
author: jcb
date: 2018-10-03
---

see `sort.ml`

Okay, so a couple things here. First, it looks like OCaml scopes everything
after its declaration, so expressions can only call expressions declared above
itself. This is annoying, but is partially fixable by declaring auxilliary
functions with a `let`-`and` block.

Secondly, the ocaml repl is not very user friendly. No arrow keys, no command
history. We could solve this with `rlwrap`, which is a general tool for adding
line editing features to a program, but I like to keep things in-ecosystem as
much as possible, so we'll use
[`utop`](https://opam.ocaml.org/blog/about-utop/).

But, since this is NixOS, I don't want to pollute my global environment with
`nix-env -iA nixos.ocamlPackages.utop`, instead I want to use a `nix-shell`. My
`default.nix`:

```
with import <nixpkgs> {};
  stdenv.mkDerivation rec {
    name = "ocamlProject";
    src = null;
    buildInputs = with ocamlPackages;
    [ ocaml
      opam
      utop
    ];
  }
```

# Questions

[see `sort.ml`](https://github.com/johnchandlerburnham/ofvb/blob/master/05/sort.ml)

## 2

I have modified `take` and `drop` to never fail, since they now take and drop
greedily, i.e. `take 5 []` returns `[]`, which makes `take 6 [1]` return `[1]`

## 3

Just requires flipping the `<=` to a `>=`.

## 5

Lists are sorted in "alphabetic word order", which is characterwise comparison
where the leading entry is most determinant, e.g. `[1; _ ] < [2; _]`.


