# BLOCKS

1, What are closures?

Closures allow us to create a 'chunk of code' that can be passed around to be called upon later on.

2, What is binding?

Binding is the relationship that closures share with their surrounding artifacts. Closures have access to variables, methods, constants, etc based on where they are defined regardless of when or where they are called upon later, we call this behavior and relationship, binding.

3, How does binding affect the scope of closures?

Binding allows closures to access variablse, methods, constants based on where the closure is defined and not when it is called upon. Therefore this allows closures and whatever is calling upon the closure to access or manipulate data on something that may be completely out of its scope normal scope, had there been no binding.

Example

```ruby
def some_method(pro)
  pro.call
end
name = 'Joe'
some_proc = proc { puts name}

some_method(some_proc)
```

This example shows us that a closure (the proc) is bound to the local var `name` and is able access it even if it is called upon within a method, where local variable are normally not accessable unless explicitly passed in as an argument upon method invocation.

4, How do blocks work?

Blocks are an unnamed chunk of code that are passed into methods. Blocks are defined by the `do..end` statements and `{}` curly brackets. The return value of blocks are determined by the last evaluated line on code within the block.

5, When do we use blocks? (List the two reasons)

- when we want to delegate the implementation of the method to the caller of the method.

- when we want to have a before and after (sandwich) code within our method.

6, Describe the two reasons we use blocks, use examples.

-We want to delegate the implementation of a method to the caller of the method when the implementor of the method does not know the desired outcome of the code. The method will accept a block that will define the desired outcome of the method.
Example:

```ruby
[1,2,3,4,5].map { |n| n.to_s }
```

In this example we can see that the `map` method will iterate through an array and return a new array but what goes into the new array is determined by the block passed in by the caller.

- We want to use a block when we have a method that requires a before and after implementation of something. The block will be implemented between the before and after and will return some desired value that is needed for the after.
  Example:

```ruby
def some_method(string)
puts string
new_string = yield(string)
puts "#{string} is now #{new_string}!"
end

```

7, When can you pass a block to a method? Why?

You can pass a block to a method upon invocation at any time. Methods have an implicit parameter that is not visible to us but will accept a block at any time. The method will need to be defined in a specific way to access that block, but even if a method is not defined to accept blocks, it will not raise an error when a block is passed in.

8, How do we make a block argument manditory?

We use the `&` and prepend it to a parameter variable within the parameters.
Example:

```ruby
def some_method(&block); end
```

9, How do methods access blocks passed in?
Methods use the keyword `yield` to invoke implicit blocks passed in and us the `Proc#call` method to invoke explicit blocks passed in.
Example:

```ruby
def some_method(&block)
block.call #explicit block invocation
yield # implicit block invocation
end
```

10, What is `yield` in Ruby?

`yield` in Ruby is a keyword used in a method definition that calls the implicit block passed into the method. `yield` can accept arguments and pass them into the block and assign them to the block local variable defined it its parameters.

11, How do we check if a block is passed into a method?

We can use the Kernel#block_given? method to see if an implicit block was passed into the method

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
