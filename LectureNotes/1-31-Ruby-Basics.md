# OOP in Ruby

## Typing

- Manifest (explicit) typing: explicitly telling compiler the type of new variables
- Latent (implicit) typing: not needing to give a type to a variable
  - Ruby uses latent typing

- Can use `.methods` to get all methods on object
- Can use `.class` to get class of object
  - The class of a class is `Class`

## `nil`

- `nil` has class `NilClass`
- Has its own methods
  - `nil.to_s` gives `""`

- Ruby returns last evaluated line

## Methods

- Last line in method returned
- No method overloading

## Instance and static variables

- `@foo` is an instance variable (private by default)
- `@@foo` is a static/class variable

## Getters and setters

- Can make method called `foo=` to make setter for `foo`
- Can also add `attr_accessor :foo` at the top of the class to add getter and setter for `foo`

## Tuples

- Can return comma-separated list of values (`return 3, 4`)
- Can assign to comma-separated list of names (`a, b = foo`)
