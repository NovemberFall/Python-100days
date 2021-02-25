## NumPy Introduction

### What is NumPy?

- NumPy is a Python library used for working with arrays.
- It also has functions for working in domain of linear 
  algebra, fourier transform, and matrices.
- NumPy was created in 2005 by Travis Oliphant. It is an open 
  source project and you can use it freely.
- NumPy stands for Numerical Python

![](img/2021-02-25-03-54-32.png)

- [The source code for NumPy is at this github repository](https://github.com/numpy/numpy)


```py
import numpy as np    # np is an alias for numpy
# print (dir(np))


I = [ [1,0], [0,1] ]
Q = [ [1,1], [1,0] ]  # Q
I = np.array(I)
I
# array([[1, 0],
#        [0, 1]])



def mul(X, Y):
    X = np.array(X)
    Y = np.array(Y)
    Z = X.dot(Y)
    print(Z)
    return Z.tolist() # converted back to the python 2d list

X = [ [1,0], [0,1] ]
Y = [ [1,1], [1,0] ]
C = mul(X, Y)
C
# [[1 1]
#  [1 0]]

# [[1, 1], [1, 0]]
```

---

- fibonacci

```py
import numpy as np    # np is an alias for numpy

def fib (n):   
    I = [ [1,0], [0,1] ]
    Q = [ [1,1], [1,0] ]  # Q
    I = np.array (I)
    Q = np.array(Q)
    if ( n==0):
        return I
    p = fib (n//2)
    p = p.dot(p)
    if n%2:
        p = p.dot(Q)
    return p
    

n=10
ans = [ fib(i)[0][1] for i in range(n)]

print ( ans )
# [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]

```



