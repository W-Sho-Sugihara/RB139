BLOCKS

# What are closures?

# What is binding?

# How does binding affect the scope of closures?

# How do blocks work?

# When do we use blocks? (List the two reasons)

# Describe the two reasons we use blocks, use examples.

# When can you pass a block to a method?

# How do we make a block argument manditory?

# How do methods access blocks passed in?

# What is `yield` in Ruby?

# How do we check if a block is passed into a method?

# Why is it important to know that methods and blocks can return closures?

# What are the benifits of explicit block?

# Describe the arity differences of blocks, procs, methods and lambdas.

# What are other differences are there between lambdas and procs? (might not be assessed on this, but good to know)

# What does `&` do when in a the method parameter?

```ruby
def method(&var); end
```

# What does `&` do when in a method invocation argument?

```ruby
method(&var)
```

# What is happening in the code below?

```ruby
arr = [1, 2, 3, 4, 5]

p arr.map(&:to_s) # specifically `&:to_s`
```

# How do we get the desired output without altering the method or the method invocations?

```ruby
def call_this
  yield(2)
end

# your code here

p call_this(&to_s) # => returns 2
p call_this(&to_i) # => returns "2"
```

# How do we invoke an explicit block passed into a method using `&`? Provide example.

# What concept does the following code demonstrate?

```ruby
def time_it
  time_before = Time.now
  yield
  time_after= Time.now
  puts "It took #{time_after - time_before} seconds."
end
```

# What will be outputted from the method invocation on line 84? Why does/doesn't it raise an error?

```ruby
def block_method(animal)
  yield(animal)
end

block_method('turtle') do |turtle, seal|
  puts "This is a #{turtle} and a #{seal}."
end
```

# What will be outputted if we add the follow code to the code above? Why?

```ruby
block_method('turtle') { puts "This is a #{animal}."}
```

# What will the method call `call_me` output? Why?

```ruby
def call_me(some_code)
  some_code.call
end

name = "Robert"
chunk_of_code = Proc.new {puts "hi #{name}"}
name = "Griffin"

call_me(chunk_of_code)
```

# What happens when we change the code as such:

```ruby
def call_me(some_code)
  some_code.call
end

chunk_of_code = Proc.new {puts "hi #{name}"}
name = "Griffin"

call_me(chunk_of_code)
```

# What will the method call `call_me` output? Why?

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

# Why does the following raise an error?

```ruby
def a_method(pro)
  pro.call
end

a = 'friend'
a_method(&a)
```

TESTING WITH MINITEST

# What is a test suite?

# What is a test?

# What is an assertion?

# What do testing framworks provide?

# What are the differences of Minitest vs RSpec

# What is Domain Specific Language (DSL)?

# What is the difference of assertion vs refutation methods?

# How does assert_equal compare its arguments?

# What is the SEAT approach and what are its benefits?

# When does setup and tear down happen when testing?

# What is code coverage?

# What is regression testing?

CORE TOOLS

# What are the purpose of core tools?

# What are RubyGems and why are they useful?

# What is Version Control and why are they useful?

# What is Bundler and why are they useful?

# What is Rake and why are they useful?

# What constitues a Ruby project?
