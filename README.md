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
