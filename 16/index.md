# 16 Building Bigger Programs

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

## Questions

## 1

[See`stats/stats.ml`](/16/stats/stats.ml)

### 2

[See`reverse/reverse.ml`](/16/reverse/reverse.ml)

### 3

[See`compare/fact.ml`](/16/compare/fact.ml)

Need `nums.cma` for `ocamlc` and `nums.cmxa` for `ocamlopt`.

Compiling with `ocamlc`, `factorial 100000` took 10 seconds. With `ocamlopt`,
also 10 seconds.

### 4

[See`search/search.ml`](/16/search/search.ml)
