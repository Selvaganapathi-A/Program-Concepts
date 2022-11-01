## Class



A class is a blueprint for the object.



These classes define what attributes an instance of this type will have, like color, but not the value of those attributes for a specific object.



(or)



It is a user-defined data type, which holds its own data members and member functions, which can be accessed and used by creating an instance of that class.



A ***class is a ‘data-type’*** and an ***object as a ‘variable’ of that type***. 

Any number of objects can be created after a class is created.



A simple Vehicle class Defined as Follows:



```python
class Vehicle:
    def __init__(self, vehicle_type, color, reg_number, owner):
        self.vehicle_type = vehicle_type
        self.color        = color
        self.reg_number   = reg_number
        self.owner        = owner
```



``self`` - The `self` variable is a reference to the object itself, so by using it you can read and update the properties of the object.

# Objects

An object refers to the instance of the `class`, which contains the instance of the members and behaviors defined in the class template. 



In the real world, an `object` is an actual entity to which a user interacts, whereas class is just the blueprint for that object. So the `objects` consume space and have some characteristic behavior



Each object contains code and data to manipulate the data. Objects can even interact without knowing the details of each other’s code or data. 



The entire set of code and data of an object can be made user-defined data type using the concept of the class. A class is a ‘data-type’ and an object as a ‘variable’ of that type. Any number of objects can be created after a class is created.

## Methods vs Functions

A `function` is a piece of code that is called by a name. You can pass it data to operate on via parameters and it can optionally return data. All data that is passed to a function is explicitly passed through parameters.



A `method` is a piece of code that is called by a name *that is associated with an object*. Methods and functions are similar but have two key differences.

1. A method is *implicitly* passed the object on which it was called. In other words, you won't see all the inputs in the parameter list
2. A method is able to operate on data that is contained within the class. In other words, you won't see all the outputs in the `return` statement.

## Constructors in Python

It's quite rare in the real-world to see a class that defines properties in the way we've been doing it so far.

```python
class Soldier:
    armor = 2
    num_weapons = 2
```

It's much more practical to use a [constructor](https://en.wikipedia.org/wiki/Constructor_(object-oriented_programming)). In Python, a constructor is made with the [__init__() method](https://docs.python.org/3/reference/datamodel.html#object.__init__), and it is automatically called when a new object is created. So, with a constructor the code would look like this.

```python
class Soldier:
    def __init__(self):
        self.armor = 2
        self.num_weapons = 2
```

However, because the constructor is a method, we can now make the starting armor and number of weapons configurable with some parameters.

```python
class Soldier:
    def __init__(self, armor, num_weapons):
        self.armor = armor
        self.num_weapons = num_weapons

soldier = Soldier(5, 10)
print(soldier.armor)
# prints "5"
print(soldier.num_weapons)
# prints "10"
```

## Class Variables vs Instance Variables

### Instance variables

Instance variables vary from object to object and are declared in the constructor.

```python
class Wall():
    def __init__(self):
        self.height = 10

south_wall = Wall()
south_wall.height = 20 # only updates this instance of a wall
print(south_wall.height)
# prints "20"

north_wall = Wall()
print(north_wall.height)
# prints "10"
```

### Class variables

Class variables remain the same between instances of the same class and are declared at the top-level of a class.

```python
class Wall():
    height = 10

south_wall = Wall()
print(south_wall.height)
# prints "10"

Wall.height = 20 # updates all instances of a Wall

print(south_wall.height)
# prints "20"
```

### **Class vs instance variables – which should I use?**

Generally speaking, *stay away from class variables*. Just like global variables, class variables are usually a bad idea because they make it hard to keep track of which parts of your program are making data updates.

However, it is important to understand how they work because you may see them out in the wild.