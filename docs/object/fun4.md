## Useful functions


- The key parameter can be defined as a function to be called 
  on each element of list/iterable before comparison and sort, 
  respectively. In this case, the inline function lambda 
  `x: x[1]` is defined as a value of the key parameter. The 
  `lambda` function takes input x return `x[1]` which is the 
  second element of x.


```py


mylist = [[7, 8], [1, 2, 3], [2, 5, 6]]
# list(map(lambda x: x[1], mylist)) returns [8, 2 ,5]






mylistSort = sorted(mylist, key = lambda x: x[1])
# will sort the nested list based on the result of the lambda # function 










# The following code snippets print out the  
#frequency = { "a": 5,"b": 1, "c":1, "d": 0, "e": 3, "f":6}
# x = list(frequency.items());

x= [('a', 5), ('b', 1), ('c', 1), ('d', 0), ('e', 3), ('f', 6)]
x =   sorted ( x ,  key = lambda x:x[1])
print (x)
# [('d', 0), ('b', 1), ('c', 1), ('e', 3), ('a', 5), ('f', 6)]
```