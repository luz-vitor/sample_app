# Ruby on Rails Tutorial sample application

This is the sample application for
[*Ruby on Rails Tutorial:
Learn Web Development with Rails*](https://www.railstutorial.org/)
(6th Edition)
by [Michael Hartl](https://www.michaelhartl.com/).

## License

All source code in the [Ruby on Rails Tutorial](https://www.railstutorial.org/)
is available jointly under the MIT License and the Beerware License. See
[LICENSE.md](LICENSE.md) for details.

## Getting started

To get started with the app, clone the repo and then install the needed gems:
```
$ bundle install --without production
```
Next, migrate the database:
```
$ rails db:migrate
```
Finally, run the test suite to verify that everything is working correctly:
```
$ rails test
```
If the test suite passes, you'll be ready to run the app in a local server:
```
$ rails server
```
For more information, see the
[*Ruby on Rails Tutorial* book](https://www.railstutorial.org/book).
----------------------------------------------------------------------------
Exercises Chapter 4

```js
4.2.1

1. 
>> city = "Rio Claro"
=> "Rio Claro"
>> state = "Sao Paulo"
=> "Sao Paulo"
2. >> puts "#{city}, #{state}"
Rio Claro, Sao Paulo
=> nil
3. >> puts "#{city},\t#{state}"
Rio Claro,      Sao Paulo
=> nil
4. >> puts '#{city},\t#{state}'
#{city},\t#{state}
=> nil
```

```js
4.2.2

1. 
>> "racecar".length
=> 7
2. 
>> "racecar".reverse
=> "racecar"
3.
>> s = "racecar"
=> "racecar"
>> s == s.reverse
=> true
4. 
>> puts "It's a palindrome!" if s == s.reverse
It's a palindrome!
=> nil
>> s = "onomatopoeia"
=> "onomatopoeia"
>> s == s.reverse
=> false
```

```js
4.2.3

1. 
?> def palindrome_tester(s)
?>   if s == s.reverse
?>     puts "It's a palindrome!"
?>   else puts "It's not a palindrome."
?>   end
>> end
=> :palindrome_tester
2. 
>> palindrome_tester("racecar")
It's a palindrome!
=> nil
>> palindrome_tester("onomatopoeia")
It's not a palindrome.
=> nil
3.
>> palindrome_tester("racecar").nil?
It's a palindrome!
=> true
```

```js
4.3.1

1. 
>> a = "A man, a plan, a canal, Panama".split(',')
=> ["A man", " a plan", " a canal", " Panama"]
2. 
>> s = a.join()
=> "A man a plan a canal Panama"
3. 
>> s = a.join("")
=> "A man a plan a canal Panama"
>> palindrome_tester(s)
It's not a palindrome.
>> s = s.split
=> ["a", "man", "a", "plan", "a", "canal", "panama"]
>> s = s.split.join(' ')
=> "a man a plan a canal panama"
>> s = s.split.join()
=> "amanaplanacanalpanama"
>> palindrome_tester(s)
It's a palindrome!
=> nil
4. 
>> vetor = ('a'..'z').to_a
=>
["a",
...
>> vetor[7]
=> "h"
>> vetor.reverse![7]
=> "s"
```

```js
4.3.2

1. 
>> (0..16).each {|elemento| puts elemento ** 2}
0
1
4
9
16
25
36
49
64
81
100
121
144
169
196
225
256
=> 0..16
2. 
?> def yeller(vet_char)
?>   vet_char.map(&:upcase).join
>> end
=> :yeller
>> yeller(['o','l','d'])
=> "OLD"
3.
?> def random_subdomain
?>   ('a'..'z').to_a.sample(8).join
>> end
=> :random_subdomain
>> random_subdomain
=> "opinyque"
>> random_subdomain
=> "joubhevm"
4.
?> def string_shuffle(s)
?>   s.split('').shuffle.join
>> end
=> :string_shuffle
>> string_shuffle("foobar")
=> "brofao"
>> string_shuffle("foobar")
=> "oarbof"
```

```js
4.3.3

1.
>> frase = {}
=> {}
>> frase = { :one => "uno", :two => "dos", :three => "tres"}
=> {:one=>"uno", :two=>"dos", :three=>"tres"}
?> frase.each do |key, value|
?>   puts "'#{key}' in Spanish is '#{value}'"
>> end
'one' in Spanish is 'uno'
'two' in Spanish is 'dos'
'three' in Spanish is 'tres'
=> {:one=>"uno", :two=>"dos", :three=>"tres"}
2.
=> {:one=>"uno", :two=>"dos", :three=>"tres"}
>> person1 = { :first => "Jose" , :last => "Silva" }
=> {:first=>"Jose", :last=>"Silva"}
>> person2 = { :first => "Maria" , :last => "Santos" }
=> {:first=>"Maria", :last=>"Santos"}
>> person3 = { :first => "Alice" , :last => "Carroll" }
=> {:first=>"Alice", :last=>"Carroll"}
>> params = { :father => person1, :mother => person2, :child => person3}
=>
{:father=>{:first=>"Jose", :last=>"Silva"},
...
>> params[:father][:first]
=> "Jose"
>> params[:mother][:first]
=> "Maria"
>> params[:child][:last]
=> "Carroll"
3.
>> hash = { :name => "Vitor Luz", :email => "luz_vitor@hotmail.com", 
								:password => ('a'..'z').to_a.sample(16).join}
=> {:name=>"Vitor Luz", :email=>"luz_vitor@hotmail.com", 
								:password=>"ocfuxyngmdkajzeh"}
>> hash = { :name => "Vitor Luz", :email => "luz_vitor@hotmail.com", 
								:password => ('a'..'z').to_a.sample(16).join}
=> {:name=>"Vitor Luz", :email=>"luz_vitor@hotmail.com", 
								:password=>"ofcpwjlqugxzaemv"}
4.
>> { "a" => 100, "b" => 200 }.merge({ "b" => 300 })
=> {"a"=>100, "b"=>300}
".merge return a 'new hash'. If the value for entries are duplicated, 
the 'new' keys value will be the value of the 'other_hash' keys".
```

```js
4.4.1

1.
