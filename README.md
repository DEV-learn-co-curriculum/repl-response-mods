# Let's test some Repls!

Testing out whether we can introspect on `response` inside our repl validations.

%%%

### Code Challenge II: Mass Assignment

Define a class, School, that initializes with a name and a location. The class should also have `attr_accessor`s for name and location. The initialize method should use keyword arguments for those attributes. Then, instantiate a new instance of the School class using mass assignment. 

~~~ruby

class School
# your code here
end

school_attributes = {name: "The Flatiron School", location: "11 Broadway, NY, NY"}

#instantiate your instance of School here, using mass assignment with the above school_attributes

~~~solution

class School

  attr_accessor :name, :location
  
  def initialize(name:, location:)
    @name = name
    @location = location
  end
end

school_attributes = {name: "The Flatiron School", location: "11 Broadway, NY, NY"}

School.new(school_attributes)

~~~validation

assert_type(response, School)
assert_equal(response.name, "The Flatiron School")
assert_equal(response.location, "11 Broadway, NY, NY")

~~~

%%%

Now let's test Ruby repl `puts`.

%%%

### Ruby Repl Puts

Write a method that puts "ruby" 3 times

~~~ruby

def puts_ruby_three_times
  # code your solution here
end

# do not remove the line below
puts_ruby_three_times

~~~solution

def puts_ruby_three_times
  3.times do
    puts "ruby"
  end
end

puts_ruby_three_times

~~~validation

assert_output(response, "ruby\nruby\nruby\n")

~~~

%%%

Now let's test multiple validations.

%%%

### Ruby Repl Multiple Validations (`assert_output` and `assert_length`)

Write a method that returns 'ruby'

~~~ruby

def puts_ruby
  # code your solution here
end

# do not remove the line below
puts_ruby

~~~solution

def puts_ruby
  puts "ruby"
end

puts_ruby

~~~validation 

assert_output(response, "ruby\n")
assert_length(response, 5)

~~~

%%%

Now just a regular ol Ruby repl...

%%%

### Ruby Repl - Regular (no puts)

Write a method that reverses a string, and call it, passing "12345" as an argument.

~~~ruby

# Code your solution here

~~~solution

def reverse(string)
  string.reverse
end

reverse("12345")

~~~validation

assert_equal(response, "54321")

~~~

%%%

One more repl... Javascript this time.

%%%

### Javascript Repl

Directions: Write an array containing three strings, each saying "taylors gonna tay".

~~~javascript

// Code your solution here

~~~solution

["taylors gonna tay", "taylors gonna tay", "taylors gonna tay"]

~~~validation

assert.equal(response.length, 3);
expect(response).to.be.a("array");

~~~

%%%
