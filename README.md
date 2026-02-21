# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of unknowns n and form the augmented matrix [A | B].
2. Convert the augmented matrix into upper triangular form using row operations:

𝑅
𝑗
=
𝑅
𝑗
−
(
𝑎
𝑗
𝑖
𝑎
𝑖
𝑖
)
𝑅
𝑖
R
j
	​

=R
j
	​

−(
a
ii
	​

a
ji
	​

	​

)R
i
	​

3. Check that no pivot element 
𝑎
𝑖
𝑖
=
0
a
ii
	​

=0.
If zero → system cannot be solved (division by zero)
4. Use Backward Substitution to find the values of unknowns 
𝑥
𝑛
,
𝑥
𝑛
−
1
,
.
.
.
,
𝑥
1
x
n
	​

,x
n−1
	​

,...,x
1
	​

.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Mohana Priya D
RegisterNumber: 212225230182
*/
```
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if (a[i][i]==0.0):
        sys.exit("Divide by zero deleted!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```

## Output:
<img width="1258" height="577" alt="image" src="https://github.com/user-attachments/assets/1fa83489-18ff-4b4d-9e47-ca4d3f328312" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

