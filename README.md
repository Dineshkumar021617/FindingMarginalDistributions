# Marginal distributions and correation coefficient  

# Aim : 

To find marginal distributions and correation coefficient of joint probability mass funcition of two dimensional random variables

![image](https://user-images.githubusercontent.com/104613195/168222062-bb7dec1f-f115-4669-8b4c-58283af8ccf3.png)

# Software required :  

Python

# Theory:

A marginal distribution is a distribution of values for one variable that ignores a more extensive set of related variables in a dataset.
The marginal mass function for X is found by summing over the appropriate column and the marginal mass function
for Y can be found be summing over the appropriate row.

Correlation coefficients are indicators of the strength of the linear relationship between two different variables. The coefficient of correlation is measure of degree of realtionship betwen two variavbles. A linear correlation coefficient that is greater than zero indicates a positive relationship. A value that is less than zero signifies a negative relationship. Finally, a value of zero indicates no relationship between the two variables x and y.  



# Procedure :
![image](https://user-images.githubusercontent.com/104613195/168220332-09383cb4-a7ac-4526-b547-fc522ca53227.png)



# Program:
```python
import math
import numpy as np
P = [[0,0.01,0.03,0.05,0.07,0.09],
    [0.01,0.02,0.04,0.05,0.06,0.08],
    [0.01,0.03,0.05,0.05,0.05,0.06],
    [0.01,0.02,0.04,0.06,0.06,0.05]]
Px = np.sum(P,axis=0)
print("Marginal distribution of x",Px)
Py = np.sum(P,axis=1)
print("Marginal distribution of y",Py)
x = [0,1,2,3,4,5]
Ex = np.inner(x,Px)
y = [0,1,2,3]
Ey = np.inner(y,Py)
Ex2 = np.inner(np.square(x),Px)
Vx = Ex2 - Ex**2
print("Variance: ",round(Vx,3))
Sx = math.sqrt(Vx)
print("SD: ",round(Sx,3))
Ey2 = np.inner(np.square(y),Py)
Vy = Ey2 - Ey**2
Sy = math.sqrt(Vy)
Exy = 0
for i in range(4):
    for j in range(6):
        Exy=Exy+(P[i][j]*x[j]*y[i])
Cov = Exy - Ex*Ey
r = Cov/(Sx*Sy)
print("The coefficient of Correlation is %0.4f"%r)
```




# Output:
![Screenshot (205)](https://user-images.githubusercontent.com/75234807/168963653-a8d0d0eb-e95c-48b6-8efd-76f041f12e4e.png)


# Result:
Thus, marginal distributions and correation coefficient of joint probability mass funcition of two dimensional random variables is found using python program.
