# 3: Case by Case

Okay, so since copy-pasting into a REPL is no fun, I'm going to quickly flip
forward to the section "Loading a Program from a File":

>Save the file in same directory (folder) as you enter OCaml from, under the
>name `lists.ml`:
>
>```ocaml
># #use "lists.ml";;
>```
>
>We can then tell OCaml to use the contents of that file like this: It is
>exactly the same as typing it in manually \[...\] Errors and warnings will be
>reported as usual. Note that the #use command is not part of the OCaml language
>for expressions – it is just a command we are giving to OCaml.

One thing to add is that unlike in Haskell, we can't put our type signatures
in the same file. Apparently, there's a separate "interface file" with a `.mli`
extension, but I won't worry about that yet.

## Questions

[see `case.ml`](/03/case.ml)

### 4

Easier to read pattern matching, since doesn't require nested `if` statements.

### 5

Evaluates to `5`


