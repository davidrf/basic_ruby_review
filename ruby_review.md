#Basic Ruby Review

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
hash = { first_key: "first_value", second_key: "second_value", third_key: "third_value" }
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
```
array.each do 
