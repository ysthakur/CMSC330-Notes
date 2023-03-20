# Higher order functions

## Data types

- Tuples can be heterogeneous

### Variants

- Type names can be lowercase, but constructor names have to be uppercase
- Use pattern matching to get fields

```ocaml
type coin = Heads | Tails
type color = Red of int | Green of int | Blue of int

let r : color = Red(255)
```

### Records

```ocaml
type color = { red : int; green : int; blue : int; }

let c1 : color = { red = 255; green = 0; blue = 255; }
c1.red (* 255 *)

match c1 with
  { red = x; green = 0 } -> x
| _ -> -1
```

## Anonymous functions

```ocaml
(fun arg1:'a arg2:'b ... -> e:tx): 'a -> 'b -> ... -> tx
```
