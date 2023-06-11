# Algorithm for QR Decomposition

## Aim:

To implement QR decomposition algorithm using the Gram-Schmidt method.

## Equipment’s required:

1.	Hardware – PCs

2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm:

1.	Intialize the matrix Q and u

2.	The vector u and e is given by 

![image](https://github.com/SivaramakrishnanBaskar/QRdecomposition/assets/119476322/42f1d060-d10e-48c4-bc2b-51ba0d70a1b8)


3.	Obtain the Q matrix   

![image](https://github.com/SivaramakrishnanBaskar/QRdecomposition/assets/119476322/ed9f4d91-8570-4cc3-b7ad-7eb62cf77494)

4.	Construct the upper triangular matrix R.

![image](https://github.com/SivaramakrishnanBaskar/QRdecomposition/assets/119476322/e6018a2b-330a-4676-aeb3-7d42b45a799e)

    
## Program Using Gram-Schmidt Method:
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: Sivaramakrishnan B
Register Number: 212222110044
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i): 
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output 
![image](https://github.com/SivaramakrishnanBaskar/QRdecomposition/assets/119476322/3fe06354-1476-4dec-956f-adca9222ce5f)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
