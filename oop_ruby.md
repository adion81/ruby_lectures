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
**Let's say we want to create a card game.  We will need to first create a deck of cards, and more important, a card class**<br>
<br>
card.rb
```ruby
class Card
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
        else
            @string_value = val.to_s()
        end
    end

    # Write methods to implement behaviour to the class
end
```
