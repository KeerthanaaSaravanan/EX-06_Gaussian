# EX-06: Gaussian Elimination
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.
## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm
1. Get the size of the system (n).
2. Initialize matrices for the augmented system and the solution.
3. Input the coefficients of the augmented matrix.
4. Perform Gaussian Elimination to convert the matrix to upper triangular form.
5. Perform Back Substitution to find the solution vector.
6. Output the results.
## Program:
```
'''
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: KEERTHANA S
RegisterNumber: 23013398
'''
import numpy as np
n=int(input())
arr=np.zeros((n,n+1))
res=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        arr[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=arr[j][i]/arr[i][i]
        for k in range(n+1):
            arr[j][k]=arr[j][k]-ratio*arr[i][k]
res[n-1]=arr[n-1][n]/arr[n-1][n-1]
for i in range(n-1,-1,-1):
    res[i]=arr[i][n]
    for j in range(i+1,n):
        res[i]=res[i]-arr[i][j]*res[j]
    res[i]=res[i]/arr[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,res[i]), end=" ")
```

## Output:
![Screenshot 2023-12-23 144732](https://github.com/KeerthanaaSaravanan/EX-06_Gaussian/assets/145742596/d6fa3a57-7a9a-4dd0-bf5c-298a72280d29)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

