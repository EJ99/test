# Ruby

•	Most things in ruby are objects
•	OOP programming style

```ruby
print “Please enter your name: “
name = gets
puts “Hello #{name + lastname}! Age is #{5 + age)”
```

* puts will force a line break
* print will not

## Variables

```ruby
puts "if i add #{my_age}, #{my_height}, and #{my_weight} i get #{my_age + my_height + my_weight}."
```
if i add 35, 74, and 180 i get 289.

*	Use \n to push output onto the next line
*	Use \t to push a tab in the output
*	Use \s to create a space
*	Variable.upcase
*	Variable.downcase
*	Variable.reverse.downcase
*	If you use a method on a variable – generally the variable won’t change and you will just get a new return value
*	But if you do variable.upcase! with an exclamation mark you are changing that original variable for good
*	To find out the type of value in ruby - Variable.class

##If/Else/Unless

hungry = false

unless hungry
  puts "I'm writing Ruby programs!"
else
  puts "Time to eat!"
end


```ruby

print "What do you want to ask?"
user_input = gets.chomp
user_input.downcase!

if user_input.include? "s"
    user_input.gsub!(/s/, "th")
    puts "you thay it like thith #{user_input}"
elsif user_input == ""
    puts "you must say something!"
else
    print "There was no s to find!"
end


```

## Methods

* Methods are summoned using a .. If you have a string, "I love espresso", and take the .length
* "I love espresso".length # ==> 15
* If you add an ! to the end of a method it changes the variable permantly you don't need to assign into new variable
* Make sure to include the ! so that the user's string is modified in-place; otherwise, Ruby will create a copy of user_input and modify that instead.

##String Interpolation

* If you define a variable monkey that's equal to the string "Curious George", and then you have a string that says "I took #{monkey} to the zoo",
* Ruby will do something called string interpolation and replace the #{monkey} bit with the value of monkey—that is, it will print
* "I took Curious George to the zoo". We can do the same thing here! For example:

###Method chaining

```ruby
name = "elizabeth"
name.downcase.reverse.upcase

print "What's your first name?"
first_name = gets.chomp
first_name.capitalize!

#first_name variable will now be permantly changed to capitalized because of the !
puts "Your name is #{first_name}"

```

###gets

```ruby
variable_name = gets.chomp
```

* gets is the Ruby method that gets input from the user.
* When getting input, Ruby automatically adds a blank line (or newline) after each bit of input; chomp removes that extra line.
* (Your program will work fine without chomp, but you'll get extra blank lines everywhere.)


def method_name

end

* Don’t have to return something but they can
*	Have to call methods
*	Call methods by just writing the name
*	Pass an argument as below

def add(x, y)
	puts “adding #{x) and #{y}:”
	puts x + y
end

add(7, 2)
adding 7 and 2:
11

## Arrays

*	Check what’s in array
* Puts grocery_list.inspect
* To add something to an array:
* Grocery list << “carrots”
* Grocery_list.push(“potatoes”)
*	Grocery_list.unshift(“celery”)
* Grocery_list.unshift(“celery”)
* Grocery_list += [“pie”, “cake”]

Accessing items in the array
*	Fave item = Grocery_list[2]
*	Grocery_list.first
* Grocery_list.last
* Grocery_list.length
* Grocery_list.count(“eggs”) – counts how many times its in the array
* Grocery_list.include?(“water”) – looks to see if value exists in array

Adding items to the array
*	Grocery_list.insert(2, “oatmeal)

Removing items to the array
*	.shift and .pop
*	can put the value in variable and will be taken off main array
* Grocery_list.drop(2) – drops the last two items but does NOT change the original array

To make new array from array
*	New array = Grocery_list.slice(0,3)
*	But original array will remain the same

## Hashes
*	Hashes are like arrays but don’t use numbers as identifiers
* Instead the identifier can be number, symbols, or strings

Item = { “name” => “bread, “quantity” => 1}

* You can create a new hash by:
* Setting a variable equal to Hash.new creates a new, empty hash;
* it's the same as setting the variable equal to empty curly braces ({}).

```ruby

my_hash = Hash.new

```

* Add key value to the hash

```ruby
Item[:brand] = ‘baked’
Item[“brand”] = “baked”
Item.store(“calories”, 200)
```

* To get the value of a key

Item.fetch(“quantity”)  #returns 1

### Hash values
* Item.values will return all the values of the has in an array
*	Item.values_at(“brand”, “quantity”)
*	Item.invert – switches keys with values

### Hash merge
* Item.merge({‘calories’ => 100})
* Merges two hashes together

## Loops

* Some languages have the increment operators ++ and -- (which also add or subtract 1 from a value), but Ruby does not.
* You'll have to make do with += and -=!

```ruby
i = 0
loop do
  i += 1
  print "#{i}"
  break if i > 5
end

```


```ruby
def get_name   
  name = ""   
    loop do     
      print "Enter your name (minimum 2 characters, no numbers): "    
      name = gets.chomp     
    if name.length >= 2 && !name.index(/\d/)       
      break     
    else       
      puts "Name must be longer than 2 char, not contain numbers."     
    end   
  end   
  return name
end  
```

name = get_name()
puts "Hi #{name}."

### while loop

```ruby
While loop
answer = ""
while answer != "n"   
print "Do you want me to repeat this pointless loop again? (y/n) "   
answer = gets.chomp.downcase end
```

### until loop

```ruby
answer = ""
until answer == "no" do
  print "Do you want this loop to continue? (y/n) "
  answer = gets.chomp
end
```


```ruby
def print_hello(number_of_times)
  i = 0
  while i < number_of_times
    puts "hello"
    i += 1
  end
end

answer = 0
until answer >= 5
  print "How many times do you want to print 'hello'? Enter a number greater than 5 to exit) "
  answer = gets.chomp.to_i
  print_hello(answer)
end

```

###For Loop

* Sometimes you do know how many times you'll be looping, however, and when that's the case, you'll want to use a for loop.

```Ruby
for num in 1...10
  puts num
end
```
* puts every number from 1 - 9

* The reason Ruby counted to 9 and not 10 was because we used three dots in the range; this tells Ruby to exclude the final number in the count: for num in 1...10 means "go up to but don't include 10."
* If we use two dots, this tells Ruby to include the highest number in the range

###Next

```ruby
  i = 20
  loop do
  i -= 1
  next if i % 2 != 0
  print "#{i}"
  break if i <= 0
  end
```

### Each with Arrays - Use when need to iterate through every item in the array

Instead of using a while loop - we can use the each method to iterate over the individual items in the array:

The do...end is called a block. A block is a chunk of code you can pass into a Ruby method. What the each method does is to call your block once for each item in the array, and pass the item into the block as an argument. So the above block prints each item in the array on its own line.

```ruby
array = [0, 1, 2, 3, 4, 5]

array.each do |item|
  puts "The current array part is: #{item}"
end

###OR

array = [1,2,3,4,5]

array.each do |x|
  x += 10
  print "#{x}"
end

### PRINTS 11, 12, 13, 14, 15

```

### .times method

```ruby
10.times do
    print "chunky ham"
end
```


We can also manipulate items inside of an each block. NOTE: This will leave the original array unchanged.

```ruby
array = [0, 1, 2, 3, 4, 5]
array.each do |item|
  item = item + 2
  puts "The current item + 2 is #{item}."
end
```

### Each with 2D Arrays

* To print a list of items in 2D array

```ruby
s = [["ham", "swiss"], ["turkey", "cheddar"], ["roast beef", "gruyere"]]

s.each do |sub_array|
    sub_array.each do |item|
        puts item
    end
end


```

### Each with Hashes

We can work with each key and value using the each method, which takes two arguments. We separate arguments to blocks using a comma, just like method arguments:

```ruby
secret_identities = {
  "The Batman" => "Bruce Wayne",
  "Superman" => "Clark Kent",
  "Wonder Woman" => "Diana Prince",
  "Freakazoid" => "Dexter Douglas"
}

secret_identities.each do |f, r|
    puts "#{f}: #{r}"
end

```

```ruby
business = { "name" => "Treehouse", "location" => "Portland, OR" }

business.each do |key, value|
  puts "The hash key is #{key} and the value is #{value}."
end
```

The each method is aliased as each_pair. We can iterate over hash keys using the each_key method, which takes one argument:

```ruby
business.each_key do |key|
  puts "Key: #{key}"
end

```

The same thing applies to values using the each_value method, which also takes one argument:

```ruby
business.each_value do |value|
  puts "Value: #{value}"
end
```


## Classes
*	A class is a way to take a grouping of functions and data and place them inside a container so you can access them with the . (dot) operator.
*	Are like a blueprint
*	string = String.new
* When we call .new we are intialising a new instance of the string class (for example)
* the variable string becomes an object and now we can ask it questions about itself
*	so can do string.upcase
*	to see what methods we can run on it – string.methods.sort
*	ej = String.new(“ej”) passing a string argument

```ruby
  String.new => ""
	Array.new => []
	Hash.new => {}
```
