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
>> hash = { :name => "Vitor Luz", :email => "luz_vitor@hotmail.com", :password => ('a'..'z').to_a.sample(16).join}
=> {:name=>"Vitor Luz", :email=>"luz_vitor@hotmail.com", :password=>"ocfuxyngmdkajzeh"}
>> hash = { :name => "Vitor Luz", :email => "luz_vitor@hotmail.com", :password => ('a'..'z').to_a.sample(16).join}
=> {:name=>"Vitor Luz", :email=>"luz_vitor@hotmail.com", :password=>"ofcpwjlqugxzaemv"}
4.
>> { "a" => 100, "b" => 200 }.merge({ "b" => 300 })
=> {"a"=>100, "b"=>300}
".merge return a 'new hash'. If the value for entries are duplicated, the 'new' keys value will be the value of the 'other_hash' keys".
```

```js
4.4.1

1. 
>> (1..10)
=> 1..10
2.
>> Range.new(1,10)
=> 1..10
3.
>> (1..10) == Range.new(1,10)
=> true
```

```js
4.4.2

1.
>> Range.class
=> Class
>> Range.class.superclass
=> Module
>> Range.class.superclass.superclass
=> Object
>> Range.class.superclass.superclass.superclass
=> BasicObject
2.
?> class Word < String
?>   def palindrome?
?>     self == reverse
?>   end
>> end
=> :palindrome?
>> s = Word.new("level")
=> "level"
>> s.palindrome?
=> true
```

```js
4.4.3

1.
>> s = Word.new("racecar")
=> "racecar"
>> s.palindrome?
=> true
>> s = Word.new("onomatopoeia")
=> "onomatopoeia"
>> s.palindrome?
=> false
>> s = Word.new("Malayalam")
=> "Malayalam"
>> s.downcase!
=> "malayalam"
>> s.palindrome?
=> true
2.
?> class String
?>   def shuffle
?>     self.split('').shuffle.join
?>   end
>> end
=> :shuffle
>> "foobar".shuffle
=> "foarob"
3.
?> class String
?>   def shuffle
?>     split('').shuffle.join
?>   end
>> end
=> :shuffle
>> "foobar".shuffle
=> "oroafb"
```

```js
4.4.4

1.
>> user = User.new
=> #<User:0x0000024530f28998 id: nil, name: nil, email: nil, created_at: nil, updated_at: nil>
2.
>> user.class
=> User(id: integer, name: string, email: string, created_at: datetime, updated_at: datetime)
>> user.class.superclass
=> ApplicationRecord(abstract)
>> user.class.superclass.superclass
=> ActiveRecord::Base
>> user.class.superclass.superclass.superclass
=> Object
>> user.class.superclass.superclass.superclass.superclass
=> BasicObject
```

```js
4.4.5

1, 2 and 3.
class User
	attr_accessor :first_name, :last_name

	def initialize(attributes = {})
		@first_name = attributes[:first_name]
		@last_name = attributes[:last_name]
	end

	def full_name
		"#{@first_name} #{@last_name}"
	end

	def alphabetical_name
		"#{@last_name}, #{first_name}"
	end
end

>> require './example_user'
=> true
>> user = User.new(:first_name => "Vitor", :last_name => "Luz")
=> #<User:0x00000282070ce2f8 @first_name="Vitor", @last_name="Luz">
>> user.full_name
=> "Vitor Luz"
>> user.alphabetical_name
=> "Luz, Vitor"
>> user.full_name.split == user.alphabetical_name.split(', ').reverse
=> true
```

Exercises Chapter 6

``` js
6.1.2

1.
>> user.class
=> User(id: integer, name: string, email: string, created_at: datetime, updated_at: datetime)
>> user.class.superclass
=> ApplicationRecord(abstract)
>> user.class.superclass.superclass
=> ActiveRecord::Base
```

```js
6.1.3

1.
>> user.name.class
=> String
>> user.email.class
=> String
2.
>> user.created_at.class
=> ActiveSupport::TimeWithZone
>> user.updated_at.class
=> ActiveSupport::TimeWithZone
```

```js
6.1.4

1.
>> User.find_by(name: "A Nother")
  User Load (0.5ms)  SELECT "users".* FROM "users" WHERE "users"."name" = ? LIMIT ?  [["name", "A Nother"], ["LIMIT", 1]]
=>
#<User:0x00000162c538b408
 id: 2,
 name: "A Nother",
 email: "another@example.org",
 created_at: Thu, 24 Nov 2022 22:38:44.272569000 UTC +00:00,
 updated_at: Thu, 24 Nov 2022 22:38:44.272569000 UTC +00:00>

>> User.find_by_name ("Michael Hartl")
  User Load (0.3ms)  SELECT "users".* FROM "users" WHERE "users"."name" = ? LIMIT ?  [["name", "Michael Hartl"], ["LIMIT", 1]]
=>
#<User:0x00000162c34137d8
 id: 1,
 name: "Michael Hartl",
 email: "michael@example.com",
 created_at: Thu, 24 Nov 2022 22:32:17.850535000 UTC +00:00,
 updated_at: Thu, 24 Nov 2022 22:32:17.850535000 UTC +00:00>
2.
>> User.all.class
=> User::ActiveRecord_Relation
3.
>> User.all.length
  User Load (0.1ms)  SELECT "users".* FROM "users"
=> 2
```

```js
6.1.5

1.
>> user.name =  "Michael"
=> "Michael"
>> user.save
  TRANSACTION (0.1ms)  SAVEPOINT active_record_1
  User Update (0.2ms)  UPDATE "users" SET "name" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["name", "Michael"], ["updated_at", "2022-11-24 23:22:15.539769"], ["id", 1]]
  TRANSACTION (0.0ms)  RELEASE SAVEPOINT active_record_1
=> true
2.
>> user.update(email:"michael@example.org")
  TRANSACTION (0.1ms)  SAVEPOINT active_record_1
  User Update (0.2ms)  UPDATE "users" SET "email" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["email", "michael@example.org"], ["updated_at", "2022-11-24 23:24:10.776789"], ["id", 1]]
  TRANSACTION (0.0ms)  RELEASE SAVEPOINT active_record_1
=> true
3.
>> user.created_at = 1.year.ago
=> Wed, 24 Nov 2021 23:26:01.860268900 UTC +00:00
>> user.save
  TRANSACTION (0.1ms)  SAVEPOINT active_record_1
  User Update (0.2ms)  UPDATE "users" SET "created_at" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["created_at", "2021-11-24 23:26:01.860268"], ["updated_at", "2022-11-24 23:26:22.637686"], ["id", 1]]
  TRANSACTION (0.1ms)  RELEASE SAVEPOINT active_record_1
=> true
```

```js
6.2.1

1.
>> User.new(name: "Example User", email: "user@example.com").valid?
=> true
2.
>> User.new.valid?
=> true
```

```js
6.2.2

1.
>> u = User.new
=> #<User:0x0000029e1ac2d728 id: nil, name: nil, email: nil, created_at: nil, updated_at: nil>
>> u.valid?
=> false
>> u.errors.full_messages
=> ["Name can't be blank", "Email can't be blank"]
2.
>> u.errors.messages
=> {:name=>["can't be blank"], :email=>["can't be blank"]}
>> u.errors[:email]
=> ["can't be blank"]
```

```js
6.2.3

1.
>> user = User.new(name: "a" * 51, email: "a" * 244 + "@example.com")
  TRANSACTION (0.1ms)  begin transaction
=>
#<User:0x0000025a7cfc9a80
...
>> user.valid?
=> false
2.
>> user.errors.full_messages
=> ["Name is too long (maximum is 50 characters)", "Email is too long (maximum is 255 characters)"]
```

```js
6.3.2

1.
>> user = User.new(name: "michael", email:"michael@example.com")
  TRANSACTION (0.1ms)  begin transaction
=>
#<User:0x000002415f0ba458
...
>> user.valid?
  User Exists? (0.2ms)  SELECT 1 AS one FROM "users" WHERE "users"."email" = ? LIMIT ?  [["email", "michael@example.com"], ["LIMIT", 1]]
=> false
2.
>> user.errors.full_messages
=> ["Password can't be blank"]
```

```js
6.3.3

1.
>> user = User.new(name: "michael", email: "michael@example.com", password: "1234", password_confirmation: "1234")
  TRANSACTION (0.1ms)  begin transaction
=>
#<User:0x000001de05283450
...
>> user.valid?
  User Exists? (0.2ms)  SELECT 1 AS one FROM "users" WHERE "users"."email" = ? LIMIT ?  [["email", "michael@example.com"], ["LIMIT", 1]]
=> false
2.
>> user.errors.messages
=> {:password=>["is too short (minimum is 6 characters)"]}
```

```js
6.3.4

1.
>> user = User.find_by(email: "michael@example.com")
  User Load (0.4ms)  SELECT "users".* FROM "users" WHERE "users"."email" = ? LIMIT ?  [["email", "michael@example.com"], ["LIMIT", 1]]
=>
#<User:0x000001a668aaf310
...
>> user
=>
#<User:0x000001a668aaf310
 id: 1,
 name: "Michael Hartl",
 email: "michael@example.com",
 created_at: Fri, 25 Nov 2022 21:10:26.731218000 UTC +00:00,
 updated_at: Fri, 25 Nov 2022 21:10:26.731218000 UTC +00:00,
 password_digest: "[FILTERED]">
 2.
>> user.name
=> "Michael Hartl"
>> user.name = "Other Name"
=> "Other Name"
>> user.save
  TRANSACTION (0.1ms)  begin transaction
  User Exists? (0.3ms)  SELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?  [["email", "michael@example.com"], ["id", 1], ["LIMIT", 1]]
  TRANSACTION (0.0ms)  rollback transaction
=> false
>> user.errors.full_messages
=> ["Password can't be blank", "Password is too short (minimum is 6 characters)"]
3.
>> user.update_attribute(:name, "Vitor")
  TRANSACTION (0.1ms)  begin transaction
  User Update (1.4ms)  UPDATE "users" SET "name" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["name", "Vitor"], ["updated_at", "2022-11-25 21:25:27.743540"], ["id", 1]]
  TRANSACTION (114.0ms)  commit transaction
=> true
```