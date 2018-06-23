## arithmetic operations
- "/" : integer division

## display:
- print: no new line
- puts: with new line

## show class
- "A string".class

## constant is stored in uppercase
- note that constant value can be changed

## comments:
- multiline comments: 
``` ruby
=begin
multiline comment
=end
```
## type conversion
- to_s: to string
- to_i: to int
- to_f: to float
- to_sym: to symbol


## conditional branch
- if elsif else end
- no curly braces
- comparsion operators:
  - "a <=> b" : 0 if equal, 1 if a greater, -1 if b is greater
    ``` ruby
    puts "5 <=> 10" + (5 <=> 10).to_s
    ``` 
    
  - unless: 
    ``` ruby
    unless age < 4
      puts "No School"
    else 
      puts "Go to School"
    end
    ```
  - case statement
    ``` ruby
    case greeting
    when "French", "french"
      puts "Bojour"
      exit
    when "Spanish", "spanish"
    puts "Hola"
      exit
    else "English" # else is used as default
      puts "Hello" 
    end
    ```
  - `puts "You're young" if age < 10`
  - `puts (age > 50) ? "Old" : "Young"`
  
## Loop
- loop
  ``` ruby
  loop do
    x += 1
    next unless (x % 2) == 0 # will skip odd number
    puts x
    
    break if x >= 10
  end
  ```
  
- while loop
  ``` ruby
  while y <= 10
    y += 1
    next unless (y % 2) == 0
    puts y
  end
  ```
  
- until loop
  ``` ruby
  until a >= 10
    a = 1
    next unless (x % 2) == 0
    puts a
  end
  ```
  
- for loops
  ``` ruby
  numbers = [1, 2, 3, 4, 5]
  for number in numbers
    puts "#{number}," # to show variable value inside " ", use "#{}"
  end
  
  groceries = ["bananas", " sweet potatoes"]
  groceries.each do |food|
    puts "Get Some #{food}"
  end
  
  (0..5).each do |i|
    puts "# #{i}"
  end
  ```

## functions
- def key word
  ```ruby
    def function_name(param1, param2)
      return param1.to_i + param2.to_i
  ```
- note that parameters are passed by value so the value of variable can't be changed


## exceptions
- deal with exceptions
  ``` ruby
  first_num = gets.to_i
  second_num = gets.to_i
  
  begin
    answer = first_num / second_num
    
  rescue 
    puts "You can't divide by zero"
    exit
  end
  ```
  
- raise
  ``` ruby
  def check_age(age)
    raise ArgumentError, "Enter Positive Number" unless age > 0
  end
  
  begin 
    check_age(-1)
  rescue ArgumentErro
    puts "That is an impossible age"
  end
  ```
  
## string functions

- operations inside a string
  ``` ruby
    puts "Add them #{4 + 5} \n \n" # double quotes will do interpolation
    puts 'Add them #{4 + 5} \n \n' # single quotes won't
  ```
  
- multiline string: use `<<EOM ... EOM`
  ``` ruby
  multiline_string = <<EOM
  This is a multiline string
  that contains interpolation
  like #{4 + 5} \n \n 
  EOM
  ```
  
- concatenation: use "+" or use interpolation

- some functions
  ``` ruby
  puts full_name.inculde?("justion")
  puts full_name.size # number of characters in string
  puts "Vowels: " + full_name.count("aeiou").to_s # number of appearances
  puts "Consonants: " + full_name.count("^aeiou").to_s
  puts full_name.start_with?("Banas")
  puts "Index: " + full_name.index("Banas").to_s # start position
  
  puts "a == a"
  "a".equal?("a")
  
  full_name.strip
  full_name.lstrip # remove left spaces
  full_name.rstrip # remove right spaces
  
  full_name.center(20, '.')
  full_name.rjust(20, '.')
  full_name.ljust(20, '.') # make the string occupy 20 characters (by adding blanks on left) and use '.' to fill blanks
  
  full_name.chop # chop the last letter
  full_name.chomp('as') # chop the letter specified
  
  full_name.delete("a") # delete all "a"'s 
  
  name_array = full_name.split(//) # split everywhere there's a new character
  name_array = full_name.split(/ /) # split by white spaces
  
  
  ```
  
## objects

- Create class
  ``` ruby
  class Animal
    def initialize # constructor
      puts "Createing a New Animal"
    end
    
    def set_name(new_name)
      @name = new_name # @name is a property
    end
    
    def name
      @name
    end
    
    def name=(new_name)
      if new_name.is_a?(Numeric)
        puts "Name can't be a number"
      else 
        @name = new_name
      end
    end
  end   
    
  ```

- Create instance
  ``` ruby 
  cat = Animal.new
  cat.set_name("Good")
  ```
  
- Example
  ``` ruby
  class Dog
    attr_accessor :name, :height, :weight
    
    def bark
      return "Generic Bark"
      
    end
  end
  
  rover = Dog.new
  rover.name = "Rover"
    
  ```
  
- Inheritance

  ``` ruby
  class GermanShepard < Dog # inheritance
    def bark # overwrite
      return "Loud Bark"
    end
  end
  
  max = GermanShepard.new
  max.name = "Max"
  
  printf "%s goes %s \n", max.name, max.bark()
  ```
  
## Module
- Moudles can't be initiated, i.e can't create instance of module. A class can inherit multiple modules, but can only inherit one class.
- Example
  ``` ruby
  # create module
  module Human
    attr_accessor :name, :height, :weight
    
    def run
      puts self.name + "runs"
    end
  end
  
  # create another module
  module Smart
    def act_smart
      return "Smart"
    end
    
  end
  
  
  # another file
  require_relative "human" # file name for Human module
  require_relative "smart"
  
  class Dog
    include Animal # include a module
  end
  
  class Scientist
    include Human
    prepend Smart # use prepend to avoid overwrite methods
    
    deft act_smart
     return "Another smart"
     
    end
  end
  
  einstein = Scientist.new
  einstein.name = "Albert"
  eistein.act_smart # will give smart cuz we use prepend Smart instead of include Smart
  
  ```



## Polymophism

- 

## Symbols

- Symbol is basically a string which can't be changed
- e.g. 
  ``` ruby
  puts :derk
  ```
  
## array

``` ruby
array_1 = Array.new
array_2 = Array.new(2)
array_3 = Array.new(3, "Good") # Good Good Good
array_4 = [1, "two", 3, 5.5]


puts array_4[2,2].join(",") # print starts from 2th item and print 2 in total, and join concatenate them with ","
puts array_4.value_at(0,1,3).join(", ")

array5.unshift(0) # add from begin of the array
array_4.shift() # remove the start element of the array
array4.push(100,200) # add end
array_4.pop

array_4.concat([1,2,3])
array.size()
array.include?(100)
array.count(100)
array.empty?
array.join(", ")
p array # print array
array.each do |value|
  puts value
end
```


## Hash

- key-value pairs
  ``` ruby 
  number_hash = {"PI" => 3.14, "Gold" => 0.618, "e" => 2.718}
  superheroes = Hash["Gho", "ksfs"]
  ```
