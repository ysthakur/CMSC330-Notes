# Intro to OCaml

Features of functional languages:

- Immutable state
- Declarative programming
- Referential transparency

Tools:

- `utop` is fancy repl (default `ocaml` repl sucks)
- `dune` is for building, like make
  - `dune build <folder>` to build your code
  - `dune utop <folder>` will build your program and load it in `utop`
- `opam` is package manager

## OCaml syntax

```ocaml
(if expr:bool then expr:t else expr:t):t
let x = 3;; (* Define variable named x *)
let f x = x + 1;; (* Define function to increment int *)
(a:int + b:int):int
(a:float +. b:float):float
a:string ^ b:string (* Concatenate strings *)
(let var = e1:t1 in e2:t2): t2
```
