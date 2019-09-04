<h1> Notes for basic Ruby</h1>

TL;RL:
- string = "string"
- hashes = {}
- arrays = [] <i>can contain many - objects </i>
- symbols = !symbol
- integers = 123
- floats = 123.456

<i>Try to always use single quotes '' cause it saves processing power, use doublequotes "" if there's a need like string interprolation or you wrap a string in somethingelse</i>


Ruby/ irb - use https://www.codecademy.com/courses/learn-ruby/lessons/loops-iterators/exercises/the-until-loop?action=resume_content_item to learn more ruby! 
Especially hashes and arrays. 

Ctlr + C to quit Irb! 
För att testa koden: ruby nameofprogram.rb 
Börja koda ruby genom att skriva irb i terminal.

<h2>DATATYPES;</h2> to know what class something is, type the objectname.class

- <b>String</b>= a class, object type, for letters/characters, anything inside “ “  or ‘ ‘ is a string. 
- <b>Floats</b> =  numbers (and decimal numbers)
- <b>Integer</b> = whole numbers (a Fixnum class)
- <b>Booleans </b>= yes and no, true or false types,  no quotations! 
- <b>Arrays</b> = list/collection of objects (can have strings, floats, integers, booleans etc within) 
	- Create by: Collection = Array.new or collection = [ ]  objects in arrays are indexed/numbered starting with 0 collection[0] . 
	- PUSH/<< (also called the shovel method) To add to an Array, use objectname.push [the new thing] . Or use objectname << newthing. 
	- POP to remove the last added variable from an Array use collection.pop . 
	my_array.first
	my_array.laster
	my_array[1]
	my_array.push('horse')
	To delete by it’s index use objectname.delete_at(indexnr exvis. 0)  
- <b>Hashes</b> are collection of key-value pairs. 
	- To create: 
	Person = {name: “pia”, age: 27, weight: 59.5} :name is the key and “pia” is the value. 
	my_hash = {}
	my_hash = Hash.new
	- Hash[:key] tells irb to look in the hash for the :key and display the info.
	my_hash[:another_key]
	- To return a key from a hash:
	```rb
	my_hash = {familykey: 'value', petskey: 'pets')
	my_hash.keys 
	#returns the following => [:family, :pets].
	``` 

To extract a hash from an array that contains a hash:
```rb
person1 = {name: 'Faraz'}  ((is a hash))
person2 = {name: 'Thomas'} ((is a hash))
people = [person1, person2]
people[0][:name]
```

<h3> String interprelation</h3>
First write your method.
Arguments are the raw material that you pass in to a method. 
Parameters are placeholernames for an argument.
```rb
def my_method(parameter)
puts "my name is: #{parameter}"
end
```

<b> .each do </b>
.each do is an itterator which repets what is inside what is called on(on the left of the .)
.to_i makes the string digit into an integer
```rb
numbers = [1, 2, 3, 4, 5]
numbers.each do [digit]
	digit.to_i
	puts digit + digit
end
```

<b> To check even or uneven</b>
```rb
if digit.even?
puts digit + 1
end
if digit.odd?
puts "uneven digit"
end
```

<b>To find methods</b>
numbers = [1, 2, 3, 4, 5]
puts numbers.methods shows the methods available for the created object

def random_method(name = 'pia')
puts name
end
#returns pia when called
random_method('Becca')
# returns Becca when called


To print the strings inside an array as a greetings messge 
```rb
names = ['Thomas', 'Kalle', 'Anders']
names.each do |name|
  puts "Hello #{name}"
end
```

<b> => also called a Hashrocket </b> 
This is no longer acceptable usage! But it separates the keys from the values in a hashmap literal. When used as the last parameter of a function the { } aren’t needed for that hash. f(:a => 1, :b => 2), f is called with one argument, which is a hashmap that has the keys :a and :b and the values 1 and 2.
```rb
# So instaed of 
my_hash = {key => 'value'}
#write
my_hash ? {key: 'value'}
```

```rb
x: “something” 
```
x => “something” means that the thing on the left has the same value as the thing on the right of the =>.      


<h4>From the 11/8 lecture about Ruby:</h4> which is an object-oriented programming language. 
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