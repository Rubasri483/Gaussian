# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1. Start the program and enter the number of unknowns in the equations.

2. Read the augmented matrix which contains the coefficients of variables and constants.

3. Use forward elimination to make all elements below the main diagonal zero, forming an upper triangular matrix.

4. Check for zero pivot elements and stop the program if division by zero occurs.

5. Apply back substitution to find the values of all unknown variables starting from the last equation.

6. Display the final results of all variables with two decimal places and stop the program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: R.Rubasri
RegisterNumber: 212224240139
*/
```
```python
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
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio*a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```

## Output:
<img width="849" height="391" alt="image" src="https://github.com/user-attachments/assets/f44947bf-8121-460b-a618-ee9cfd16336a" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

