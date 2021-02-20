
## format() method


```py
   print('This is a string{}'.format(' INSERTED'))  
   # This is a string INSERTED 

   print('The {2} {1} {0}'.format('fox','brown','quick')) 
   # The quick brown fox

   print('The {0} {0} {0}'.format('fox','brown','quick')) 
   # The fox fox fox

   print('The {q} {b} {f}'.format(f = 'fox', b = 'brown', q='quick'))  # The quick brown fox

   print('The {f} {f} {f}'.format(f = 'fox', b = 'brown', q='quick'))   # The fox fox fox
```

---

## Float formatting follows "{value:width.precision f}"

```py
   result = 100/777     # 0.1287001287001287

   print("The resulat was {r} ".format(r=result))    
   # The resulat was 0.1287001287001287

   result = 104.12345
   print("The resulat was {r:1.3f}".format(r=result))   
   #  The resulat was104.123

   print("The resulat was {r:10.3f}".format(r=result)) 
   # The resulat was      0.129
```

---



```py
   name = "Jose"    
   print('Hello, his name is {}'.format( name))  
   # Hello, his name is Jose

   print(f'Hello, his name is {name}')   
   # new python 3.6
   # Hello, his name is Jose

   name = "Sam"
    age = 3
   print(f'{name} is {age} years old.')    
   #  Sam is 3 years old.
```

-----


### 06.6.1 format method

```py
"{0} is the {1} of {2}".format(
   "Ambrosia", "food", "the gods") 
# 'Ambrosia is the food of the gods'


"{{Ambrosia}} is the {0} of {1}".format(
   "food", "the gods")    
# '{Ambrosia} is the food of the gods'
```

---

### 06.6.2 format method, named params

```py
"{food} is the food of {user}".format(
   food="Ambrosia", user="the gods")  
# 'Ambrosia is the food of the gods'




"{0} is the food of {user[1]}".format(
   "Ambrosia",  user=["men", "the gods", "others"])   
# 'Ambrosia is the food of the gods'
```

---

### 06.6.3 format specifiers

```py
"{0:10} is the food of gods".format("Ambrosia")      
# 'Ambrosia   is the food of gods'





"{0: ^20} is the food of gods".format("Ambrosia")    
# '      Ambrosia       is the food of gods'



"{0:{1}} is the food of gods".format("Ambrosia", 10)   
# 'Ambrosia   is the food of gods'



"{food:{width}} is the food of gods".format(
   food="Ambrosia", width=10)
# 'Ambrosia   is the food of gods'



"{0:>10} is the food of gods".format("Ambrosia")         
# '  Ambrosia is the food of gods'



"{0:&>10} is the food of gods".format("Ambrosia")        
# '&&Ambrosia is the food of gods'
# 注意：左边空格的地方由 && 填补




"{0:#>20} is the food of gods".format("Ambrosia") 
'############Ambrosia is the food of gods'
```

---

### Formatting strings with %

```py
"%s is the %s of %s" % ("Ambrosia", "food", "the gods")  
# 'Ambrosia is the food of the gods'



"%s is the %s of %s" % (
   "Nectar", "drink", "gods")                 
# 'Nectar is the drink of gods'


"%s is the %s of the %s" % (
   "Brussels Sprouts", "food","foolish")  
# 'Brussels Sprouts is the food of the foolish'




x = [1, 2, "three"]
"The %s contains: %s" % ("list", x)            
# "The list contains: [1, 2, 'three']"




x = "Pi is <%-6.2f>" % 3.14159                 
# 'Pi is <3.14  >'

y = "Pi is (%-1.2f, %-1.2f) " % (3.14159,0)                
# 'Pi is (3.14, 0.00) '

```

---

## 06.7.2 Named params and Formatting sequences

```py
num_dict = {'e': 2.718, 'pi': 3.14159}
print("%(pi).2f - %(pi).4f - %(e).2f" % num_dict)
# 3.14 - 3.1416 - 2.72
```