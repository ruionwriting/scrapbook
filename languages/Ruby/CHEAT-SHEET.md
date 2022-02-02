# Ruby Cheat-Sheet

<!-- TOC depthFrom:2 -->

- [Testing](#testing)
  - [Minitest](#minitest)
- [Gems](#gems)
- [Arrays](#arrays)
  - [Intersection/Union/Difference](#intersectionuniondifference)
  - [Reject elements](#reject-elements)
- [Hashes](#hashes)
- [Case](#case)
- [yield](#yield)
- [ERB Templating](#erb-templating)
- [Commands Execution](#commands-execution)
- [Objects](#objects)
- [defined keyword](#defined-keyword)
- [Net::HTTP](#nethttp)
- [SemVer](#semver)
  - [Articles](#articles)
- [Strings](#strings)
- [Loops and Iterators](#loops-and-iterators)
  - [Articles](#articles-1)

<!-- /TOC -->

> Eric the Coder [My beloved Ruby Cheat Sheet](https://dev.to/ericchapman/my-beloved-ruby-cheat-sheet-208o) is a great starting point.

## Testing

### Minitest

- [devhints.io](https://devhints.io/minitest)
- [Minitest Cheat Sheet](https://www.rubypigeon.com/posts/minitest-cheat-sheet/)
- [The Minitest Style Guide](https://minitest.rubystyle.guide)

  Setup:

  ```ruby
  require 'minitest/autorun'

  # Classes act as groups of tests.
  class RandomTests < Minitest::Test

    # The `setup` method is run before every test.
    def setup
      @random = File.open('/dev/random')
    end

    # The `teardown` method is run after every test.
    def teardown
      @random.close
    end

    # Tests are methods that begin with "test_".
    def test_reading
      content = @random.read(5)
      assert_equal 5, content.length
    end

    # The `skip` method prevents a test from running.
    # Skipped tests do not count as failures.
    def test_skipping
      skip 'Fix this test later'
    end

  end
  ```

  Assertions:

  ```Ruby
  class AssertionsTest < Minitest::Test
    def test_assertions
      # The subjects (values being tested)
      singer = 'Michael Buble'
      calculation = 0.3 - 0.2 # = 0.09999999999999998

      # The most basic assertion
      assert singer.end_with?('e')

      # Equality/matching
      assert_equal 'Michael', singer.split.first # expected == actual
      assert_same singer, singer # expected.equal?(actual)
      assert_nil nil
      assert_match /Michael (Buble|Jackson)/, singer # regex =~ singer

      # Containers
      assert_empty "" # obj.empty?
      assert_includes singer, 'Bub' # singer.include?('Bub')

      # Numeric
      assert_in_delta 0.1, calculation    # float comparison (absolute error method)
      assert_in_epsilon 0.1, calculation  # float comparison (relative error method)
      assert_operator calculation, :<, 5  # calculation < 5

      # Types/messages
      assert_instance_of Float, calculation  # calculation.instance_of?(Float)
      assert_kind_of Numeric, calculation    # calculation.kind_of?(Numeric)
      assert_respond_to singer, :downcase    # singer.respond_to?(:downcase)

      # Generic
      assert_predicate calculation, :positive?   # calculation.positive?
      assert_send [singer, :start_with?, 'Mic']  # singer.start_with?('Mic')

      # Exceptions
      error = assert_raises(ZeroDivisionError) { 5 / 0 }
      assert_equal error.message, 'divided by 0'

      # Output
      assert_output("0.09999999999999998\n") { puts calculation }
      assert_silent { "nothing output to $stdout or $stderr" }

      # Refute (opposite of assert)
      refute singer.end_with?('Jackson')
      refute_empty singer
      refute_equal singer, 'Lady Gaga'
      refute_in_delta calculation, 3.14
      refute_in_epsilon calculation, 3.14
      refute_includes singer, 'z'
      refute_instance_of Numeric, calculation
      refute_kind_of Integer, calculation
      refute_match /Gaga/, singer
      refute_nil singer
      refute_operator calculation, :>, 3.14
      refute_predicate singer, :empty?
      refute_respond_to singer, :sing
      refute_same singer, 'Michael Buble'
    end
  end
  ```

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

## Hashes

- [Ruby Hashes Cheat Sheet](https://www.shortcutfoo.com/app/dojos/ruby-hashes/cheatsheet)

## Case

- [The Power of Ruby's Case Statement](http://blog.molawson.com/the-power-of-ruby-s-case-statement)
  > Features `procs` and `lambdas`.
- [The Many Uses Of Ruby Case Statements](https://www.rubyguides.com/2015/10/ruby-case/)

## yield

- [The yield Keyword in Ruby](https://medium.com/rubycademy/the-yield-keyword-603a850b8921)

## ERB Templating

- [An Introduction to ERB Templating](https://www.stuartellis.name/articles/erb/)

## Commands Execution

- [5 ways to run commands from Ruby](https://mentalized.net/journal/2010/03/08/5-ways-to-run-commands-from-ruby/)

## Objects

- [Ruby Getters and Setters](https://dev.to/ksato1995/ruby-getters-and-setters-1p30)
- [How getter/setter methods work in Ruby](https://medium.com/@rondwalker22/how-getter-setter-methods-work-in-ruby-c5f5da07f99)

## defined keyword

- [How to Check If a Variable is Defined in Ruby](https://www.rubyguides.com/2018/10/defined-keyword/)

## Net::HTTP

- [Net::HTTP by Example / Net::HTTP Cheat Sheet (Book Edition)](https://yukimotopress.github.io/http)

## SemVer

### Articles

- [How to compare semantic version strings in Ruby](https://medium.com/@edgar/how-to-compare-semantic-version-strings-in-ruby-95fbf067de32)

## Strings

- [Ruby Strings Cheat Sheet](https://www.shortcutfoo.com/app/dojos/ruby-strings/cheatsheet)

## Loops and Iterators

### Articles

- [Loops and Iterators](http://www.dev-hq.net/ruby/7--loops-and-iterators)
