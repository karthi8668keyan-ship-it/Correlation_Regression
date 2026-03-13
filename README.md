# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
~~~
import numpy as np
import matplotlib.pyplot as plt

print("Enter X values:")
X = np.array([int(i) for i in input().split()])

print("Enter Y values:")
Y = np.array([int(i) for i in input().split()])

N = len(X)

SumX = np.sum(X)
SumY = np.sum(Y)
SumX2 = np.sum(X**2)
SumY2 = np.sum(Y**2)
SumXY = np.sum(X*Y)

# Means
MeanX = SumX/N
MeanY = SumY/N

# Correlation coefficient
num = (N*SumXY) - (SumX*SumY)
den = np.sqrt((N*SumX2 - SumX**2) * (N*SumY2 - SumY**2))
r = num/den

print("Coefficient of Correlation r =", round(r,3))

# Regression coefficient
b = num / (N*SumX2 - SumX**2)

print(f"Regression line Y on X: Y = {b:.3f}(X - {MeanX:.3f}) + {MeanY:.3f}")

# Regression function
def reg(x):
    return MeanY + b*(x-MeanX)

# Graph
plt.scatter(X,Y)
plt.plot(sorted(X),reg(np.array(sorted(X))))
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Regression Line")
plt.grid(True)
plt.show()
~~~
# Output 

![WhatsApp Image 2026-03-13 at 4 22 32 PM](https://github.com/user-attachments/assets/31944e32-8e1c-4a4a-8964-b1a3f7436252)

# Result

Thus the program is implemented and executed successfully.

