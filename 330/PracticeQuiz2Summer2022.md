# Practice Quiz 2 - Summer 2022

1.1. `fun a b -> string_of_int a = b`
1.2. `fun f a c -> f a`
2.1. `('a -> 'c -> 'd) -> ('a * 'a) list -> 'c list -> ('d * 'd) list`
2.2. `('a -> ('b -> 'd)) -> 'a -> 'b list -> 'd list`
3. `fold (fun (mi, ma) x -> (min mi x, max ma x)) (100, 1) lst`
4.

```ocaml
let sumtiply l1 l2 =
  let sum = fold (+) 0 l1 in
  map (fun x -> sum * x) l2
```
