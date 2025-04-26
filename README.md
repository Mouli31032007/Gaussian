# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## 1.  Create zero matrices
       Create a 2D array a of size n x (n+1) for the augmented matrix.
       Create a 1D array x of size n to store the solution.
## 2. Input coefficients into matrix a
      You are inputting the values of an augmented matrix a of size n x (n+1).
## 3. Forward Elimination (Make matrix upper triangular)
      Loop over each pivot row, Check for divide-by-zero (pivot cannot be 0)
## 4.Back Substitution (solve for x) 
     Solve for the last variable,Solve remaining variables in reverse order.
    Display the results

## Program:
```
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

/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: S.MOULIDHARAN
RegisterNumber: 212224240095
*/
```
## Output:
![image](https://github.com/user-attachments/assets/b02fddaa-c002-46fa-b180-6bd304dbe70e)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

