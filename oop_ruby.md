# An Intro to Object Oriented Programming (Ruby)

<img src="https://github.com/adion81/ruby_lectures/blob/master/img/ruby.png" alt="Ruby" width="350px">

### What is OOP?

Object Oriented Programming(OOP) is a programming paradigm that organizes data in objects.  These objects can have attributes and methods to define what they are and how they behave.

<details>
    <summary>Benefits of OOP</summary>
    <ul>
        <li>Easy to collaborate</li>
        <li>Scalabity of your application</li>
        <li>Makes your code efficient and resuable</li>
    </ul>
</details>

<details>
    <summary>The Four Pillars of OOP</summary>
    <ul>
        <li>Encapsulation</li>
        <li>Abstraction</li>
        <li>Polymorphism</li>
        <li>Inheritance</li>
    </ul>
</details>

## Creating Objects in OOP

### Classes
We can define objects creating blueprints of them that specify what attributes they have and their behaviours.<br>
<img src="https://github.com/adion81/ruby_lectures/blob/master/img/blueprint.png" alt="Blue Print" width="200px">
<br>
We do this through classes . . .<br>
<br>
*Let's say we want to create a card game.  We will need to first create a deck of cards, and more important, a card class*<br>
<br>

<img src="https://github.com/adion81/ruby_lectures/blob/master/img/ace.png" alt="Ace of Spades" width="200px">

card.rb

```ruby
    class Card
        # sets our instance variables into getters
        attr_reader :suit, :point_value, :string_value

        # This is a constructor function in ruby
        def initialize(suit, val)
            @suit = suit
            @point_value = val
            case val
            when 11
                @string_value = "Jack"
            when 12
                @string_value = "Queen"
            when 13
                @string_value = "King"
            when 1
                @string_value = "Ace"
            else
                @string_value = val.to_s()
            end
        end

        # Write methods to implement behaviour to the class
        def card_info
            puts "#{string_value} of #{suit}"
        end
    end
```

Above is how we would write a class or blueprint for the `card` object.<br>
<br>
Now we can create an instance of the card class

program.rb

```ruby
require "./models/card.rb"

# this is how we create an instance of an object
card  = Card.new("Spades", 1)

```

 ### Instance Varibles

 As mentioned above, we can give attributes to our classes.<br>
 <br>
 These attribues are things that an object can have, i.e. A dog can have a name, breed, and a color.<br>
 <br>
 With Ruby we add attributes to a class with `Instance Variables` and they can be defined similarly to regular local variables except they have an `@` in front of them.
<hr>

### Getters and Setters
Maybe you've heard of them before, but we use them to protect the data in our classes.<br>
<br>
More specifically we use them to grant access to read or overwrite them from outside the class, like on the instance of an object.<br>
<br>
card.rb

```ruby
class Card
    # allows you to read the instance variables from outside the class
    attr_reader :suit, :point_value, :string_value

    # allows you to write(assign) the instance variables from outside the class
    attr_writer :suit, :point_value, :string_value

    #allows you to read and write(assign) the instance variables from outside the class
    attr_accessor :suit, :point_value, :string_value
end
```
<hr>

### Methods

Methods allow us to give actions to our objects.<br>
<br>
We define methods in the class the same way we would define one normally<br>
<br>

card.rb

```ruby
class Card
    def show_card
        puts "The #{@string_value} of #{@suit} || Point Value: #{@point_value}"
    end
end
```
<hr>

### Inheritance

Inheritance is one of the most implemented pillars of OOP.

<details>
    <summary>What is the purpose of Inheritance?</summary>
    <p>Inheritance allows us to pass down attributes and methods of a class down to child classes.  Just like a parent will pass down genes and behaviours to their children.</p>
</details>

*We can use the card class to create a child or subclass version of it.  A more specific version of the card*<br>
<img src="https://github.com/adion81/ruby_lectures/blob/master/img/five_crowns.jpg" alt="Five Crowns" width="200px">

uno_card.rb

```ruby
class FiveCrownsCard < Card

    # We still need to call the constructor method because we want the child class to have a color attribute.
    def initialize(suit,val, color)
        super(suit,val)
        @color = color
    end

    # We can make a child version of the card info method here.
    def card_info

        # We print out the color of the UnoCard
        print "Color: #{@color} || "

        # Then we call 'super' to invoke the parent method witht the same name!
        super
    end

end
```