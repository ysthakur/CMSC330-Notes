# Rust

- Stack
  - Lifetimes (fixed)
  - Fixed size
  - Know how much memory to allocate/deallocate
  - Allows automatic memory management

Rules of ownership:

- Each value has a variable that is its owner
- There can only be one owner at a time
- When the owner goes out of scope, the value is dropped
