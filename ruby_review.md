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

hash.each.do |key, value|
 puts "Key is: #{key} and value is: #{value}"
end

#Outputs key-value pairs for each element
```
\#map
```
array = [2, 5, 8]
array.map = { |element| element + 2 }
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
