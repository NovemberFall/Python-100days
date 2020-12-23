## for loop

```py
mylist = [1,2,3,4,5,6,7,8,9,10]
In [2]:
for num in mylist: 
    print(num)
1
2
3
4
5
6
7
8
9
10



In [4]:
for num in mylist:
    # Check for even
    if num % 2 == 0:
        print(num)
    else:
        print(f'Odd Number: {num}')
Odd Number: 1
2
Odd Number: 3
4
Odd Number: 5
6
Odd Number: 7
8
Odd Number: 9
10





In [5]:
list_sum = 0

for num in mylist:
    list_sum += num

print(list_sum)
55







In [6]:
mystring = 'Hello World'

for letter in mystring:
    print(letter)
H
e
l
l
o
 
W
o
r
l
d







In [7]:
tup = (1,2,3)

for item in tup:
    print(item)
1
2
3






In [8]:
mylist = [(1,2), (3,4), (5,6), (7,8)]

In [9]:
len(mylist)
Out[9]:
4


In [10]:
for item in mylist:
    print(item)
(1, 2)
(3, 4)
(5, 6)
(7, 8)





In [11]:
for (a,b) in mylist:
    print(f'{a}, {b}')
1, 2
3, 4
5, 6
7, 8




In [12]:
mylist = [(1,2,3), (5,6,7), (8,9,10)]

In [13]:
for a,b,c in mylist:
    print(f'({a}, {b}, {c})')
(1, 2, 3)
(5, 6, 7)
(8, 9, 10)


In [14]:
d = {'k1':1, 'k2':2, 'k3':3}

for item in d:
    print(item)
k1
k2
k3



In [15]:
for item in d.items():
    print(item)
('k1', 1)
('k2', 2)
('k3', 3)



In [17]:
for key,value in d.items():
    print(value)
    print(f'{key} => {value}')
1
k1 => 1
2
k2 => 2
3
k3 => 3



In [18]:
for value in d.values():
    print(value)
1
2
3
```























