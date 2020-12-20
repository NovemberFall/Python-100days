## Indexing and Slicing with Strings

### single quto ; double quto

```py
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
                     # a => c => e => g => i 

    mystring[::3]    # 'adgj'
                     # a => d => g = > j

    mystring[::-1]    # 'kjihgfedcba'

    mystring[2:7:2]  # 'ceg'
                     # from index 2 to 7, every time jump 2 steps 

```

