---
title: "Notes (OFVB 09/31): More with Functions"
author: jcb
date: 2018-10-05
---


# Questions

## 1

This is just a description of currying, which I have written about in great
detail elsewhere (HPFP notes).

## 2

Type of member is ` 'a -> 'a list -> bool`

## 3

`((/) 2)` is the same as `(fun x -> 2 / x)`, we want `(fun x -> x / 2)`

## 4

It is possible to write a function which works like a map over arbitrary list
nesting. One way to do it is to write a function that first converts the list
into a tree, and then a write another function that maps over the leaves of the
tree.


