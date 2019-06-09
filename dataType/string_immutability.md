# single quto ; double quto
```python
    "world"     # print: 'world'

    ' I'm going on a run'

    #   File "<ipython-input-9-47ed2ead564e>", line 1
    # ' I'm going on a run'
    #     ^
    # SyntaxError: invalid syntax

    "I'm going on a run"

    print('hello \n world')
    # hello 
    #  world

    len('hello')   # 5
    len('I am')    # 4

    mystring = "Hello World"
    mystring[0]     # H
    mystring[8]     # r
    mystring[-2]    # l
    mystring[-3]    # r
    mystring[-1]    # d

    mystring = 'abcdefghijk'
    mystring[2:]    # 'cdefghijk'
    mystring[:3]    # 'abc'
    
    mystring[3:6]    # 'def'
    mystring[1:3]    # 'bc'

    mystring[::2]    # 'acegik'
    mystring[::3]    # 'adgj'
    mystring[::-1]    # 'kjihgfedcba'
```

# Immutability
```python
    name = "Sam"
    name[0] = 'P'  # immutability
#     <ipython-input-2-81c23e8a7401> in <module>
# ----> 1 name[0] = 'P'  # immutability

    last_letters = name[1:] #  'am'
     'P' + last_letters  # 'pam'

    x = 'Hello World'
    x = x + " it is beautiful outside!"
    # 'Hello World it is beautiful outside!'

    letter = 'z'
    letter * 10
    # 'zzzzzzzzzz'

    '2' + '3'
    # '23'

    x = 'Hello World'
    x.upper()   # 'HELLO WORLD'
    x.lower()   # 'hello world'
    x.split()   # ['Hello', 'World']
    
    x = 'Hi this is a string' # 
    x.split()   # ['Hi', 'this', 'is', 'a', 'string']
    

```