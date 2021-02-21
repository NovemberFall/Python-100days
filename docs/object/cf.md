## Control flow

```py
dir ( range(10) )
d = [  i for i in range(10).__iter__() ]
d # same as list ( range(10) )
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]





# 08.3 For loop

x = [1.0, 2.0, 3.0]
for n in x:
    print(1 / n)
# 1.0
# 0.5
# 0.3333333333333333    







d = {1:1, 2:2,}
for i in d.__iter__():
    print(i)
# 1
# 2    







x = [1, 2, 3, 4]
squares = [ i*i for i in x]
squares
# [1, 4, 9, 16]








x = list( range(10) )
squares = [ i*i for i in x.__iter__() ]
squares
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]








x = list( range(10) )
squares = [ i*i for i in x.__iter__() ]
squares
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

---

## 08.3.1 range function

```py
# x = [1, 3, -7, 4, 9, -5, 4]
# for i in range(len(x)):
#     if x[i] < 0:
#         print("Found a negative number at index ", i)
# 

list(range(3, 7))   # [3, 4, 5, 6]
list(range(2, 10))  # [2, 3, 4, 5, 6, 7, 8, 9]        
list(range(5, 3))   # []
# 
# 
list(range(0, 10, 2))   # [0, 2, 4, 6, 8]
list(range(5, 0, -1))   # [5, 4, 3, 2, 1]
```

---

## 08.3.4 enumerate function

- `enumerate` return a pair

```py
help ( enumerate )

x = [1, 3, -7, 4, 9, -5, 4]
for i, n in enumerate(x):                               
    if n < 0:                                           
        print("Found a negative number at index ", i)   
# Found a negative number at index  2
# Found a negative number at index  5        
```

----

## `zip` function 

```py
x = [1, 2, 3, 4]
y = ['a', 'b', 'c']           #A 
z = zip(x, y)
list(z)
# [(1, 'a'), (2, 'b'), (3, 'c')]    #B







A = [ [1,2,3,4], [5,6,7,8] ]
B = [ list(x) for x in zip(A) ]
B
# [[[1, 2, 3, 4]], [[5, 6, 7, 8]]]




A = [ [1,2], [3,4] ]
B = [ list(x) for x in zip(A) ]
B
# [[[1, 2]], [[3, 4]]]





A = [ [1,2], [3,4] ]
B = [ list(x) for x in zip(*A) ]
B
# [[1, 3], [2, 4]]




A = [ [1,2,3,4], [5,6,7,8] ]
B = [ list(x) for x in zip(*A) ]
B
# [[1, 5], [2, 6], [3, 7], [4, 8]]
```

---

### zip

```py
p = [ [1,0], [0,1] ]
x = [ list(x) for x in zip(*p)]
x
# [[1, 0], [0, 1]]






A = [ [1,2], \
      [3,4] ]
B = [ list(x) for x in zip(*A) ]
[ print(r) for r in B]
# [1, 3]
# [2, 4]






A = [ [1,1,1], \
      [2,2,2] ]
B = [ list(x) for x in zip(*A) ]
[ print(r) for r in B]
# [1, 2]
# [1, 2]
# [1, 2]







A = [ [1,1,1], \
      [2,2,2], \
      [3,3,3] ]
print (*A)
# [1, 1, 1] [2, 2, 2] [3, 3, 3]





zip( [1, 1, 1], [2, 2, 2], [3, 3, 3]  )
# <zip at 0x7fb63557ad40>



x = zip( [1, 1, 1], [2, 2, 2], [3, 3, 3]  )
# x = zip(*A)     # same above
print(x)
# <zip object at 0x7fb6355313c0>
# Note: zip(*A), return a zip object








x = zip( [1, 1, 1], [2, 2, 2], [3, 3, 3]  )
# x = zip(*A)
for y in x: print(y)
# (1, 2, 3)
# (1, 2, 3)
# (1, 2, 3)





A = [ [1,1,1], \
      [2,2,2], \
      [3,3,3] ]
B = [ list(x) for x in zip(*A) ]
[ print(r) for r in B]
# [1, 2, 3]
# [1, 2, 3]
# [1, 2, 3]





import copy
def dot (A, B):
    z = ( a*b for a,b in zip(A,B) )
    return sum(z)

def mul(X, Y):
    Y = [ list(y) for y in zip(*Y) ] # transpose matrix Y
    print("Y=", Y)
    Z = [ [ dot(x,y) for y in Y ] for x in X]
    for i in range( len(Z) ):
        for j in range( len(Z[i])  ):
            X[i][j] = Z[i][j]
    return X[0][j]

p = [ [1,0], [0,1] ]
q = [ [1,1], [1,0] ]
n = 10
[0] + [ mul(p,q) for _ in range (n)]

# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# Y= [[1, 1], [1, 0]]
# [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
```