## 15.5.6 Inheritance

```py
# 15.5.6 Inheritance  
class Shape:
    """base (parent) (super) class for all geometric shapes"""
    def __init__(self, x, y):
         self.x = x
         self.y = y
    def move(self, delta_x, delta_y):  # instance method
         self.x = self.x + delta_x
         self.y = self.y + delta_y
     
    def __str__(self):
        return "({}, {})".format(self.x, self.y)


class Circle(Shape):                                     #C
    def __init__(self, r=1, x=0, y=0):
        super().__init__(x, y)                           #D
        self.radius = r

class Point(Circle):
    def __int__(self, x=0, y=0):
        super().__init__(0, x, y)
 
c = Circle(1)
c.move(3, 4)
c.x, c.y                          # 3, 4 
pt = Point(10, 100)
pt.move(300,300)
print(pt)
# (400, 300)
```

