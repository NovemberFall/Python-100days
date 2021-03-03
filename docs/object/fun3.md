## 09.8 Decorators

```py
def decorate(f): # lambda
    def a(*args): return "<html>{}<html>".format( f(*args)) 
    # wrapper function
    return a

@decorate
def f(x):
    return x

print(f("hello"))     
#<html>hello<html>








def decorate(f):
    def a(*args):            # wrapper function
        x = f(*args)
        return "<html>{}<html>".format(x)
    return a

@decorate
def foo(parameter):
    return parameter

print(foo("Test"))     
#<html>Test<html>











def decorate(f):
    def a(*args):            # wrapper function
        def b(*args):       # inner_wrapper function
            x = f(*args)
            return "<html>{}<html>".format(x)
        return b(*args)
    return a

@decorate
def foo(parameter):
    return parameter

print(foo("Test"))     
#<html>Test<html>
```