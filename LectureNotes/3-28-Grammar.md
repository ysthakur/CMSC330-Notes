# More OpSem/Grammar

## Context-Free Grammars (CFGs)

- A CFG is like a regular expression in that it describes a language
- Only need Push-Down Automaton (PDA)
- However, they can also have recursion, so CFGs can do more than regex
  - e.g. balanced parentheses, palindromes
- CFGs can only do so much, **Context-Sensitive Grammars** are needed for more complex stuff
- Need the following 4 things for a CFG:
  - Alphabet (capital sigma) - a set of symbols allowed (**terminals**)
  - Non-terminals - groupings of terminals and nonterminals
  - Production - A definition of a non-terminal
  - Starting place

## Parsing

- Make lexer to generate tokens
- After lexer makes tokens, use parser to check if grammatically correct
  - Generates AST
- After parser, need evaluator to go from AST to value
