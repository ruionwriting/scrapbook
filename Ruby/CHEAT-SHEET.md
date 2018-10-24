# Ruby Cheat-Sheet

## Gems

Download only

```shell
gem fetch psych
gem fetch psych -v 3.0.2
gem fetch psych -v 3.0.2 --platform x64-mingw32
```

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

## Case

- [The Power of Ruby's Case Statement](http://blog.molawson.com/the-power-of-ruby-s-case-statement)
  > Features `procs` and `lambdas`.


## ERB Templating

- [An Introduction to ERB Templating](https://www.stuartellis.name/articles/erb/)
