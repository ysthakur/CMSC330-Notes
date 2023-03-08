# Finite Machines

## Finite State Machines

- FSM
  - Finite memory
- Push-down automaton (PDA)
  - Infinite memory
  - Uses stack
  - Can do more than FSMs
- Turing machine
  - Infinite memory
  - Uses ticker tape
  - Can do more than PDAs

FSMs:

- States with an extra circle around them denote the target
- **Garbage state**: a state where you know you won't be going anywhere
  - Safe to leave out of your graph

Deterministic vs non-determinism:

- **NFA**s are non-deterministic finite automata
  - Hard to check acceptance
- **DFA**s are deterministic finite automata
  - Easy to check acceptance
  - Each of its transitions is uniquely determined by its source state and input symbol
  - Cannot do ε transitions, i.e. reading an input symbol is required for each state transition
- All DFAs are NFAs

## Regex

- ε (lowercase epsilon) - empty string
- R1R2 - concatenation
- n - some letter n in alphabet
- R1|R2 - branch
- R1* - repetition/Kleene closure

Any regular expression can be turned into a DFA (need to convert to NFA first)

For a finite state machine, need 5 things:

- Σ (uppercase sigma) - set of symbols (alphabet)
- Q - set of states
- s_0 - starting state
- F - set of final (accepting) states
- δ (lowercase sigma) - set of transitions

## Converting regex to NFA

[Slides](https://bakalian.cs.umd.edu/assets/slides/ndfa.html#/4/0/4)

- Single letter: Just the starting state and an acceptance state, and a transition
  from the first to the second if the letter is given as input
- Concatenation: Simply join the NFAs for the two subexpressions together
- Union: If the NFA for the left subexpression looked like `S_a -> ... -> F_a`
  and the NFA for the right subexpression looked like `S_b -> ... -> F_b`, then
  the NFA for their union will be: ![Union NFA](https://bakalian.cs.umd.edu/assets/slides/dist/assets/ndfa/f11.png)
- Kleene closure: If the NFA for some regex `x` looks like `S_a -> ... -> F_a`,
  then the NFA for `x*` will be ![Kleene NFA](https://bakalian.cs.umd.edu/assets/slides/dist/assets/ndfa/f13.png)

## Converting NFA to DFA

Need to combine states to represent possible NFA states.

Subset algorithm

- Requires two functions:
  - ε-closure: which states can I get to using only ε-transitions
    - Can always reach self
  - Move: which states can I get to using only one symbol transition
    - Could be none

Pseudocode:

```
NFA = (a, states, start,finals,transitions)
DFA = (a, states, start,finals,transitions)
visited = []
let DFA.start = e-closure(start), add to DFA.states 
while visited != DFA.states
  add an unvisited state, s, to visited
  for each char in a
    E = move(s)
    e = e-closure(E)
    if e not in DFA.states
      add e to DFA.states
    add (s,char,e) DFA.transitions
DFA.final = {r | s \in r and s \in NFA.final} 
```

## Converting DFA to regex

Idea: Remove states and replace with regex
- Each state has 3 parts: incoming, self, outgoing
- Regex added in that order
