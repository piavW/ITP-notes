<h1>Notes from Rspec lecture.</h1>
Spec = Given some context - When it occurs - Then i shoudl see a specific output... or: executable example that test whether a portion of code exhibits the expected behavoir in a controlled context. 

Rspec is a testing framework for code written in Ruby, uses a DSL (domain specific language) and Ruby code. It has it's own and rubys helpermethods. 

- TDD - test driven development
- BDD - behaviour driven development

Stay in scope : stanna inom området/avgränsningen. 

Always test: Happy path, sad paths, edge cases(timeszones, languages etc), bug fixes. 
No need to test: already tested behaviour, basic ruby/javascript, basic frameworks: react/ruby on rails, third party APIs. 

```ruby
expect().to ()
expect().not_to ()
```

matchers are methods used to match someting with something else..?
```ruby
expect(acutal).to match(expected)
expect( ).to eq
expect( ).to match
expect( ).to be(true/false)
expect( ).to match_array
```

<b> Describe </b>
describe ClassName do
end
"#instance_method"
".class_method"

<b>it-block </b>  (telling it what I want it to do.) 
```ruby
it '..' do
end
```

- In your folder in terminal, write "touch Gemfile" to create the Gemfile, gems are bundles of codes that can be used in ruby. We store gems in the gemfile and then we pull the gems. "Code Gemfile. 
- Write: source 'http://rubygems.org' install the rspec gem by writing: gem 'rspec'
- In terminal, write: bundle  and it will install the gems. 
- To initialize rspec, in terminal write: "rspec --init". 
- In .rspec in VSC, write "--require spec_helper" and under that write "--format documentation" and "--color". 
- you run rspec by wirting "rspec" in terminal.

In terminal "touch spec/nameofthething_spec.rb" in this folder you write your test. This file then references what it needs to test with the code in the lib/car.rb file. 

write: require '.lib/car.rb' also in terminal create the mkdir lib and in lib touch car.rb It is withing the car.spec you write your code.
test your code everytime you've done something in one of the files by 'rspec'

```ruby
describe Car do
it 'needs to be a tesla' do
expect(subject.brand).to eq 'tesla'
end
end
```

within the lib/car.rb you need to create a car Class by: 
```ruby
class Car
attr_accessor :brand
def initialize 
@brand = 'tesla'
end
end
```

explanaition of the modulo % https://www.youtube.com/watch?v=b5cb_nfDyyM

About testing - always write in your name_spec.rb, test it, then write the actual code!!

100.times {|n| output << fizz_buzz(n+1)} 
#you know what this mean, Sverrir explained it :) 
