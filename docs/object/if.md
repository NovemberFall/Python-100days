## If Elif and Else Statements in Python

- control flow:
  - if
  - elif
  - else


---

```py
if True:
    print('Its True!')

#Its True!



In [3]:
hungry = True

if hungry:
    print('Feed Me!')
else:
    print("I'm not hungry")


#Feed Me!




In [6]:
location = 'Game'

if location == 'Auto Shop':
    print("Cars are cool!")
elif location == 'Bank':
    print("Money is cool!")
elif location == 'Store':
    print("Welcome to the store!")
else:
    print("I do not know much.")

# I do not know much.







name = 'Sammy'

if name == 'Frankie':
    print("Hello Frankie!")
elif name == 'Sammy':
    print("Hello Sammy")
else:
    print("What is your name?")

# Hello Sammy
```