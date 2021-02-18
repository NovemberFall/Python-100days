## String

```py
# Chapter 06.1
x = "Hello"
x[0]           # 'H'
x[-1]          # 'o'
x[1:]          # 'ello'
x.__getitem__(0)  # same as x[0]
for i in x:  # same as for i in x.__iter__():
    print (i)
help (x.format)


# H
# e
# l
# l
# o
# Help on built-in function format:

# format(...) method of builtins.str instance
#     S.format(*args, **kwargs) -> str
    
#     Return a formatted version of S, using substitutions # from args and kwargs.
#     The substitutions are identified by braces ('{' and '}# ').








x = "Goodbye\n"
x = x[:-1]
x
# 'Goodbye'
# 
# 
len(x)  # 7
x.__len__()   # same as the len("x)
```

---