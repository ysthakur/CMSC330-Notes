# Practice Quiz 2 - Fall 2019

1.
  a. `int -> int`
  b. `'a list list`
  c. `(float -> float) -> float -> float -> float`
2.
  a. `fun a b -> float_of_int a +. b`
  b. `fun f a -> f 1 (int_of_float a)` (wrong)
3.

```ocaml
let check_matrix lst =
  -2 < (foldl (fun acc row ->
    let size = fold (fun s _ -> s + 1) 0 row in
    if acc = -1 || acc = size then size
    else -2
  ) -1 lst)
```
wrong, need `(-1)`
