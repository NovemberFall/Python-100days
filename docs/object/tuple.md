## Tuples with Python

- Tuples are very similar to List. However they have one key different - **immutability**
  - Once an element is inside a tuple, it can not be reassigned.
  - Tuples are parenthesis: (1, 2, 3)

---

```py
t = (1,2,3)            # tuple
mylist = [1,2,3]       #list
 type(t)               #tuple
 len(t)                #3
 t                     #(1, 2, 3)



t = ('one',2)                
t[0]                   #'one'
t[-1]                  #2

t = ('a','a','b')
t.count('a')           #2
t.index('a')           # 0;  the very first index
t.index('b')           #2

mylist[0]='NEW'
mylist                 #['NEW', 2, 3]

t[0] ='NEW'            # TypeError: 'tuple' object does not support item assignment
```