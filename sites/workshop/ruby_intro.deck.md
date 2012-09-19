!SLIDE subsection
# Ruby Programming Intro

<img src="img/ruby-logo.jpg" width="250">

<!SLIDE bullets incremental>
# What we'll cover

* What is Ruby?
* Ruby's common objects
* Ruby syntax basics
* Object oriented programming concepts
* Passing code to a Ruby interpreter

!SLIDE

# Ruby vs. Rails

### Ruby is a Language
<img src="img/ruby-logo.jpg" height="125" width="125">

### Rails is a Framework
<img src="img/rails_logo.jpg" height="125" width="125">

### Rails is written in Ruby

!SLIDE
## Ruby vs. Rails

### Ruby is a language
<img src="img/ruby-logo.jpg" height="125" width="125">

### Gems are Ruby libraries
<img src="img/rubygems.png" height="125" width="125">

### Rails is a framework 
<img src="img/rails_logo.jpg" height="125" width="125">




<!SLIDE subsection incremental>
# Ruby Philosophy


```
I believe people want to express themselves when they program.
  
They don't want to fight with the language.

Programming languages must feel natural to programmers.

I tried to make people enjoy programming and concentrate on the fun and creative part of programming when they use Ruby.
```
 -- [Matz](http://linuxdevcenter.com/pub/a/linux/2001/11/29/ruby.html) (Yukihiro Matsumoto), Ruby creator
 
 
!SLIDE incremental
# Ruby Philosophy, Applied

* Ruby has a *humane interface*
  * many ways to do things
* Ruby favors readability and variety over concision and perfection
* sometimes makes code hard to understand (but usually makes it easier)
* contrast to *minimal interface*
  * one (or a few) "right" ways to do things
  * Python has a minimal philosophy
  
# Many Rubies

* Ruby 1.0 released in 1996
  * Fully Open Source
* Many implementations
  * MRI
    * REE
    * Kiji
  * JRuby
  * Rubinius
  * MagLev
  * MacRuby
  * IronRuby


# Versions common today

* MRI 1.8.7
* MRI 1.9.3
* JRuby


!SLIDE bullets
# Ruby is a scripting language

* Scripting languages:
  * Don't require a compiler.
  * Have an interpreter _(more on that later...)_
  * Run "on the fly"
  * Easy to change frequently

Python, Perl, and JavaScript are scripting languages too.

Java and C++ are examples of compiled languages.

# Ruby is object-oriented
* Everything is an object!
* Ruby is truly object-oriented.
* Everything is an object!
```
1.to_s
#=> "1"
```
    _(more on that later...)_



# Ruby Language Overview

* Dynamically typed
* Interpreted
* Can be modified at runtime
* Object oriented
* Blocks / lambdas / closures
* Perl-like regular expressions
* Closely tied to shell & OS

!SLIDE subsection

# Let's start coding!

!SLIDE bullets
# Open Your Terminal
You may also hear it called "command Line", "console", "shell", or "Bash"

* Windows: `git bash` ![](img/git_bash.png)

* Mac OS X & Ubuntu: `Terminal` ![](img/mac_terminal_sm.png)


!SLIDE
# Prompt

* Terminals show a line of text when you login & after a command finishes
* It's called the `prompt`, and customarily ends with a dollar sign

Whenever instructions start with `"$ "`, type the rest of the line into terminal.

Let's give the terminal a `command`, to open Interactive Ruby (IRB)

```bash
  $ irb
```


!SLIDE commandline
# irb: Interactive Ruby

IRB has its own prompt, which customarily ends with `>`

```
  $ irb
  >
```

You can use `Control-C` to exit IRB any time.
Or type `exit` on its own line.

```ruby
  > exit
  $ 
```

Now you're back to the terminal's prompt.

    Windows Users! Some people have experienced trouble with backspace, delete, and arrow keys working properly in irb - what a pain! If you run into this problem, use this command instead to launch irb.

    $ irb --noreadline
    
    
# IRB: Interactive RuBy

Type `irb` in the terminal to launch IRB

    @@@ ruby
    >> 4
    => 4
    >> 4+4
    => 8

Please fire up `irb` on your computer and try this out!





!SLIDE
## Number
### Integer
### Float

!SLIDE
## Number
### Integer
"Whole number" (no decimal)

```
  42
  101
  0
```

!SLIDE
## Number
### Float
"Real number" (decimal)

```
  4.99
  98.7
  6000.0
```




!SLIDE bullets
## String

A string is text. It must be wrapped in a matched pair of quotation marks.

```ruby
  $ irb
  > 'Single quotes work'
  => "Single quotes work"
  > "Double quotes work"
  => "Double quotes work"
  > "Start and end have to match'
  ">
```
  
What is happening on the last two lines?  How would you solve it?



# String interpolation

    @@@ ruby
    "boyz #{1 + 1} men"
    => "boyz 2 men"

* Any Ruby code can go inside the braces
* It gets evaluated and stuck inside the string



!SLIDE bullets
# Common types of information

* String
* Number
* Arrays
* Hashes


!SLIDE

## Variables
### A variable holds information.
* We give it a name so we can refer to it
* The info it holds can be changed

```
  $ irb
  > my_variable = 5
  => 5
  > another_variable = "hi"
  => "hi"
  > my_variable = 10
  => 10
```




!SLIDE
# Variables are declared implicitly

    @@@ ruby
    first_name = "Santa"
    last_name = "Claus"
    full_name = first_name + last_name
    #=> "SantaClaus"





!SLIDE !bullets
## Variable
### Variable Naming

* Starts with letter (will not work otherwise)
* Can have a number in it
* ```snake_case```
* Constants use ```Camel_Case```


!SLIDE bullets
# Common types of information

* String
* Number
* Arrays
* Hashes



!SLIDE
## Array
An array is a list.

Each array must be surrounded by `square braces` aka `square brackets`. A comma separates each `member`.

    @@@ Ruby
    > fruits = ["kiwi", "strawberry", "plum"]
    => ["kiwi", "strawberry", "plum"]

!SLIDE
## Array
### Indexing

Members are stored in order. Each can be accessed by its `index`. Ruby starts counting at _zero_.

    @@@ Ruby
    > fruits[0]
    => "kiwi"
    > fruits[1]
    => "strawberry"
    > fruits[2]
    => "plum"

!SLIDE
## Hash
In a `hash` we can refer to a member by a keyword instead of a number. Each member is a pair:

* *Key*: address of the hash member

* *Value*: variable contained by the member, and located by key name

A hash may also be known as a `dictionary`, `associative array`, or `map`.


!SLIDE
## Hash
### Hash Syntax

A hash is surrounded by `curly braces` aka `curly brackets`. A comma separates each member pair. A key uses `=>` (the `rocket`) to point to its value.

    @@@ Ruby
    > states = {"CA" => "California",
    "DE" => "Delaware"}
    => {"CA"=>"California", "DE"=>"Delaware"}



!SLIDE
## Hash
### Hash Indexing

Member pairs can be accessed by their key.  So each hash key has to be unique.

Values don't have to be unique.

    @@@ Ruby
    > states["CA"]
    => "California"




!SLIDE custom
# Literal Types

* Numbers
  * `42`
* Booleans
  * `true`
  * `false`
* Strings
  * `"apple"`
  * `'banana'`
* Symbols
  * `:apple`
* Arrays
  * `["apple", "banana"]`
* Hashes
  * `{:apple => 'red', :banana => 'yellow'}`
* Ranges
  * `(1..10)`

!SLIDE  
## Flow Control and Object-Oriented Programming

* Loops
* Conditionals
* Operators
* Functions
* Classes & Methods


!SLIDE
## Loop
### Does something repeatedly
#### Single-line syntax

We can put a single-line action into curly braces.

```
  >> fruits.each {|fruit| puts fruit}
  kiwi
  strawberry
  plum
  => ["kiwi", "strawberry", "plum"]
```


(`puts` means to print the result.  _More on that later._)




!SLIDE
## Loop
### Does something repeatedly
#### Multi-line syntax

Put a multi-line action between `do` and `end`

```
  > fruits.each do |fruit|
  ?> puts fruit
  > end
  kiwi
  strawberry
  plum
  => ["kiwi", "strawberry", "plum"]
```


!SLIDE
## Conditional

### Do something only if a condition is true

```
  > fruits.each do |fruit|
  ?> puts fruit if fruit == "plum"
  > end
  plum
  => ["kiwi", "strawberry", "plum"]
```

!SLIDE  
## Flow Control and Object-Oriented Programming

* Loops
* Conditionals
* Operators
* Functions
* Classes & Methods


!SLIDE
## Operators

### Do stuff with objects

```
  > my_variable + 2
  => 7
  > my_variable * 3
  => 15
```
```
  > my_fruits = fruits + ["lychee"]
  => ["kiwi", "strawberry", "plum", "lychee"]
  > my_fruits = my_fruits - ["plum"]
  => ["kiwi", "strawberry", "lychee"]
```

!SLIDE
## Comparison Operators

Return a boolean value.

A boolean is one of only two possible values: `true` or `false`.

```
  > 1 + 1 == 2
  => true
  > 1 + 1 == 0
  => false
```

( `==` means "is equal to". _More on that later_)

# Assignment vs. Comparison

* `x = 1` is Assignment!
    "put the value `1` in the variable `x`"
* `x == 2` is a Comparison!
    "`true` if `x` is `2`, otherwise `false`"



!SLIDE  
## Flow Control and Object-Oriented Programming

* Loops
* Conditionals
* Operators
* Functions
* Classes & Methods


# Functions

    @@@ ruby
    def add(a,b)
      a + b
    end

    add(2, 2)
    #=> 4

* Note: no 'return' required

# Classes and methods

    @@@ ruby
    class Calculator
      def add(a,b)
        a + b
      end
    end

* a *function* inside a *class* is called a *method*

!SLIDE  
## Flow Control and Object-Oriented Programming

* Loops
* Conditionals
* Operators
* Functions
* Classes & Methods


# More notes!


# Everything evaluates to something

    @@@ ruby
    >> 2 + 2
    => 4

    >> (2+2).zero?
    => false

    >> "foo" if false
    => nil

    >> puts "foo"
    foo
    => nil

# Hash mark comments, like perl

    @@@ ruby
    # is a comment
    2 + 2 # is a comment

# Optional semicolons, parens, and `return`

These are equivalent:

    @@@ ruby
    def inc x
      x + 1
    end
    
    def inc x
      x + 1;
    end

    def inc(x)
      return x + 1;
    end

    def inc(x); x + 1; end

# Line Break Gotcha

    @@@ ruby
    x = 1 + 2
    x #=> 3

    x = 1
      + 2
    x #=> 1

Solution: always put operators on top line

    x = 1 +
        2
    x #=> 3

# Use parens when you need them

    @@@ ruby
    >> "Hello".gsub 'H', 'h'
    => "hello"

    >> "Hello".gsub("H", "h").reverse
    => "olleh"



# bang and question methods

* method names can end with `!` or `?`
  * `!` means "watch out!"
  * `?` means "boolean"


# Classes are objects
* (Everything is an object!)
* Classes are objects, and class methods are really just methods on the class
object
* Code evaluated in the scope of a class definition acts on the class
object.

  
# Meta-programming
* Writing code on the fly
* Ruby provides really powerful tools for meta-programming  and introspection
* This is most of the magic of Rails!




