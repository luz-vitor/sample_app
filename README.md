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
4.2.1
```js
1. >> city = "Rio Claro"
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
