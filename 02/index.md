---
title: "Notes (OFVB 02/31): Names and Functions"
author: jcb
date: 2018-10-02
---

# 2: Names and Functions"
On my system, `max_int` is 2^62 - 1, `min_int` is (-2)^62. Apparently OCaml
uses the extra bit for some internal pointer magic.

## Questions

### 1

```ocaml
# let f x = x * 10
val f : int -> int = <fun>
```

### 2

```ocaml
# let f x y = x <> 0 && y <> 0;;
val f : int -> int -> bool = <fun>
```

### 3

```ocaml
# let rec f x = if x = 1 then 1 else x + f (x - 1);;
val f : int -> int = <fun>
```

### 4

```ocaml
let rec power x n = if n = 0 then 1 else x * f x (n - 1);;
val power : int -> int -> int = <fun>
```

### 5

```ocaml
# let isVowel c = c = 'a' || c = 'e' || c = 'i' || c = 'o' || c = 'u';;
val isVowel : char -> bool = <fun>
# let not x = if x then false else true;;
val not : bool -> bool = <fun>
# let isConsonant c = not (isVowel c);;
val isConsonant : char -> bool = <fun>
```

### 6

```ocaml
# let x = 1 in let x = 2 in x + x;;
Warning 26: unused variable x.
- : int = 4
```

OCaml searches bindings from inside to outside, so only the `let x = 2` matters.

### 7

```ocaml
# let rec factorial a = if a <= 0 then 0 else
    if a = 1 then 1 else a * factorial (a - 1);;
val factorial : int -> int = <fun>
```



