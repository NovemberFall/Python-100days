
## format() method


```py
   print('This is a string{}'.format(' INSERTED'))  # This is a string INSERTED 

   print('The {2} {1} {0}'.format('fox','brown','quick')) # The quick brown fox

   print('The {0} {0} {0}'.format('fox','brown','quick')) # The fox fox fox

   print('The {q} {b} {f}'.format(f = 'fox', b = 'brown', q='quick'))  # The quick brown fox

   print('The {f} {f} {f}'.format(f = 'fox', b = 'brown', q='quick'))   # The fox fox fox
```

---

## Float formatting follows "{value:width.precision f}"

```py
   result = 100/777     # 0.1287001287001287

   print("The resulat was {r} ".format(r=result))    # The resulat was 0.1287001287001287

   result = 104.12345
   print("The resulat was {r:1.3f}".format(r=result))   #  The resulat was104.123

   print("The resulat was {r:10.3f}".format(r=result)) 
   # The resulat was      0.129
```

---



```py
   name = "Jose"    
   print('Hello, his name is {}'.format( name))  # Hello, his name is Jose

   print(f'Hello, his name is {name}')   # new python 3.6
   # Hello, his name is Jose

   name = "Sam"
    age = 3
   print(f'{name} is {age} years old.')    #  Sam is 3 years old.
```