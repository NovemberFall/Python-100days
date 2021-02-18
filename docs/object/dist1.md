## What is a dictionary?

```py
x = []      # empty list      

# error 
# x[0] = 'Hello'
# Traceback (innermost last):
#   File "<stdin>", line 1, in ?
# IndexError: list assignment index out of range
# 
x += [ "hello" ] 
x.insert (0, "world")  # Insert object before index 0
x[0] =  "hello"
x.__setitem__(1, "world")    # same as x[1] =  "world"
print (x)

# ['hello', 'world']




y = {}      # empty dictionary      
# 
# 
y[0] = 'Hello'
y[1] = 'Goodbye'
y.__setitem__(0,'Hello')    # same as y[0] = 'Hello'
y.__setitem__(1,'Goodbye')  # same as y[1] = 'Goodbye'
print (y)
# 
print(y[0])                 # Hello
print(y.__getitem__(0))            # Hello
# {0: 'Hello', 1: 'Goodbye'}
# Hello
# Hello


y[1] + ", Friend."
# 'Goodbye, Friend.'



y["two"] = 2
y["pi"] = 3.14
y["two"] * y["pi"]          # 6.28






# English-to-French color translator:
english_to_french = {}                      #A
english_to_french['red'] = 'rouge'          #B
english_to_french['blue'] = 'bleu'
english_to_french['green'] = 'vert'
print("red is", english_to_french['red'])   #C: red is rouge
# red is rouge
```

---

### Other dictionary operations

```py
english_to_french = {'red': 'rouge', 'blue': 'bleu', 'green': 'vert'} 
len(english_to_french)                # 3
# 
# 
for i in english_to_french.keys(): print(i)

for i,j in english_to_french.items(): print(i,j)

# list( english_to_french.items() )
print( english_to_french.keys() )







english_to_french = {'red': 'rouge', 'blue': 'bleu', 'green': 'vert'} 
len(english_to_french)                # 3
# 
# 
for i in english_to_french.keys(): print(i)

for i,j in english_to_french.items(): print(i,j)

# list( english_to_french.items() )
print( english_to_french.keys() )
# red
# blue
# green
# red rouge
# blue bleu
# green vert
# dict_keys(['red', 'blue', 'green'])












english_to_french = {'red': 'rouge', 'blue': 'bleu', 
'green': 'vert'} 
len(english_to_french)                # 3
# 
# 
list(english_to_french.keys())        
# ['red', 'blue', 'green']

list(english_to_french.values())      
#  ['rouge', 'bleu', 'vert']
# 
# 
list(english_to_french.items())       
# [('red', 'rouge'), ('blue', 'bleu'), ('green', 'vert')]



for i in english_to_french:
    print ( i, english_to_french[i])
# red rouge
# blue bleu
# green vert



for i in english_to_french.items():
    print ( i )
# ('red', 'rouge')
# ('blue', 'bleu')
# ('green', 'vert')



for i,j in english_to_french.items():
    print ( i,j )
# red rouge
# blue bleu
# green vert



del english_to_french['green']
list(english_to_french.items())       
#  [('blue', 'bleu'), ('red', 'rouge')]

'red' in english_to_french            # True
'orange' in english_to_french         # False






english_to_french = 
{'red': 'rouge', 'blue': 'bleu', 'green': 'vert'} 

a = english_to_french.get('blue', 'No translation') # bleu
b = english_to_french ['blue']
print (a,b)
# bleu bleu






a= english_to_french.get('chartreuse', 'No translation') # okay
b = english_to_french ['chartreuse']      # not okay

english_to_french.setdefault('chartreuse', 'No translation')
# okay










x = {0: 'zero', 1: 'one'}
y = x.copy()
y                                      # {0: 'zero', 1: 'one'}
z = {1: 'One', 2: 'Two', 3: 'Three'}
x = {0: 'zero', 1: 'one'}
x.update(z)
x                # {0: 'zero', 1: 'One', 2: 'Two', 3: 'Three'}
```