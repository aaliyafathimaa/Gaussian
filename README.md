# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
STEP 1:
Input Initialization
      *Read number of variables n using int(input()).
      *Initialize augmented matrix a of size n x (n+1) using np.zeros().
      *Fill matrix a with user input using nested loops and float(input()).
STEP 2:
Forward Elimination
      *For each pivot row i, check a[i][i] != 0.0 to avoid division by zero (sys.exit() if violated).
      *For rows below (j = i+1 to n-1), compute ratio = a[j][i] / a[i][i] and update row using a[j][k] = a[j][k] - ratio * a[i][k] for all columns k.
STEP 3:
Back Substitution
      *Set x[n-1] = a[n-1][n] / a[n-1][n-1].
      *For i from n-2 to 0, compute x[i] = (a[i][n] - Σ a[i][j]*x[j]) / a[i][i].
STEP 4:
Solution Output
      *Print all variables x[i] using formatted output: print('X%d = %0.2f' % (i, x[i])).
```
## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Aaliya Fathima.M
RegisterNumber: 212223230001
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
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
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
    print('X%d = %0.2f'%(i,x[i]), end=' ')
```

## Output:
![Screenshot 2025-04-27 162450]![alt text](<Screenshot 2025-05-28 190706-1.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

