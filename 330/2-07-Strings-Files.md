# Strings and Files

## Files

```ruby
f = File.open('file.txt')
line = f.gets
while line
  line = f.gets
end
f.close
```

## Strings

- `s.sub(/regex/, replacement)` - Replace first occurrence
- `s.gsub(/regex/, replacement)` - Replace all occurrences
- Class of regex is `Regexp`
- `"str" =~ /regex/` - Check if string includes regex (`/r/ =~ "s"` also works)
