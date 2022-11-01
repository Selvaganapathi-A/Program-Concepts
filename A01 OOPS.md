# Object-oriented programming Structure



Object-oriented programming (OOP) is a computer programming model that organizes software design around data, or objects, rather than functions and logic. An object can be defined as a data field that has unique attributes and behavior.



The main concept of OOPs is to bind the data and the functions that work on that together as a single unit so that no other part of the code can access this data.



Object-oriented programming combines a group of data attributes with functions or methods into a unit called an "object."



Typically, OOP languages are class-based, which means that a class defines the data attributes and functions as a blueprint for creating objects, which are instances of the class.



Popular class-based OOP languages include Java, Python and C++.



Multiple independent objects may be instantiated—or represented—from the same class and interact with each other in complex ways.



​		A simple example would be a class representing a person.

```python
class Person:
    name = ''
    age = 0
    height = 0

    def sayName(self):
        print(self.name)

    def sayAge(self):
        print(self.age)

    def sayHeight(self):
        print(self.height)

```

​		The person class would contain attributes to represent information such as the person’s age, name, height, etc.

​		The class definition might also contain functions such as "sayMyName" which would simply print that person’s name to the screen.

```python

class Family:
    familyMembers = []
    def persons(self):
        return self.familyMembers
```

​		A family could be constructed by instantiating person objects from the class for each member of the family.

​		Each person object would contain different data attributes since each person is unique.



## Features of OOPS

Some features of object-oriented programming are:

- Programs are divided into objects
- Data Structures are designed to characterize objects.
- **Methods operating on the data** of an object are **tied together** in the data structure.
- Data is hidden, and external functions cannot access it.
- Objects communicate with each other through methods.
- New methods and data can be easily added whenever necessary.
- Follows the bottom-up approach in program design.
