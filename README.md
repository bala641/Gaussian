# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### step 1:Input the augmented matrix of the system (coefficients + constants).

### step 2:Apply forward elimination to transform the matrix into upper triangular form.

### step 3:Check for division by zero during elimination to avoid singularities.

### step 4:Apply back substitution to solve for unknown variables starting from the last row.

### step 5:Output the values of all variables.



## Program:
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: BALA B
RegisterNumber: 212224100005
'''


~~~python
import numpy as np
import sys

n = int(input())

a = np.zeros((n, n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')

    for j in range(i+1, n):
        ratio = a[j][i] / a[i][i]

        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n-1] = a[n-1][n] / a[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = a[i][n]

    for j in range(i+1, n):
        x[i] = x[i] - a[i][j] * x[j]

    x[i] = x[i] / a[i][i]

for i in range(n):
    print('X%d = %0.2f' % (i, x[i]), end=' ')
## Output:
![gaussian elimination]()
~~~
##output:
![image](https://github.com/user-attachments/assets/3cf27fab-65af-4860-824f-a8871b029e08)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

