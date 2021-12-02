# BLOCKS

1, What are closures?

2, What is binding?

3, How does binding affect the scope of closures?

4, How do blocks work?

5, When do we use blocks? (List the two reasons)

6, Describe the two reasons we use blocks, use examples.

7, When can you pass a block to a method?

8, How do we make a block argument manditory?

9, How do methods access blocks passed in?

10, What is `yield` in Ruby?

11, How do we check if a block is passed into a method?

12, Why is it important to know that methods and blocks can return closures?

13, What are the benifits of explicit block?

14, Describe the arity differences of blocks, procs, methods and lambdas.

15, What are other differences are there between lambdas and procs? (might not be assessed on this, but good to know)

16, What does `&` do when in a the method parameter?

```ruby
def method(&var); end
```

17, What does `&` do when in a method invocation argument?

```ruby
method(&var)
```

18, What is happening in the code below?

```ruby
arr = [1, 2, 3, 4, 5]

p arr.map(&:to_s) # specifically `&:to_s`
```

19, How do we get the desired output without altering the method or the method invocations?

```ruby
def call_this
  yield(2)
end

# your code here

p call_this(&to_s) # => returns 2
p call_this(&to_i) # => returns "2"
```

20, How do we invoke an explicit block passed into a method using `&`? Provide example.

21, What concept does the following code demonstrate?

```ruby
def time_it
  time_before = Time.now
  yield
  time_after= Time.now
  puts "It took #{time_after - time_before} seconds."
end
```

22, What will be outputted from the method invocation on line 84? Why does/doesn't it raise an error?

```ruby
def block_method(animal)
  yield(animal)
end

block_method('turtle') do |turtle, seal|
  puts "This is a #{turtle} and a #{seal}."
end
```

23, What will be outputted if we add the follow code to the code above? Why?

```ruby
block_method('turtle') { puts "This is a #{animal}."}
```

24, What will the method call `call_me` output? Why?

```ruby
def call_me(some_code)
  some_code.call
end

name = "Robert"
chunk_of_code = Proc.new {puts "hi #{name}"}
name = "Griffin"

call_me(chunk_of_code)
```

25, What happens when we change the code as such:

```ruby
def call_me(some_code)
  some_code.call
end

chunk_of_code = Proc.new {puts "hi #{name}"}
name = "Griffin"

call_me(chunk_of_code)
```

26, What will the method call `call_me` output? Why?

```ruby
def call_me(some_code)
  some_code.call
end

def name
  "Joe"
end

name = "Robert"
chunk_of_code = Proc.new {puts "hi #{name}"}

call_me(chunk_of_code)
```

27, Why does the following raise an error?

```ruby
def a_method(pro)
  pro.call
end

a = 'friend'
a_method(&a)
```

# TESTING WITH MINITEST

28, What is a test suite?

29, What is a test?

30, What is an assertion?

31, What do testing framworks provide?

32, What are the differences of Minitest vs RSpec

33, What is Domain Specific Language (DSL)?

34, What is the difference of assertion vs refutation methods?

35, How does assert_equal compare its arguments?

36, What is the SEAT approach and what are its benefits?

37, When does setup and tear down happen when testing?

38, What is code coverage?

39, What is regression testing?

# CORE TOOLS

40, What are the purpose of core tools?

41, What are RubyGems and why are they useful?

42, What is Version Control and why are they useful?

43, What is Bundler and why are they useful?

44, What is Rake and why are they useful?

45, What constitues a Ruby project?
