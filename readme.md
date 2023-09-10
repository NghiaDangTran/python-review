# Python OOP
```
# Enter your code here. Read input from STDIN. Print output to STDOUT

class Queue():
    
    def __init__(self):
        self.contain=[]
    
    def enqueue(self,number):
        self.contain.append(number)
    
    def dequeue(self):
        self.contain.pop()
        
    def __str__(self):
        return self.contain[0]
        
if __name__ == '__main__':
    tests = int(input())
    
    for i in range(test):
        
        

        
        
        
    
```
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


Both class variables and instance variables are used within a class, but they serve different purposes and have different characteristics.

1. **Scope**:
    - **Class Variable**: Shared across all instances of the class. There's only one copy of the class variable, and when any object modifies it, the change is reflected in all other instances.
    - **Instance Variable**: Unique to each instance of the class. Every object has its own copy of the instance variable, and changes made to it will not affect other objects.

2. **Declaration**:
    - **Class Variable**: Declared within the class but outside any of the class's methods.
    - **Instance Variable**: Declared inside a method and prefixed with the `self` keyword.

3. **Usage**:
    - **Class Variable**: Accessed using the class name or an instance.
    - **Instance Variable**: Accessed using the instance of the class.

4. **Modification**:
    - **Class Variable**: Can be modified using the class name. If modified using an instance, it often results in the creation of an instance variable with the same name, shadowing the class variable.
    - **Instance Variable**: Can only be modified using the instance of the class.

5. **Use Cases**:
    - **Class Variable**: When you want a variable to be shared among all instances, for example, a counter to track the number of objects created.
    - **Instance Variable**: When you want each instance to have its own state, for example, attributes like name, age, etc.

Here's a simple illustration:

```python
class MyClass:
    class_var = 0  # Class variable

    def __init__(self, value):
        self.instance_var = value  # Instance variable

    def increment_class_var(self):
        MyClass.class_var += 1

    def increment_instance_var(self):
        self.instance_var += 1

# Create two instances
obj1 = MyClass(10)
obj2 = MyClass(20)

# Initial values
print(obj1.class_var, obj1.instance_var)  # 0 10
print(obj2.class_var, obj2.instance_var)  # 0 20

# Increment class variable using obj1
obj1.increment_class_var()
print(obj1.class_var, obj1.instance_var)  # 1 10
print(obj2.class_var, obj2.instance_var)  # 1 20

# Increment instance variable using obj2
obj2.increment_instance_var()
print(obj1.class_var, obj1.instance_var)  # 1 10
print(obj2.class_var, obj2.instance_var)  # 1 21
```

In the example above, `class_var` is a class variable shared across all instances of `MyClass`. `instance_var` is unique for each instance of the class.
