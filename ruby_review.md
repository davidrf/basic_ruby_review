#Basic Ruby Review

##Strings
String Interpolation
```
launcher_count = 44
"We have #{launcher_count} Launchers"
#=> "We have 44 Launchers"
```
 \#length
 ```
 "hello".length
 #=> 5
 ```
 \#split
 ```
 "split.this".split(".")
 #=> ["split", "this"]
 ```
 \#join
 ```
 ["join", "this"].join(".")
 #=> "join.this"
 ```
 #join is technically an array method, but I included here because it returns a string and is the reverse of #split
##Arrays

```
#Example Array
array = ["first", "second", "third", "fourth"]
```
n.b. each method assumes that you start out with this array at the beginning of each method and not the resulting array from the previous method
\#[]
```
array[1]
#=> "second"
```
\#index
```
array.index["third"]
#=> 2
```
\#include?
```
array.include?("fourth")
#=> true
array.include?("fifth")
#=> false
```
\#first
```
array.first
#=> "first"
```
\#last
```
array.last
#=> "fourth"
```
\#length
```
array.length
#=> 4
```
\#pop
```
array.pop
#=> "fourth"
array
#=> ["first", "second", "third"]
```
\#<<
```
array << "fifth"
#=> ["first", "second", "third", "fourth", "fifth"]
array
#=> ["first", "second", "third", "fourth", "fifth"]
```
\#shift
```
array.shift
#=> "first"
array
#=> ["second", "third", "fourth"]
```
\#unshift
```
array.unshift("zeroth")
#=> ["zeroth", "first", "second", "third", "fourth"]
array
#=> ["zeroth", "first", "second", "third", "fourth"]
```
\#insert
```
array.insert(1, "hi dad")
#=> ["first", "hi dad", "second", "third', "fourth"]
array
#=> ["first", "hi dad", "second", "third', "fourth"]
```
\#delete
```
array.delete("third")
#=> ["first", "second", "fourth"]
array
#=> ["first", "second", "fourth"]
```
##Hashes
```
#Example Hash
hash = { first_key: "first_value", second_key: "second_value", third_key: "third_value" }
```
n.b. each method assumes that you start out with this hash at the beginning of each method and not the resulting hash from the previous method

\#[]
```
hash[:second_key]
#=> "second_value"
```
\#[]=
```
hash[:fourth_key] = "fourth_value"
#=> "fourth_value"
hash
#=> { first_key: "first_value", second_key: "second_value", third_key: "third_value", fourth_key: "fourth_value" }
```
\#keys
```
hash.keys
#=> [:first_key, :second_key, :third_key]
```
\#values
```
hash.values
#=> ["first_value", "second_value", "third_value"]
```
##Enumerables
\#each
```
array.each do |element|
  puts element
end
#Outputs elements to terminal

hash.each do |key, value|
 puts "Key is: #{key} and value is: #{value}"
end

#Outputs key-value pairs for each element
```
\#map
```
array = [2, 5, 8]
array.map { |element| element + 2 }
#=> [3, 6, 9]
```
\#inject
```
array = [2, 5, 8]
array.inject(0) { |element, sum| element + sum }
#=> 15
```
\#sort
```
array = [7, 3, 9, 2]
array.sort
#=> [2, 3, 7, 9]
```
\#sort_by
```
array = ["a", "ccc", "bb", "dddd"]
array.sort_by { |element| element.length }
#=> ["a", "bb", "ccc", "dddd"]
```
## Flow Control
Example of if, elsif, and else statements
```
if conditional_1
  #do something if conditional 1 is true
elsif conditional_2 && conditional_3
  #do something if both condiditons 2 and 3 are true
elsif conditional_4 || conditional_5
  #do something if either conditional 4 or 5 is true
end
```
Everything except false and nil evaluates to true in Ruby
```
if false
  #code never gets run
elsif nil
  #code never gets run
elsif "" && 0
  #empty strings and 0 evaluate to true
end
```
Can check if the opposite is true with ! before conditional or using unless statement
```
if !false
  #code gets executed
end

unless false
  #code gets executed
end
```
Example of while loop
```
count = 0
while count < 5
 count += 1
end
count
#=> 5
```
Using until loop instead
```
count = 0
until count == 5
  count += 1
end
#=> 5
```
##Methods
Example method
```
def complex_equation(number)
  result = number + 1
  return result
end

complex_equation(3)
#=> 4
```
Ruby methods return the last evaluated line, so no need for explicit return in previous example
```
def complex_equation(number)
  result = number + 1
  result
end

complex_equation(3)
#=> 4
```
Also, it's worth noting that the puts method returns nil
```
def say_hi
  puts "Hello!"
end

say_hi
#Ouputs Hello! to the terminal
```
While this does output "Hello" to the terminal, the method itself returns nil.
Methods in general should return values, it would be better to do the following.
```
def say_hi
  "Hello!"
end

puts say_hi
#Ouputs Hello! to the terminal
```
Set default values to methods
```
def complex_equation(number = 1)
  number + 1
end

complex_equation(1)
#=> 2

complex_equation
#=> 1
```
