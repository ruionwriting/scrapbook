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
- [The Many Uses Of Ruby Case Statements](https://www.rubyguides.com/2015/10/ruby-case/)

## ERB Templating

- [An Introduction to ERB Templating](https://www.stuartellis.name/articles/erb/)

## Commands Execution

- [5 ways to run commands from Ruby](https://mentalized.net/journal/2010/03/08/5-ways-to-run-commands-from-ruby/)

## Objects

- [Ruby Getters and Setters](https://dev.to/ksato1995/ruby-getters-and-setters-1p30)
- [How getter/setter methods work in Ruby](https://medium.com/@rondwalker22/how-getter-setter-methods-work-in-ruby-c5f5da07f99)

## defined keyword

- [How to Check If a Variable is Defined in Ruby](https://www.rubyguides.com/2018/10/defined-keyword/)
