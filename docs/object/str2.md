## Immutability


```py
    name = "Sam"
    name[0] = 'P'  # immutability
#     <ipython-input-2-81c23e8a7401> in <module>
# ----> 1 name[0] = 'P'  # immutability
# TypeError: 'str' object does not support item assignment

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
    
    x.split('i') # ['H', ' th', 's ', 's a str', 'ng']


```