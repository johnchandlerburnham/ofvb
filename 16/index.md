---
title: "Notes (OFVB 16/31): Building Bigger Programs"
author: jcb
date: 2018-10-07
---

Erratum: Should be `ocamlc textstat.ml`, not `ocamlc textstate.ml`

If you compile with the interface file second with:

```
ocamlc textstat.ml textstat.mli
```

You get an

```
Error: The files textstat.cmo and textstat.cmi make inconsistent assumptions
       over interface Textstat
```

You need to compile with the interface first.

# Questions

## 1

see `stats/stats.ml`

## 2

see `reverse/reverse.ml`

## 3

see `compare/fact.ml`

Need `nums.cma` for `ocamlc` and `nums.cmxa` for `ocamlopt`.

Compiling with `ocamlc`, `factorial 100000` took 10 seconds. With `ocamlopt`,
also 10 seconds.

## 4

see `search/search.ml`
