# h1
## h2
### h3

- one
- two

```ruby
$ code .
```

Ruby/ irb - use https://www.codecademy.com/courses/learn-ruby/lessons/loops-iterators/exercises/the-until-loop?action=resume_content_item to learn more ruby! 
Especially hashes and arrays. 

Ctlr + C to quit Irb! 
För att testa koden: ruby nameofprogram.rb 
Börja koda ruby genom att skriva irb i terminal.

DATATYPES; to know what class something is, type the objectname.class
- String = a class, object type, for letters/characters, anything inside “ “  or ‘ ‘ is a string. 
- Floats =  numbers (and decimal numbers)
- Integer = whole numbers (a Fixnum class)
- Booleans = yes and no, true or false types,  no quotations! 
- Arrays = list/collection of objects (can have strings, floats, integers, booleans etc within) 
	- Create by: Collection = Array.new or collection = [ ]  objects in arrays are indexed/numbered starting with 0 collection[0] . 
	- PUSH/<< To add to an Array, use objectname.push [the new thing] . Or use objectname << newthing. 
	- POP to remove the last added variable from an Array use collection.pop . 
- To delete by it’s index use objectname.delete_at(indexnr exvis. 0)  
- Hashes are collection of key-value pairs. 
	- Person = {name: “pia”, age: 27, weight: 59.5} :name I the key and “pia” is the value. 
	- Hash[:key] tells irb to look in the hash for the :key and display the info.

To display something: 
```Ruby
names = ['Thomas', 'Kalle', 'Anders']
names.each do |name|
  puts "Hello #{name}"
end
```

<b> => </b> also called a Hashrocket, separates the keys from the values in a hashmap literal. When used as the last parameter of a function the { } aren’t needed for that hash. f(:a => 1, :b => 2), f is called with one argument, which is a hashmap that has the keys :a and :b and the values 1 and 2.

x: “something” 
x => “something” means that the thing on the left has the same value as the thing on the right of the =>.      

From the 11/8 lecture about Ruby: which is an object-oriented programming language. 
A high-level code-language, high-level code-language is written for humans, slower than low-level but more creative and can write more code in fewer lines. 
Low-level code-language is closer to the computer, like when you give a machine commands, executes faster. 

Everything in Ruby is an object - every object belong (is an instance of) a class. Being a part of a class gives it methods/power/functions.

Exampels:
x.nil? Asks is there something in this? Answer will be true/false. 
x is_a? Nilclass/Fixnum/Integer etc asks about the 
x.methods shows the built in methods we can use for  that object. 

We can add our own methods to a class. 
Def nil.say_hi
‘Hello World’
End
Creates a method called say.hi. 

Inheritance - you can have a child/sub-class & a parent-class. The basic attributes are inherent from the parents. ¨

Super keyword - used to override a method that comes from a parent class to a subclass. 

Initialize - creates an instance of a class with their initial values. 

attr_accessor : color (kan se koden och ändra koden
attr_reader - Kan läsa koden
attr_writer - Kan ändra koden?
Nameofobject.color = ‘newcolor’ changes color.  

Code to create a new class and object. 
Class name
Def initialize 
@color = red
@doors = 5
End
end

my_car = name.new

.methodname används för att “tillkalla”/använda en metod. 
Man kan oxå använda flera metoder efter varandra/Chain methods.



%w (x y) är genväg för [“x”, “y”], listar det som skrivs in 

If … = ..
Puts “Correct”
End
 Är en vanlig if-statement

Unless … = …
Puts “sometimes”
End
	är motsatsen till if, såvida inte det som kommer efter unless är True, så kommer det stå “sometimes”. 

my_array = ["cat", "dog", "world"]
my_array.each do |item|
  puts "hello " + item
end
Då kommer det ut: Hello cat, ny rad, Hello dog, ny rad, Hello world.

Hashes är I curlybrakets { }
Array är i hardbrakets: [ ]

Att hämta från en hash som är i en array my_group[1][:age]  om du skapat hash = {name: “noel”, age: 34, gender: “male”}, och skapat hash2 = {name: “faraz”, age: 34, gender: “male”}, sen my:group [hash, hash2] och därefter skapar din array my_group = [hash, harsh2]. 

String interprelation = när du ser en hashtag med curlybrackets vilket är när går in i en hash och tar information/upprepar information från en hash eller hashens key till en string. 

.each do är en helper method som avslutas med end. Vi använder pipes | | 
my_group.each do |person|
Puts “#{person[:name]} is a #{person[:age]} year old #{person[:gender]}”  använder “” då vi hämtar från en string. 



Method:
Def hello(name)
	“Hello”+” “+ name +” “+”how are you?”
End 

Mellanrummet mellan “ “ skapar mellanslag. 
För att kalla på metoden skriver vi hello(“Pia”)


You can also use logical or boolean operators. Ruby has three: and (&&), or (||), and not (!). 
Ruby has the boolean operator not (!). !makes true values false, and vice-versa.
With && both comparisons on the left and right must evaluate to true for the entire statement to return true. If the left side does not return true it will not bother trying the right side
With || either the right or left side must evaluate to true. If the left side evaluates to true, the right side will not be tried because it has met the condition of one side being true.
With ! you reverse the result. If you’re false you’re now true. if you’re true you’re now false! Just think of it as opposite day!




to_s makes it into a string
to_i makes it into a integral etc

.chomp removes the new line



.product = returns an array of all combinations of elements from all arrays.
 
Arr = [15, 7, 18, 5, 8, 5, 1]
arr.index(5) visar att det finns tre stycken 5 i arr.
arr.index[5] visar error
arr[5] visar vad för information som finns på arr nummer 5





select {|key, value| block} → a_hash
select → an_enumerator
Returns a new hash consisting of entries for which the block returns true.
If no block is given, an enumerator is returned instead.
h = { "a" => 100, "b" => 200, "c" => 300 }
h.select {|k,v| k > "a"}  #=> {"b" => 200, "c" => 300}
h.select {|k,v| v < 200}  #=> {"a" => 100}
select! {| key, value | block } → hsh or nil
select! → an_enumerator
Equivalent to Hash#keep_if, but returns nil if no changes were made.

Så om jag ska hämta från family = { brothers: [“Svante”, “Gustav”], parents: [“Thomas”, “ulrika”], cousins: [“louise”, “carl”] }
Skriver jag brothers = family.select {|x| x[“brothers”]} och får då det som är inskrivet under brothers




If …. IF-STATEMENT USE ELSIF AND ELSE LAST. 
Puts ….
Elsif ..
Puts …
elsif …
puts…
Else ..
puts.. 
End. 