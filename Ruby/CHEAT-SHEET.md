# Ruby Cheat-Sheet

## Arrays

### Intersection/Union/Difference

```ruby
x = [1, 1, 2, 4]
y = [1, 2, 2, 2]

# intersection
x & y            # => [1, 2]

# union
x | y            # => [1, 2, 4]

# difference
x - y            # => [4]
```

### Reject elements

```ruby
[1, 1, 2, 4].reject { |v| v == 1 } # => 1, 4
```
