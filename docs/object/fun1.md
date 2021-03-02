## Positional parameters

```py
def power(x, y):
     r = 1
     while y > 0:
         r = r * x
         y = y - 1
     return r
 
power(3, 3)
power(3, 4)
# 27
# 81





def power(x, y=2):
     r = 1
     while y > 0:
         r = r * x
         y = y - 1
     return r

# 
# 
power(3, 3)
# 27
power(3)
# 9
```

---

## Variable numbers of arguments

```py
def maximum(*numbers):
    print(type(numbers))
    return max (numbers) if len(numbers) else None

# 
x = maximum(3, 2, 8)                       # 8
y = maximum(1, 5, 9, -2, 2)                # 9
z = maximum ()
print (x,y,z)

# <class 'tuple'>
# <class 'tuple'>
# <class 'tuple'>
# 8 9 None







#qqq
def f2(*key ): # same as f2 (1,2,3)
    sum = 0
    for i in key:
        sum += i
    print (sum, type (key) )

f2(1,2,3)
# 6 <class 'tuple'>







x = [ [1,2],[3,4]  ]
y = [  list(i) for i in zip ( *x ) ]  
# unpacking x and is same as below
y = [  list(i) for i in zip ( [1,2],[3,4]  ) ]

print (x,y)
# [[1, 2], [3, 4]] [[1, 3], [2, 4]]






# 08.3.3 The for loop and tuple unpacking

somelist = [(1, 2), (3, 7), (9, 5)] # list of tuple
result = 0 
for t in somelist:
    result = result + (t[0] * t[1])
    print(result)
# 2
# 23
# 68  







def example_fun(x, y, **other):
    # **other same as {"foo":3,"bar":4}
    z = other.keys()
    z = list(z)
    print("x: {0}, y: {1}, keys in 'other': {2}"
    .format(x, y, z ))
    other_total = 0
    for k in other.keys():
        other_total += other[k]
    print("The total of values in 'other' is {0}"
    .format(other_total))

example_fun(2, y="1", foo=3, bar=4)
# x: 2, y: 1, keys in 'other': ['foo', 'bar']
# The total of values in 'other' is 7









#xxx programming exercises
def f1( *key, **other):
    """ key is a list
        other is a dictionary
    """
    sum = 0
    
    for i in key:  
        sum += i
        
    sum += other["x"]
    # xxx note that quotation marks are necessary
    print (sum)

f1( 5,4,3, x=2,y=1)         # 14
```

-----

## 09.3 Mutable objects as arguments

- What does += mean in Python?


- `a += b` is essentially the same as `a = a + b`, except that:
  - `+` always returns a newly allocated object, but `+=` 
    should (but doesn't have to) modify the object in-place 
    if it's mutable (e.g. list or dict, but int and str are 
    immutable).
  - In `a = a + b`, `a` is evaluated twice  








```py
# 09.3 9.3	Mutable objects as arguments
# 
def f(n, y, z):
    y.append(3)        # object pointed by y changes
    z = [4, 5, 6]  # object pointed by z does not change, then
                       # z now points to a new object [4,5,6]
    n = n + 1

x = 5                  # immutable
y = [1, 2]             # mutable,
z = [4, 5]             # mutable, 
f(x, y, z)
x, y, z                # (5, [1, 2, 3], [4, 5])
```

---

```py
def f(a, b, c,d):
    x = 3
    a = a + [x]   # a will point to new object [1,2,3]
                  # create a new object a
    b  += [x]  # will be point to any new object or same object
    c = c.append(x)  # the object pointed by c will change
                     # for here, no new object to be created
    d.__iadd__([x])  # override +=
    
a = [1, 2]   # list, mutable                 
b = [1, 2]             
c = [1, 2]            
d = b        # d and b point to the same object      

f(a,b,c,d)
a,b,c,d    # a = 
# ([1, 2], [1, 2, 3, 3], [1, 2, 3], [1, 2, 3, 3])








def f(n, list1, list2):
    # list1 += [3] 
    list1.__iadd__([3])    # object pointed by list1 change
    list2 = [4, 5, 6]      
    # object pointed by list2 does not change, then
    # list2 now points to a new object [4,5,6]
    n = n + 1

x = 5                  # immutable
y = [1, 2]             # mutable,
z = [4, 5]             # mutable, 
f(x, y, z)
x, y, z                
# (5, [1, 2, 3], [4, 5])



# explain:
                               
f(x, y, z)
def f(n, list1, list2):

                    z -> [4, 5]                     
                    |
                list2 -> [4, 5, 6]


so,  z is still point to [4, 5]
```

---

```py
def f(n, list1, list2):
    # list1 = list1 + [3]
    list1.__add__([3])    # object pointed by list1 change
    # add, create a new object
    list2 = [4, 5, 6]      
    # object pointed by list2 does not change, then
    # list2 now points to a new object [4,5,6]
    n = n + 1

x = 5                  # immutable
y = [1, 2]             # mutable,
z = [4, 5]             # mutable, 
f(x, y, z)
x, y, z                
# (5, [1, 2], [4, 5])
```

-----

```py
import operator
help( operator.__add__ )
# Help on built-in function add in module _operator:

# add(a, b, /)
#     Same as a + b.




x = 1 # x is immutable
print( id(x) )

x += 1 # since x is int, immutable
# whenever we want to change the content of X,
# we have to create a new object 
print( id(x) )

x = x + 1
print( id(x) )
# 4343478624
# 4343478656
# 4343478688







```




