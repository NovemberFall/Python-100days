## useful Operators in Python


```py
mylist = [1,2,3]

for num in range(10):
    print(num)

0
1
2
3
4
5
6
7
8
9




for num in range(0, 11, 2):
    print(num)
0
2
4
6
8
10

list(range(0, 11, 2))
[0, 2, 4, 6, 8, 10]









index_count = 0

for letter in 'abcde':
    print('At index {} the letter is {}'.format(index_count,letter))
    index_count += 1
At index 0 the letter is a
At index 1 the letter is b
At index 2 the letter is c
At index 3 the letter is d
At index 4 the letter is e




index_count = 0
word = 'abcde'
for letter in word:
    print(word[index_count])
    index_count += 1
a
b
c
d
e
word = 'abcde'
for item in enumerate(word):
    print(item)
(0, 'a')
(1, 'b')
(2, 'c')
(3, 'd')
(4, 'e')
word = 'abcde'

for index,letter in enumerate(word):
    print(index)
    print(letter)
    print('\n')
0
a


1
b


2
c


3
d


4
e




mylist1 = [1,2,3]
mylist2 = ['a','b','c']
mylist3 = [100,200,300]

for item in zip(mylist1,mylist2,mylist3):
    print(item)


(1, 'a', 100)
(2, 'b', 200)
(3, 'c', 300)




list(zip(mylist1,mylist2))



[(1, 'a'), (2, 'b'), (3, 'c')]

'x' in [1,2,3]

False

'x' in ['x', 'y', 'z']

True



'a' in 'a world'
True



'mykey' in {'mykey':345}
True




d = {'mykey':345}

345 in d.keys()
False




mylist = [10,20,30,40,100]
min(mylist)
10


max(mylist)
100





from random import shuffle
mylist = [1,2,3,4,5,6,7,8,9,10]
shuffle(mylist)  # shuffle is a in-place fucntion
mylist
[2, 8, 1, 3, 9, 7, 4, 5, 6, 10]





random_list = shuffle(mylist)  # shuffle is a in-place fucntion
type(random_list)
NoneType





from random import randint
randint(0, 100)
79



randint(0, 100)
44


mynum = randint(0, 10)
mynum
7



input('Enter a number here: ')
'50'
```