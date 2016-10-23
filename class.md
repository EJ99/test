# Classes

```ruby
class Order
  def initialize(name, price)   #a method that gets called when you use new - initialize will always get called when you do .new
    @name = name                #this is where you define the properties of the objects you will be making
    @price = price              #only this part is run when you do Order.new
  end

  def get_name                ## these are methods are functionalities, behaviours of the objects
    @name                     ## have to
  end

end

pie = Order.new()
puts pie.get_name

#dont put puts or gets in the methods just return simple values
# control flow shouldnt be used in the class - should be in the main file - class shouldnt be in the main file
# could have an array of animals in an object
# use hashes for the shlelter
# make an animal class

```

puts Order.new # this is making a new object of the class order
