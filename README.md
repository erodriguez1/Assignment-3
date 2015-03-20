# Assignment-3
Plotting Experimental Data and the Quadratic Equation 


# Elizabeth Rodriguez
# Phys 50733
# Assignment 3


#1: Plotting Experimental Data
# There is a file in the online resources called stm.txt, which contains a grid of values from scanning tunneling microscope
#measurements of the (111) surface of silicon. A scanning tunneling microscope (STM) is a device that measures the shape of a surface
#at the atomic level by tracking a sharp tip over the surface and measuring quantum tunneling current as a function of position. The
#end result is a grid of values that represent the height of the surface and the file stm.txt contains just such a grid of values.
# Write a program that reads the data contained in the file and makes a density plot of the values. Use the various options and variants
#you have learned about to make a picture that shows the structure of the silicon surface clearly.
# For full credit: Email your program plus the plotted output that shows the structure of the silicon surface clearly.

from numpy import loadtxt
from pylab import imshow, show, title, colorbar
data=loadtxt("stm.txt",float)
title('STM Density Plot of the Surface of Silicon')
colorbar(orientation='vertical')
imshow(data)
show()

#2: Precision and e^(-x)
# Compute e^(-x) four different ways and plot the results to see the differences. Compute for 0-100 in steps of 5.

# (A) Compute using math function: exp(-i)

from math import exp
for i in range(0,105,5):
    e = exp(-i)
    print(i,e)

# (B) Simple expansion
# e^(-x) = sum (-1)^n(x^n/n!)

       

# (C) Simple expansion
# e^(-x) = sum s = sum (-1)^n(x^n/n!), where s= s_n-1 (x/n)



# (D) Simple inverse
# e^(-x) = 1/exp(x)

from math import exp
for i in range(0,105,5): #Sum of the first 100 terms in state 5
    e = 1/exp(i)
    print(i,e)

# For full credit: Email your program, plus an output of the program for each way showing the answers it produces. Additionally a plot
#with all 4 ways overplotted, so differences can be seen.


#3: The Quadratic Equation

# (A) Write a program that takes an input three numbers, a, b, and c, and prints out the two solutions to the quadratic equation
# ax^2+bx+c=0 using the standard formula:
# x = [-b +- sqrt(b^2-4ac)]/2a
# Use your program to compute the solutions of 0.001x^2+1000x+0.001=0.

import math
a = float(raw_input('a='))
if a == 0:
    print'Not a quadratic equation'
b = float(raw_input('b='))
c = float(raw_input('c='))
d = b**2-4*a*c
if d == 0:
    x = -b/(2*a)
    print'x=', x
if d > 0:
    x1 = (-b+math.sqrt(d))/(2*a)
    x2 = (-b-math.sqrt(d))/(2*a)
    print'x1=', x1
    print'x2=', x2
else:
    print'x1=', x,',', math.sqrt(-d)/(2*a)
    print'x2=', x,',', -math.sqrt(-d)/(2*a)

# (B) There is another way to write the solutions to a quadratic equation. Multiplying top and bottom of the solution above by
# -b -+ sqrt(b^2-4ac), show that the solutions can also be written as:
# x = 2c/[-b -+ sqrt(b^2-4ac)]
# Add further lines to your program to print these values in addition to the earlier ones and again use the program to solve
# 0.001x^2+1000x+0.001=0. What do you see? How do you explain it?

import math
a = float(raw_input('a='))
if a == 0:
    print'Not a quadratic equation'
b = float(raw_input('b='))
c = float(raw_input('c='))
d = b**2-4*a*c
if d == 0:
    x = (2*c)/(-b)
    print'x=', x
if d > 0:
    x1 = (2*c)/(-b-math.sqrt(d))
    x2 = (2*c)/(-b+math.sqrt(d))
    print'x1=', x1
    print'x2=', x2
else:
    print'x1=', x,',', (2*c)/(-math.sqrt(-d))
    print'x2=', x,',', (2*c)/math.sqrt(-d)

# (C) Using what you have learned, write a new program that calculates both roots of a quadratic equation accurately in all cases.

import cmath
a = float(input('Enter a:'))
b = float(input('Enter b:'))
c = float(input('Enter c:'))
d = (b**2)-(4*a*c)
x1 = round((-b-cmath.sqrt(d))/(2*a), 4)
x2 = round((-b+cmath.sqrt(d))/(2*a), 4)
print'The solutions are', x1, x2

# For full credit: Email your program and turn in your answers to part (B) and a print-out of it in action, showing the solution of
#the equation 0.001x^2+1000x+0.001=00.
