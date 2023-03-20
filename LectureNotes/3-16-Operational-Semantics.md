# Operational Semantics

- Denotational semantics: Describe meanings through mathematical constructs
- Axiomatic semantics: escribe meanings through promises
- Operational semantics: Describe meanings through how things execute
  - Helpful for making interpreters

OpSem ultimately creates a proof of correctness or properties

Syntax for this class:
- Value: v
- Expression: e
- Environment: A

Goal: create a definitional interpreter

An interpreter needs a rule of what an expression returns (`e => v`)
