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

## Creating objects in OOP

### Classes
We can define objects creating blueprints of them that specify what attributes they have and their behaviours.<br>
<hr>
We do this through classes . . .<br>
<br>
*Let's say we want to create a card game.  We will need to first create a deck of cards, and more important, a card class*<br>
<br>
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

### Getters and Setters
Maybe you've heard of them before, but we use them to protect the data in our classes.<br>
<br>
More specifically we use them to grant access to read or overwrite them from outside the class, like on the instance of an object.

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

### Methods

Methods allow us to give actions to our objects.<br>


### Inheritance