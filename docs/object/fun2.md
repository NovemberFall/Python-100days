## 09.4 Local, nonlocal, and global variables

```py
# 09.4 9.4	Local, nonlocal, and global variables
# 
# def fact(n):
#     """Return the factorial of the given number."""
#     r = 1
#     while n > 0:
#         r = r * n
#         n = n - 1
#     return r
# 
def fun():
     global a
     a = 1
     b = 2

# 
a = "one"
b = "two"
# 
fun()
print(a)                       # 1     (global)
b                       # 'two' (local)
# 1
# 'two'











# nonlocal.py

g_var = 0                    #A
nl_var = 0                  #A
print("top level-> g_var: {0} nl_var: {1}"
.format(g_var, nl_var))
def test():
    nl_var = 2              #B
    print("in test-> g_var: {0} nl_var: {1}"
    .format(g_var, nl_var))
    def inner_test():
        global g_var                             #C
        nonlocal nl_var                           #D
        g_var = 1
        nl_var = 4
        print("in inner_test-> g_var: {0} nl_var: {1}"
        .format(g_var,nl_var))
        
    inner_test()
    print("in test-> g_var: {0} nl_var: {1}"
    .format(g_var, nl_var))

test()
print("top level-> g_var: {0} nl_var: {1}"
.format(g_var, nl_var))

# 
# top level-> g_var: 0 nl_var: 0
# in test-> g_var: 0 nl_var: 2
# in inner_test-> g_var: 1 nl_var: 4
# in test-> g_var: 1 nl_var: 4
# top level-> g_var: 1 nl_var: 0
```

-----

## 09.6 lambda expressions

- lambda is a function without name

```py
# 
# 09.6 lambda expressions
# 
t2 = {  'FtoK': lambda f: 273.15 + (f - 32) * 5 / 9,    #1
        'CtoK': lambda c: 273.15 + c}                   #
t2['FtoK'(32)             # 273.15
# 
t2['CtoK'](100)
# 373.15






x=[ 1,-2,3,-4,5,-6 ]
x.sort(key=abs )
print (x)
type (abs)
# [1, -2, 3, -4, 5, -6]
# builtin_function_or_method







y=[ 1,-2,3,-4,5,-6 ]
y.sort(key=lambda y: y%2==0, reverse=True )
print (y)
# [-2, -4, -6, 1, 3, 5]

help (sorted)
# Help on built-in function sorted in module builtins:

# sorted(iterable, /, *, key=None, reverse=False)
#     Return a new list containing all items from the iterable 
#     in ascending order.
    
#     A custom key function can be supplied to customize the 
#     sort order, and the
#     reverse flag can be set to request the result in 
#     descending order.







y=[ 1,-2,3,-4,5,-6 ]
y.sort(key=lambda y: y if y >= 0 else -y)
print(y)
# [1, -2, 3, -4, 5, -6]
```