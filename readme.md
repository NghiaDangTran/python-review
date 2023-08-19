# Python OOP

```
class Dog:
    # Class attribute, auto create when call new class
    species = "Canis familiaris"

    # instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age
    #dunder methods a method that auto call
    def __str__(self):
        return "Nob"
encapsulation: private medthod or value  start with __
Abstraction: cannt create, blue print pourpose
from abc import ABC, abstractmethod

class Shape(ABC):
    
    @abstractmethod
    def area(self):
        pass
    
    @abstractmethod
    def perimeter(self):
        pass

class Parent:
    def __init__(self,num=""):
        self.value=num
    def greet(self,temp=""):
        self.gret="Nghia"
        if temp:
            print(temp)
        else:print("Hello from Parent")
    # private method
    def _priv(self):
        print(self.gret)
        print("this is private",self.value)
    # read only
    @property
    def trueprivate(self):
        print("true private")
        
inheritance parent method and data
class Child(Parent):
    def greet(self):
        Parent.greet(self,temp="None nitch")
        super().greet()  # Call the 'greet' method in the Parent class
        super()._priv()
        # super("nghia")
        print("Hello from Child")
c = Child()
c.greet()



# inhertited property cannot be set by orther
class Circle:
    def __init__(self, radius):
        self._radius = radius

    @property
    def radius(self):
        return self._radius

    @radius.setter
    def radius(self, value):
        if value < 0:
            raise ValueError("Radius cannot be negative")
        self._radius = value

    @property
    def area(self):
        return 3.141592653589793 * self._radius ** 2
    @staticmethod
    can be call like circle.test()
    def test(self):
        return none
# Usage:
c = Circle(5)
print(c.radius)  # Output: 5

c.radius = 7     # Sets the radius to 7
print(c.radius)  # Output: 7

print(c.area)    # Output: 153.93804002589985

# c.radius = -5   # Raises ValueError: Radius cannot be negative
```

## encapsolation: private thing
## polymoripishm: same name method but difference action
## Abstraction: cannt create that class but can inheretance it, blue print pourpose
## inheritance: inherit method and  value from parent class

# learn moer flask, django
