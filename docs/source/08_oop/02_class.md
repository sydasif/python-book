# Classes and Objects

Everything in Python is an object, which means everything we create in Python has functions/methods or attributes or both attached to an object. This is because everything in Python comes from a class.

Class is a building block (blueprint) of the object. The class is created using the keyword `class`. A class is a code template for creating objects.

## Class Creation

For example, we want to create a blueprint for a car. A car has the following attributes (properties):

- Type of color
- Type of fuel

Cars also have some actions or functions. Those actions are called methods in a class. A method is just a function inside of a class.

- Type of car
- Capacity of car

The class is created using the keyword `class` as below:

```py
class Car:
    
    # defining constructor
    def __init__(self, color, fuel):
        self.color = color
        self.fuel = fuel
```

A class is a blueprint for how something should be defined. It doesn’t actually contain any data. All class definitions start with the `class` keyword, which is followed by the name of the class and a `colon`. Any code that is indented below the class definition is considered part of the class’s body.

```{Note}
Python class names are written in CapitalizedWords: `MyClass` or `My_Class`
```

## Object/instance

Class is a blueprint, an instance is an object that is built from a class and contains data. An instance of the `Car` class is not a blueprint anymore as below:

```py
# Create an object of the class
mike_car = Car("Red", "Petrol")
# Calling the objects
print(f"Color Type: {mike_car.color}")
print(f"Fule Type: {mike_car.fuel}")
```

```console
Color Type: Red
Fule Type: Petrol
```

## Instance Methods

Instance methods are functions that are defined inside a class and can only be called from an instance of that class, an instance method’s first parameter is always `self`.

```py
class Car:
    
    # defining constructor
    def __init__(self, color, fuel):
        self.color = color
        self.fuel = fuel

    # defining class methods 
    def type(self):
        description = f"Car has {self.color} color and fule type is {self.fuel}."
        return description 

# Create an object of the class
mike_car = Car("Red", "Petrol")
# Call methods of the objects
print(mike_car.type())
```

```console
Car has Red color and fule type is Petrol.
```

Add some more methods:

```py
class Car:
    
    def __init__(self, color, fuel):
        self.color = color
        self.fuel = fuel

    def owner(self, name):
        self.name = name
        return f"Car owner name is {self.name}"
    
    def type(self):
        description = f"and has {self.color} color, fule type is {self.fuel}"
        return description

    def capacity(self, num):
        self.num = num
        return f"and capacity is: {self.num}"

mike = Car("Red", "Petrol")
car_owner = mike.owner("'Mike'")
car_type = mike.type()
car_cap = mike.capacity(3)

car_description = f"{car_owner} {car_type} {car_cap}"
print(car_description)
```

```console
Car owner name is 'Mike' and has Red color, fule type is Petrol and capacity is: 3
```

The topic of `OOP` is huge, there is a lot more to Python objects and `OOP` and can't cover at all.
