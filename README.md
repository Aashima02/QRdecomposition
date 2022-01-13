# Algorithm for QR Decomposition
## AIM: 
To implement QR decomposition algorithm using the Gram-Schmidt method.

## EQUIPMENT'S REQUIRED:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner

## ALGORITHM:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)

## PROGRAM:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: Aashima Nazreen Sayeed S
RegisterNumber: 21500368

import numpy as np
def qrDecomposition(A):
    n,m = A.shape
    Q = np.empty((n,n))
    U = np.empty((n,n))
    
    U[:,0] = A[:,0]
    Q[:,0] = U[:,0]/ np.linalg.norm(U[:,0])
    
    for i in range(1,n):
        U[:,i] = A[:,i]
        for j in range(i):
            U[:,i] -= (A[:,i]@Q[:,j])*Q[:,j]
            Q[:,i] = U[:,i]/np.linalg.norm(U[:,i])
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j] = A[:,j]@Q[:,i]
    print(Q)
    print(R)
A = np.array(eval(input()))
qrDecomposition(A)
```

## OUTPUT:
![output](https://user-images.githubusercontent.com/93427086/149271133-c5385afb-646a-409c-9c03-5d1ada789675.png)
## RESULT:
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
