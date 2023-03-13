# Practice Exam 1 - Spring 2018

1. Basic stuff
    1. True/false
        a. False
        b. True
        c. True
        d. Emits a warning
        e. False
        f. True
        g. False
    2. Code: `fun y -> x + y + 10`, Environment: `x = 5`
2. Regex
    1. `[A-Za-z]{8,10}`
    2. `www.com`
    3. `3562`, `8392,6,3`
3. Ruby execution
    1. ERROR
    2. `nil\n3`
    3. ERROR
    4. `[2, 4, 6, 8]`
    5. `True\nTrue`
    6. `[5, hi, true]`
 4. Ruby programming
    1. `addEdge`
        ```ruby
        def addEdge(s)
          if s ~= /^start: ([A-Za-z]-[0-9]+) end: ([A-Za-z]-[0-9]+)$/
            if !@g.key? $1 then @g[$1] = [] end
            if !@g[s].contains? $2 then
              @g[s].append($2)
            end
          end
        end
        ```
    2. `inDegree`
        ```ruby
        def inDegree(node)
          n = 0
          @g.each { |k, v| if v = node then n += 1 end }
          n
        end
        ```
    3. `outDegree`
        ```ruby
        def outDegree(node)
          if @g.key? node then @g[node].length else 0 end
        end
        ```
5. OCaml Typing
    1. `int -> int option`
    2. `'a -> 'a -> 'a list`
    3. `'a list -> ('a * 'a) list`
    4. `fun x y -> if x then [y] else [x]`
    5. `fun (a, b) -> a + 1`
    6. Folding
        ```ocaml
        let f (l, n) x = (x :: l, x + n)
        ```
6. OCaml Execution
    1. ERROR
    2. 6
    3. `[1, 1, 2, 3]`
    4. 9
    5. `(-4, 1)`
    6. 3
7. OCaml Programming
  1. `let int_of_digits lst = fold (fun a x -> a * 10 + x) 0 lst`
  2. `sum_level`
      ```ocaml
      let rec sum_level t n = match t with
          IntLeaf -> 0
        | IntNode(v, l, r) ->
            if n = 0 then v
            else if n < 0 then 0
            else if n > 0 then sum_level l (n-1) + sum_level r (n-1)
      ```
