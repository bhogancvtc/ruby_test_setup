## Ruby Test Harness

A simple test setup for Ruby. 

* `lib` is where your code goes
* `test` is where your tests go
* `test\test_helper` is the file you `require` in all of your tests.
* `Rakefile` contains the `test` task

### Using

Add a test to `test` called `my_object_test.rb` like this:

```
require `test_helper`
class MyObjectTest < Test::Unit::TestCase
  def test_math_works
    assert_equal 5, MyObject.doesMath(2,3)
  end
end
```

Then add `lib/my_object.rb` with this:

```
class MyObject
  def does_math(first, second)
    first + second
  end
end
```

Then add this object to `test/test_helper.rb`

```
require `my_object`
```

Then run 

```
$ rake test
```

to see if it passes.
