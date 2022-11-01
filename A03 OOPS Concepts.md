# The Four Pillars of OOP

## 1 – Encapsulation

------

This is a programming style where implementation details are hidden. It reduces software development complexity greatly. With Encapsulation, only methods are exposed. The programmer does not have to worry about implementation details but is only concerned with the operations.



All the necessary data and methods are bind together and all the unnecessary details are hidden to the normal user. So Encapsulation is the process of binding data members and methods of a program together to do a specific job, without revealing unnecessary details.

Encapsulation can also be defined in two different ways:

1. Data hiding: Encapsulation is the process of hiding unwanted information, such as restricting access to any member of an object.
2. Data binding: Encapsulation is the process of binding the data members and the methods together as a whole, as a class.

------

[Encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)) is one of the strongest tools in your tool belt as a software engineer. Like we covered in the beginning of this tutorial, writing code that machines understand is easy. But writing code that humans can understand is very difficult.

Encapsulation is the practice of hiding information inside of a "[black box](https://en.wikipedia.org/wiki/Black_box)" so that other developers working with the code don't have to worry about it.

A basic example of encapsulation would be a function. The caller of a function doesn't need to worry too much about what happens inside – they just need to understand the inputs and outputs.

```python
pythonacceleration = calc_acceleration(initial_speed, final_speed, time)
```

In the example above, to use the `calc_acceleration` function, we don't really need to understand what goes on inside. That's the goal of encapsulation: it makes our lives easier as developers and helps us write cleaner code.

### Encapsulation in OOP

In the context of object-oriented programming, we can practice good encapsulation by using private and public members.

The idea is that if we want the users of our class to interact with something directly, we make it *public*. If they don't need to use a certain method or property, we make that *private* in order to keep the usage instructions for our class simple.

### Encapsulation in Python

In order to enforce encapsulation in Python, developers prefix properties and classes that they intend to be private with a double underscore.

```python
class Wall():
    def __init__(self, height):
        # this stops us from accessing the __height
        # property directly on an instance of a Wall
        self.__height = height

    def get_height(self):
        return self.__height
```

In the example above, we don't want users of the `Wall` class to be able to change its height. We make the `__height` property private and expose a public `get_height` method so that users can still read the height of a wall without being tempted to update it.

This will stop developers from being able to do something like:

```python
# front_wall is an instance of a Wall
front_wall.__height = 10 # this results in an error
```

### Encapsulation does NOT make systems more secure

Like we talked about earlier, encapsulation is the practice of hiding some code complexity inside a "[black box](https://en.wikipedia.org/wiki/Black_box)" so that other developers working with the code don't have to worry about it. Adding encapsulation to our programs through "public" and "private" members makes our code easier to work with. It makes it "cleaner".

To be clear, encapsulation doesn't make the code more secure in the [cryptographic](https://boot.dev/learn/learn-cryptography) or cyber-security sense of the word. That's a point I was personally confused about when I was first learning about private and public class members in school.

Encapsulation is a mechanism for making code easier to work with and less buggy. We stop *ourselves* from accessing private data because we've decided it doesn't make sense to be used outside from outside of the class.

## #2 – Abstraction



Abstraction is one of the key concepts of object-oriented programming. The goal of abstraction is to handle complexity by hiding unnecessary details.

------

Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the car speed or applying brakes will stop the car, but he does not know how on pressing the accelerator, the speed is actually increasing. He does not know about the inner mechanism of the car or the implementation of the accelerators, brakes etc. in the car. This is what abstraction is.

------



Abstraction and encapsulation typically go hand in hand, and if we aren't careful with our definitions, they can seem like the same thing.

### Abstraction vs encapsulation

While definitions are always changing, I like to think about abstraction and encapsulation in the following way.

- Abstraction is a technique that helps us identify what information and behavior should be encapsulated, and what should be exposed.



- Encapsulation is the technique for organizing the code to encapsulate what should be hidden, and make visible what is intended to be visible.

If you want a longer read on the topic, check out [this essay](https://web.archive.org/web/20210513154547/https://www.tonymarston.net/php-mysql/abstraction.txt).

### So are we *encapsulating* or *abstracting* our code when we make things private?

Both. We are almost always doing both. The process of using the double underscore is a form of encapsulation. The process of *deciding* which data *deserves* to be hidden behind the double underscore is abstraction.

Let's look at a concrete example.

```python
import random

my_random_number = random.randrange(5)
```

In this example we're using the `random` library to generate a random number. As it turns out, [generating random numbers](https://blog.boot.dev/cryptography/what-is-entropy-in-cryptography/) is a **really hard** problem.

The operating system actually uses the physical hardware state of the computer as an input to seed the randomness.

However, the developers of the `random` library have *abstracted* that complexity away and *encapsulated* a lot of that data and behavior so we don't need to worry about it. We just say "I want a random number less or equal to than 5" and the library takes care of it for us.

The decision to take a single number as input to the `randrange` function was a decision of abstraction. When writing production-level software, getting the abstractions right is crucial, because they are the hardest things to change later.

Think about the consequences of the `random` package maintainers changing the input parameters to the `randrange` function! It would break code all over the world.

### How OOP Developers Think

Methods can actually be private as well. In other words, we can encapsulate *behavior* as well as *data*.

### **Grouping data and behavior**

Classes in object-oriented programming are all about grouping data and behavior together in one place: an object.

Object oriented programmers tend to think about programming as a modeling problem. They think, "how can I write a `Human` class that simulates the data and behavior of a real human?"

We aren't focusing on [functional programming](https://boot.dev/learn/learn-functional-programming) in this course. But to provide some contrast, functional programmers tend to think of their code as inputs and outputs. "When a human performs an action, what are the inputs to that action, and how do the outputs affect my program state?"

### **Both paradigms are valuable**

While OOP isn't the only paradigm in programming, it's a tried and true one that is useful in a variety of circumstances.

In any event, if you personally have an understanding of multiple ways of thinking about code, you'll be a much better developer over all.

## #3 – Inheritance

------

The term “inheritance” means “receiving some quality or behavior from a parent to an offspring.” In object-oriented programming, inheritance is the mechanism by which an object or class (referred to as a child) is created using the definition of another object or class (referred to as a parent). Inheritance not only helps to keep the implementation simpler but also helps to facilitate code reuse.

------

We've made it to the Holy-grail of object-oriented programming: [inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)). Inheritance is really the defining trait of object oriented languages.

Languages without classes like [Go](https://boot.dev/learn/learn-golang)lang and [Rust](https://www.freecodecamp.org/news/rust-in-replit/) provide encapsulation and abstraction features. In fact, almost *every* language does. Inheritance, on the other hand, tends to be unique to class-based languages like [Python](https://boot.dev/learn/learn-python), [JavaScript](https://www.freecodecamp.org/news/learn-javascript-by-coding-7-games/), [Java](https://www.freecodecamp.org/news/the-java-handbook/), and Ruby.

### What is inheritance?

Inheritance allows one class (aka "the child class") to *inherit* the properties and methods of another class (aka "the parent class").

This powerful language feature helps us avoid writing a lot of the same code twice. It allows us to [DRY (don't repeat yourself)](https://blog.boot.dev/clean-code/dry-code/) up our code.

### Inheritance in Python – Syntax

In Python, one class can inherit from another using the following syntax:

```python
class Animal:
    # parent "Animal" class

class Cow(Animal):
    # child class "Cow" inherits "Animal"
```

In order to use the constructor of the parent class, we can use Python's built in `super()` method.

```python
class Animal:
    def __init__(self, num_legs):
        self.num_legs = num_legs

class Cow(Animal):
    def __init__(self):
        # call the parent constructor to
        # give the cow some legs
        super().__init__(4)
```

### When should I use inheritance?

Inheritance is a powerful tool, but it is a *really* bad idea to try to overuse it. You should only use inheritance when every instance of the child class can also be considered the same type as the parent class.

When a child class inherits from a parent, it inherits *everything*. If you only want to share *some* functionality, inheritance probably is not the best answer. In that case you would probably just want to share some functions, or maybe make a new parent class that both classes inherit from.

### All cats are animals but not all animals are cats

![LwZVCId](https://www.freecodecamp.org/news/content/images/2022/10/LwZVCId.png)

### Inheritance hierarchy

There is no limit to how deeply we can nest an inheritance tree. For example, a `Cat` can inherit from `Animal` which inherits from `LivingThing`.

That said, we should always be careful that each time we inherit from a base class that the child is a **strict** subset of the parent. You should never think to yourself "my child class needs a couple of the parent's methods, but not these other ones" and still decide to inherit from that parent.

### Multiple children

So far we've worked with linear class inheritance. In reality, inheritance structures often form trees, not lines. A class can have as many direct child classes as the programmer wants.

You'll often find in production software that it's more likely that an inheritance tree is wide than deep. In other words, instead of a deep tree like:

```
Organism -> Animal -> Mammal -> Feline -> Cat
```

You will more often see a wide tree:

```
Dragon -> Drake
       -> Wyvern
       -> Hydra
       -> Druk
```

### Why are **inheritance** trees often wide instead of deep?

Like we talked about earlier, in good software a child class is a strict subset of its parent class.

In a deep tree, that means the children need to be perfect members of all the parent class "types". That simply doesn't happen very often in the real world. It's much more likely that you'll have a base class that simply has many sibling classes that are slightly different variations of the base.

```
Vehicle -> Truck
        -> Car
        -> Boat
        -> Train
```

## #4 – Polymorphism

While inheritance is the most unique trait that object-oriented languages make claim to, polymorphism is probably the most powerful.



___

Polymorphism is the ability of a variable, function, or object to take on multiple forms. For example, in a programming language that supports inheritance, classes in the same hierarchical tree may have methods with the same name but *different* behaviors.



Polymorphism means existing in many forms. Variables, functions, and objects can exist in multiple forms in Java and Python. There are two types of polymorphism which are run time polymorphism and compile-time polymorphism. Run time can take a different form while the application is running and compile-time can take a different form during compilation.

An excellent example of Polymorphism in Object-oriented programing is a cursor behavior. A cursor may take different forms like an arrow, a line, cross, or other shapes depending on the behavior of the user or the program mode. With polymorphism, a method or subclass can define its behaviors and attributes while retaining some of the functionality of its parent class. This means you can have a class that displays date and time, and then you can create a method to inherit the class but should display a welcome message alongside the date and time. The goals of Polymorphism in Object-oriented programming is to enforce simplicity, making codes more extendable and easily maintaining applications.

Inheritance allows you to create class hierarchies, where a base class gives its behavior and attributes to a derived class. You are then free to modify or extend its functionality. Polymorphism ensures that the proper method will be executed based on the calling object’s type.

Program codes would run differently in a different operating system. The ability of program code exhibiting different behaviors across the operating system is known as polymorphism in OOP. You can create a class called “Move” and then four people create animals that would inherit the move class. But we don’t know the type of animals that they would create. So polymorphism would allow the animals to move but in different forms based on the physical features

A creates a Snail that inherits the move class, but the snail would crawl

B creates a Kangaroo that inherits the move class, but the Kangaroo would leap

C creates a Dog that inherits the move class, but the dogs would walk

D creates a Fish that inherits the move class, but the Fish would swim.



Polymorphism has ensured that these animals are all moving but in different forms. How the programs would behave would not be known until run time.

___

Let's look at a simple example:

```python
class Creature():
    def move(self):
        print("the creature moves")

class Dragon(Creature):
    def move(self):
        print("the dragon flies")

class Kraken(Creature):
    def move(self):
        print("the kraken swims")

for creature in [Creature(), Dragon(), Kraken()]:
    creature.move()
# prints:
# the creature moves
# the dragon flies
# the kraken swims
```

In this example the child classes, `Dragon` and `Kraken` are **overriding** the behavior of their parent class's `move()` method.

### Polymorphisms Roots

Take a look at the Greek roots of "polymorphism".

- "poly" means "many"
- "morph" means "to change" or "form"

Polymorphism in programming is the ability to present the same interface (function or method signatures) for many different underlying forms (data types).

A classic example is a `Shape` class that `Rectangle`, `Circle`, and `Triangle` can inherit from.

With polymorphism, each of these classes will have different underlying data. The circle needs a center and radius. The rectangle needs two co-ordinates for the top left and bottom right corners. The triangle needs coordinates for the corners.

By making each class responsible for its data **and** its code, you can achieve polymorphism.

In this example, each class would have its own `Draw()` method. This allows the code that uses the different shapes to be simple and easy, and more importantly, it can treat shapes as the **same** even though they are **different**. It hides the complexities of the difference behind a clean abstraction.

```python
shapes = [Circle(5, 10), Rectangle(1, 3, 5, 6)]
for shape in shapes:
    print(shape.Draw())
```

This is in contrast to the functional way of doing things where you would have had separate functions that have **different** function signatures, like `draw_rectangle(x1, y1, x2, y2)` and `draw_circle(center, radius)`.

### Wait, what is a "function signature"?

A function signature includes the name, inputs, and outputs of a function or method. For example, these two classes have the same method signatures.

```python
class Human:
    def hit_by_fire(self):
        self.health -= 5
        return self.health

class Archer:
    def hit_by_fire(self):
        self.health -= 10
        return self.health
```

Both methods have the same name, take `0` inputs, and return integers. If *any* of those things are different, they would have different function signatures.

Here is an example of different signatures.

```python
class Human:
    def hit_by_fire(self):
        self.health -= 5
        return self.health

class Archer:
    def hit_by_fire(self, dmg):
        self.health -= dmg
        return self.health
```

### When overriding methods, use the same function signature

If you change the function signature of a parent class when overriding a method, it could be a disaster.

The whole point of overriding a method is so that the caller of your code *doesn't have to worry* about what different things are going on inside the methods of different object types.

### Operator overloading

Another kind of built-in polymorphism in Python is the ability to override an operator in Python depending upon the operands used.

Arithmetic operators work for built-in types like integers and strings.

```python
print(3 + 4)
# prints "7"

print("three " + "four")
# prints "three four"
```

Custom classes, on the other hand, don't have any built-in support for those operators:

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y


p1 = Point(4, 5)
p2 = Point(2, 3)
p3 = p1 + p2
# TypeError: unsupported operand type(s) for +: 'Point' and 'Point'
```

However, we can add our own support! The `__add__` method is used by the Python interpreter when instances of a class are being added with the `+` operator.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, point):
        x = self.x + point.x
        y = self.y + point.y
        return Point(x, y)

p1 = Point(4, 5)
p2 = Point(2, 3)
p3 = p1 + p2
# p3 is (6, 8)
```

When you call `p1 + p2` under the hood the interpreter just calls `p1.__add__(p2)`.

Here's a list of how the operators translate into method names.

| OPERATION           | OPERATOR | METHOD           |
| :------------------ | :------- | :--------------- |
| Addition            | +        | **\_\_add\_\_**      |
| Subtraction         | -        | **\_\_sub\_\_**      |
| Multiplication      | *        | **\_\_mul\_\_**      |
| Power               | **       | **\_\_pow\_\_**      |
| Division            | /        | **\_\_truediv\_\_**  |
| Floor Division      | //       | **\_\_floordiv\_\_** |
| Remainder (modulo)  | %        | **\_\_mod\_\_**      |
| Bitwise Left Shift  | <<       | **\_\_lshift\_\_**   |
| Bitwise Right Shift | >>       | **\_\_rshift\_\_**  |
| Bitwise AND         | &        | **\_\_and\_\_**      |
| Bitwise OR          | \|       | **\_\_or\_\_**       |
| Bitwise XOR         | ^        | **\_\_xor\_\_**      |
| Bitwise NOT         | ~        | **\_\_invert\_\_**   |

### How to overload built-in methods

Last but not least, let's take a look at some of the built-in methods we can overload in Python. While there isn't a default behavior for the arithmetic operators like we just saw, there *is* a default behavior for **printing** a class.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y


p1 = Point(4, 5)
print(p1)
# prints "<Point object at 0xa0acf8>"
```

That's not super useful! Let's teach instances of our `Point` object to print themselves. The `__repr__` method (short for "represent") lets us do just that. It takes no inputs but returns a string that will be printed to the console when someone passes an instance of the class to Python's `print()` function.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __repr__(self):
        return f"({self.x},{self.y})"

p1 = Point(4, 5)
print(p1)
# prints "(4,5)"
```
