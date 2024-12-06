# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Input and Initialization - Read number of equations and initialize arrays.

Step 2: Forward Elimination (Gaussian Elimination) - Eliminate coefficients below diagonal using row operations.

Step 3: Back Substitution - Calculate solutions from last row to first row.

Step 4: Print the Solutions - Print solutions in the format X%d = %0.2f. 

## Program:
import numpy as np
import sys

n=int(input())

a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            
    x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
            
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end='')
    

## Output:
![image](https://github.com/user-attachments/assets/2ee69c50-7218-4c9c-bc85-3ad99dbe565d)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

