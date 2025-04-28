# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.  Input:
First input: number of unknowns n

Next inputs: all elements of augmented matrix (normal matrix + right-hand side).


2. Forward Elimination (make zeros below diagonal):
For each row:

Divide and subtract rows to make zeros below the current row.

Formula for elimination:ratio= 
a[i][i]
a[j][i]
​
 
Row
𝑗
=
Row
𝑗
−
ratio
×
Row
𝑖
Row 
j
​
 =Row 
j
​
 −ratio×Row 
i
​
 

3.Back Substitution (find the answers):
Start from the last unknown.

Plug values backward into the earlier equations.

Formula:

𝑥
[
𝑖
]
=
𝑎
[
𝑖
]
[
𝑛
]
−
∑
𝑗
=
𝑖
+
1
𝑛
−
1
𝑎
[
𝑖
]
[
𝑗
]
×
𝑥
[
𝑗
]
𝑎
[
𝑖
]
[
𝑖
]
x[i]= 
a[i][i]
a[i][n]−∑ 
j=i+1
n−1
​
 a[i][j]×x[j]


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

