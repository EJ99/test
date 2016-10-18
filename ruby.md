# Ruby

•	Most things in ruby are objects
•	OOP programming style

```ruby
print “Please enter your name: “
name = gets
puts “Hello #{name + lastname}! Age is #{5 + age)”
```

•	Use \n to push output onto the next line
•	Use \t to push a tab in the output
•	Use \s to create a space
•	Variable.upcase
•	Variable.downcase
•	Variable.reverse.downcase
•	If you use a method on a variable – generally the variable won’t change and you will just get a new return value
•	But if you do variable.upcase! with an exclamation mark you are changing that original variable for good
•	To find out the type of value in ruby - Variable.class

## Methods

def method_name

end

•	Don’t have to return something but they can
•	Have to call methods
•	Call methods by just writing the name
•	Pass an argument as below

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

* Add key value to the hash

Item[:brand] = ‘baked’
Item[“brand”] = “baked”
Item.store(“calories”, 200)

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
answer = "" while answer != "n"   
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

### Each with Arrays

Instead of using a while loop - we can use the each method to iterate over the individual items in the array:

The do...end is called a block. A block is a chunk of code you can pass into a Ruby method. What the each method does is to call your block once for each item in the array, and pass the item into the block as an argument. So the above block prints each item in the array on its own line.

```ruby
array = [0, 1, 2, 3, 4, 5]

array.each do |item|
  puts "The current array part is: #{item}"
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

### Each with Hashes

```ruby
  business = { "name" => "Treehouse", "location" => "Portland, OR" }
```

We can work with each key and value using the each method, which takes two arguments. We separate arguments to blocks using a comma, just like method arguments:

```ruby
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
