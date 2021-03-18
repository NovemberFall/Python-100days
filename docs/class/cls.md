## Classes and object-oriented programming

```py
# 15.1.1 Using a class instance as a structure or record 
# 
class Circle:
    def __init__(self):                    #1
        self.radius = 1
 
my_circle = Circle()
my_circle.radius = 5
print(2 * 3.14 * my_circle.radius)        
print(2 * 3.14 * my_circle.radius)        

print (type (my_circle))
print (type (1))
# 31.400000000000002
# 31.400000000000002
# <class '__main__.Circle'>
# <class 'int'>










# 15.3 Methods
# 
class Circle:
    """Define class Circle that has a radius"""
    pi = 3.14159   # class variable, belong to class
    
    def __init__(self, radius=1): 
        """self is explicit argument in Python, while "this" 
        in C/C++ is implicit"""
        self.__radius = radius  # local to the method

    #define getter and settter for each memeber
    @property
    def radius(self): return __radius
    
    def area(self):
        return self.radius * self.radius * 
        self.__class__.pi    # A
    def perimeter (self):
        return 2* self.__class__.radius * 
        Circle.pi             # B 
    def diameter (self):
        return 2*pi           # C

c = Circle(3) 
c.__radius = 3
```

---

## 15.9 Private variables and private methods

```py
class Mine:
    def __init__(self):
        self._s = 3                    # public variable
        self.x = 2                     # public variable
        self.__y__ = 3                 # public variable
        self.__z = 3                   # private variable
        self.__w = 3                   # private variable
        
    # define getter and setter
    @property   
    def z (self): return self.__z  # getter    
    def print_y(self):
         print(self.__y__)
    def print_z(self):
         print(self.__z)
            
m = Mine()
# 
print (m._s)                    # ok
print(m.x)                      # ok
print(m.__y__)                  # ok 
#print(m.__z)                  # error  
print(m._Mine__z == m.z)        
# ok, backdoor access to the private variable
print(id(m._Mine__z) == id(m.z))         
# ok, backdoor access to the private variable


print (dir(m))
['_Mine__w', '_Mine__z', '__class__', '__delattr__', 
'__dict__', '__dir__', '__doc__', '__eq__', '__format__', 
'__ge__', '__getattribute__', '__gt__', '__hash__', 
'__init__', '__init_subclass__', '__le__', '__lt__', 
'__module__', '__ne__', '__new__', '__reduce__', 
'__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', 
'__str__', '__subclasshook__', '__weakref__', '__y__', '_s', 
'print_y', 'print_z', 'x', 'z']
```

---

## 15.4 Class variables

```py
# 15.4 Class variables
# 
class Circle:
     pi = 3.14159                  # class variable
     def __init__(self, radius):   
        # self is reference to current object, likt "this" in 
        # C/C++
         self.radius = radius      # instance variable
     def area(self):  # instance method
         return self.radius * self.radius * Circle.pi
# 
Circle.pi               # 3.14159
Circle.pi = 4
Circle.pi               # 4
Circle.pi = 3.14159
Circle.pi               # 3.14159
# 
# 
c = Circle(3)
c.area()               # 28.27431


# Circle.pi
c = Circle(3)
c.radius   # instance variable
Circle.pi  # class variable
c.__class__ == Circle
# True
```

---

```py
class Circle:
     pi = 3.14159                  # class variable
     def __init__(self, radius):   
         self.radius = radius      # instance variable
            
     @classmethod
     def diameter(cls, c):
            """get the diameter of object C
            """
            return 2 * c.radius * cls.pi
        
     def area(self):  # instance method
         return self.radius * self.radius * Circle.pi
        
c = Circle(3)
Circle.diameter(c)      # class method
# 18.849539999999998
```


---

## 15.5.1 Static methods

- Python classes can also have methods that correspond 
  explicitly to static methods in a language such as Java. 
  In addition, Python has class methods, which are a bit more 
  advanced.


```py
# circle.py
"""circle module: contains the Circle class."""  
# documentation strings
class Circle:
    """Circle class"""
    all_circles = []                #A
    pi = 3.14159
    def __init__(self, r=1):
        """Create a Circle with the given radius"""
        self.radius = r
        self.__class__.all_circles.append(self) 
        # same as Circle.ll_circles.append(self)
        
    def area(self):
        """determine the area of the Circle"""
        return self.__class__.pi * self.radius * self.radius
    
    @classmethod
    def total_area(cls): 
        return sum( [c.area() for c in cls.all_circles] )
    
    @staticmethod
    def total_area(): 
        return sum( [c.area() for c in Circle.all_circles])  
```

- 15.5.1 Static methods

```py
import circle
c1 = circle.Circle(1)
c2 = circle.Circle(2)
circle.Circle.total_area()           # 15.70795

c2.radius = 3
circle.Circle.total_area()           # 31.415899999999997
```





---

## 15.10 Using @property for more flexible instance variables

- A property combines the ability to pass access to an 
  instance variable through methods like `getters` and 
  `setters` and the straightforward access to instance 
  variables through dot notation.

- To create a property, you use the property decorator with a 
  method that has the property’s name:
  - Without a setter, such a property is read-only.


```py
class Temperature:
    def __init__(self):
        self._temp_fahr = 0 
    @property
    def temp(self):
        return (self._temp_fahr - 32) * 5 / 9
```


- To change the property, you need to add a setter:

```py
    @temp.setter
    def temp(self, new_temp):
        self._temp_fahr = new_temp * 9 / 5 + 32
```

---

```py
class Temperature:
    def __init__(self):
        self._temp_fahr = 0 
        
    @property
    def temp(self):
        return (self._temp_fahr - 32) * 5 / 9
    
    @temp.setter
    def temp(self, new_temp):
        self._temp_fahr = new_temp * 9 / 5 + 32

        
        
t = Temperature()
t._temp_fahr
# 0
```

---

```py
# 15.10 Using @property for more flexible instance variables
class Temperature:
    def __init__(self):
        """store temperature in Fahrenheit, but get/set 
        temperature in Celsius"""
        self.__temp_fahr = 0 

    @property
    def celsius(self):
        return (self.__temp_fahr - 32) * 5 / 9

    @celsius.setter    
    def celsius(self, c):
        self.__temp_fahr = c * 9 / 5 + 32
 
t = Temperature()
x = t.celsius                     # -17.77777777777778
t.celsius = 0
y = t.celsius                     # 0.0
z = t._Temperature__temp_fahr     # 32.0
print (x,y,z)
# print (dir(t))
# -17.77777777777778 0.0 32.0
```




