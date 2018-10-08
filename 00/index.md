---
title: "Notes: OCaml from the Very Beginning by John Whitington"
author: jcb
date: 2018-10-02
tags: ofvb, ocaml
---

![](/images/ofvb-cover.jpg)

# Contents

- [Chapter 01: Starting Off](/projects/ofvb/01)
- [Chapter 02: Names and Functions](/projects/ofvb/02)
- [Chapter 03: Case by Case](/projects/ofvb/03)
- [Chapter 04: Making Lists](/projects/ofvb/04)
- [Chapter 05: Sorting Things](/projects/ofvb/05)
- [Chapter 06: Functions upon Functions upon Functions](/projects/ofvb/06)
- [Chapter 07: When Things Go Wrong](/projects/ofvb/07)
- [Chapter 08: Looking Things Up](/projects/ofvb/08)
- [Chapter 09: More with Functions](/projects/ofvb/09)
- [Chapter 10: New Kinds of Data](/projects/ofvb/10)
- [Chapter 11: Growing Trees](/projects/ofvb/11)
- [Chapter 12: In and Out](/projects/ofvb/12)
- [Chapter 13: Putting Things in Boxes](/projects/ofvb/13)
- [Chapter 14: The Other Numbers](/projects/ofvb/14)
- [Chapter 15: The OCaml Standard Library](/projects/ofvb/15)
- [Chapter 16: Building Bigger Programs](/projects/ofvb/16)

# Preliminaries: Getting Ready

Since I'm running NixOS:

```
$ nix-env -iA nixos.ocaml
$ ocaml
```

This book seems mostly designed to be done from the REPL for the first parts.
The default OCaml REPL is a little bare-bones (doesn't even have arrow keys), so
in [Chapter 05: Sorting Things](/projects/ofvb/05) I wrote a `default.nix` to
bring in `utop`, which is a nice wrapper that makes the REPL much more usable.
