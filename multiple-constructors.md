## Multiple Constructor

In Python, you can create a constructor only once using ```__init__```. If you want to add more constructors, 
you can use tag @classmethod which can be used like a constructor.

For example:

```python
class Circle:
    def __init__(self, radius: float):
        self.radius = radius
```

You can create constructor that use diameter by create a class method in the Circle class
```python
class Circle:
    def __init__(self, radius: float):
        self.radius = radius

    @classmethod
    def from_diameter(cls, diameter: float):
        return cls(diameter/2)
```

You can create circle object by radius or diameter

```python
circle1 = Circle(50.0)
circle2 = Circle.from_diameter(100.0)
print(f"Radius of circle1 : {circle1.radius}")
print(f"Radius of circle2 : {circle2.radius}")
```

Output 
```python
Radius of circle1 : 50.0
Radius of circle2 : 50.0
```