# More Regex

- `()` - closures
- After doing `=~`, matches are put in `$1`, `$2`, etc.
  - `$` is sigil for **global variables**
  - If you don't have enough captures, then `$2`/`$3`/whatever is the empty string
- Can also use `"foo".match(/regex/)`
  - Gives `MatchData` object that you can index into
