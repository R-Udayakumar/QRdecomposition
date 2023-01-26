# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```python
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Udayakumar R
RegisterNumber: 22008609
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    q = np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@q[:,j])*q[:,j]
        q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@q[:,i]
    print(q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)
```
## Output
![](Screenshot%20(71).png)
## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.