## Lists

```py
print (dir ([]) )
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__',
 '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', 
 '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', 
 '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 
 'insert', 'pop', 'remove', 'reverse', 'sort']


help( [].copy )   # Return a shallow copy of the list.

Help on built-in function copy:

copy() method of builtins.list instance
    Return a shallow copy of the list.


a = [1,2,3]
b = a[:]  
# Omitting both indices makes a new list that goes from the beginning to the end of 
# the original list—that is, copies the list. 
# This technique is useful when you want to make a copy that you can modify without affecting the original list:
b

# [1, 2, 3]




b = a[0:len(a)]
b
# [1, 2, 3]



import copy
b = copy.copy(b)
print( b.__str__() )
print(str(b))

# [1, 2, 3]
# [1, 2, 3]




x = [1,2,3]
y = x.copy()           # a shallow copy of the list, same as y = x[:]
x *= 3                 # x = x*3
y.__imul__(3)          # overload *= 
y

# [1, 2, 3, 1, 2, 3, 1, 2, 3]





x = [1,2,3]
y = x*3               # y = x*3   
z = x.__mul__(3)      # overload *= 
y, y == z

# ([1, 2, 3, 1, 2, 3, 1, 2, 3], True)
```

---

## 05.1 Lists like arrays


```py
x = [2, "two", [1, 2, 3]]     # list is hetrogeneous
len(x)                        # same as x.__len__()
# 3


x.__len__()  # same as len(x)
# 3

print(len(x))
# 3



for i in x:
    print(i)
# 2
# two
# [1, 2, 3]




[1, 2, 3] in x  
x.__contains__([1,2,3])
# True
```


---


##  05.2 List indices

```py
x = ["first", "second", "third", "fourth"]
a = x[-1]
a                                          # 'fourth'

print( x.__getitem__(0) )
# first



```