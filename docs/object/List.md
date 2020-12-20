## List in Python

### list

```py
my_list = ['STRING', 100, 23.2]
len(my_list)        # 3

mylist = ['one', 'two', 'three']                    #
mylist[0]                    # 'one'
mylist[1:]     # slice      ['two', 'three']

mylist                    # ['one', 'two', 'three']
 another_list = ['four','five']                   #
 new_list = mylist + another_list                   #
new_list                    #   ['one', 'two', 'three', 'four', 'five']
                    #
```

---

### add at first,  append()  pop()


```python
    # ['one', 'two', 'three', 'four', 'five']
    new_list[0] = 'ONE ALL CAPS'
    new_list                    # ['ONE ALL CAPS', 'two', 'three', 'four', 'five']

new_list.append('six')
new_list                        # ['ONE ALL CAPS', 'two', 'three', 'four', 'five', 'six']



# pop() method
new_list.pop()                  # return the last elment and delete;   seven'
 new_list                               # ['ONE ALL CAPS', 'two', 'three', 'four', 'five', 'six']
 new_list.pop(0)                               # 'ONE ALL CAPS'
new_list                                #   ['two', 'three', 'four', 'five', 'six']
                                #
         
```

---

# sort() method, can sort a list; but return nothing...
# reverse() method
```Python
new_list = ['a', 'e', 'x', 'b', 'c',]                                
new_list                                # ['a', 'b', 'c', 'e', 'x']

my_sorted_list = new_list.sort()       # new_list.sort(), doesnt' return anything
my_sorted_list                               #nothing
type(my_sorted_list)                         #NoneType
 
 num_list                           # [4, 1, 8, 3]     
 num_list.sort()                               
 num_list                       # [1, 3, 4, 8]

num_list.reverse()          # doesnt' return anything
num_list                    # [8, 4, 3, 1]

```
