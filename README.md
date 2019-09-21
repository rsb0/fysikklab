# fysikklab

This is code written to perform calculations based on observations gathered from a laboratory experiment in the
course TFY4125 - Physics, at Norwegian University of Science and Technology (NTNU)

The Data directory contains output from a tracker software used to track the movement of a ball rolling on an inverse
parabolic track (half pipe).

Euler.py contains code for predicting the ball's motion along the path given it's initial position, the angle of the path
relative to horizontal plane and gravity, and applying Euler's method for solving first order differential equations 
numerically.

Force.py calculates the ball's nomal force and force of friction exerted on it by track as a funtion of x-position. It
uses output data from the tracker software to obtain velocities in x and y direction.

Iptrack.py is code provided to us. 
It takes data file containing exported tracking data on the standard Tracker export format as input and outputs
the coefficients of a polynomial of degree 15 that is the least square fit to the data y(x). Coefficients are given in
descending powers.

lab.py plots forces and speed of the ball as it moves along the path

speed.py calculates the balls speed 

truevalues.py is code provided to us
takes arguments: 
p: the n+1 coefficients of a polynomial of degree n, given in descending order. 
(For instance the output from p=iptrack(filename).)
x: ordinate value at which the polynomial is evaluated.

outputs:
[y,dydx,d2ydx2,alpha,R]=trvalues(p,x) returns the value y of the polynomial at x, the derivative dydx and the 
second derivative d2ydx2 in that point, as well as the slope alpha(x) and the radius of the osculating circle.
The slope angle alpha is positive for a curve with a negative derivative. The sign of the radius of the 
osculating circle is the same as that of the second derivative.

util.py: contains function to plot data, extract the maximum height the ball reach after traversing the path, 
calulate the curve-fit, and save and get data from the data directory
