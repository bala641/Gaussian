# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the number of unknowns
2. Input the augmented matrix
3. Forward Elimination to form an upper triangular matrix
4. Back Substitution to find unknowns
5. Display the result

## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by:BALA B
RegisterNumber:212224100005
'''
import numpy as np
import sys
#Reading number of unknowns
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
#applying gauss elimination
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
#back substitution
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i] - a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
#displaying solution
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```


##output:
![image](https://github.com/user-attachments/assets/3cf27fab-65af-4860-824f-a8871b029e08)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

