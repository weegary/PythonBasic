# Chapter 05: Math

Python ```math``` module provides some useful mathematical functions. <br/>

## Number-theoretic and representation functions

|Function|Description|
|---|---|
|```math.fabs(x)```|Return the absolute value of x|
|```math.ceil(x)```|Return the ceiling of x|
|```math.floor(x)```|Return the floor of x|
|```math.factorial(x)```|Return the factorial of x|
|```math.isinf(x)```|Return True if x is a positive or negative infinity, and False otherwise|
|```math.isnan(x)```|Return True if x is a NaN (not a number), and False otherwise|

## Power and logarithmic functions

|Function|Description|
|---|---|
|```math.exp(x)```|Return e raised to the power x, where e = 2.718281... is the base of natural logarithms. This is usually more accurate than ```math.e ** x``` or ```pow(math.e,x)```|
|```math.log(x[,base]```|With one argument, return the natural logarithm of x (to base e).<br/>With two arguments, return the logarithm of x to the given base, calculated as ```log(x)/log(base)```|
|```math.log2(x)```|Return the base-2 logarithm of x. This is usually more accurate than ```log(x, 2)```|
|```math.log10(x)```|Return the base-10 logarithm of x. This is usually more accurate than ```log(x, 10)```|
|```math.pow(x,y)```|Return x raised to the power y|
|```math.sqrt(x)```|Return the square root of x|
|```math.cbrt(x)```|Return the cube root of x|

## Trigonometric and hyperbolic functions
|Function|Description|
|---|---|
|```math.dist(p,q)```|Return the Euclidean distance between two points p and q, each given as a sequence (or iterable) of coordinates. The two points must have the same dimension|
|```math.sin(x)```|Return the sine of x radians|
|```math.cos(x)```|Return the cosine of x radians|
|```math.tan(x)```|Return the tangent of x radians|
|```math.asin(x)```|Return the arc sine of x, in radians. The result is between -pi/2 and pi/2|
|```math.acos(x)```|Return the arc cosine of x, in radians. The result is between 0 and pi|
|```math.atan(x)```|Return the arc tangent of x, in radians. The result is between -pi/2 and pi/2|
|```math.sinh(x)```|Return the hyperbolic sine of x|
|```math.cosh(x)```|Return the hyperbolic cosine of x|
|```math.tanh(x)```|Return the hyperbolic tangent of x|
|```math.asinh(x)```|Return the inverse hyperbolic sine of x|
|```math.acosh(x)```|Return the inverse hyperbolic cosine of x|
|```math.atanh(x)```|Return the inverse hyperbolic tangent of x|

## Angular conversion functions
|Function|Description|
|---|---|
|```math.degrees(x)```|Convert angle x from radians to degrees|
|```math.radians(x)```|Convert angle x from degrees to radians|

## Constants
|Constant|Description|
|---|---|
|```math.pi```|The mathematical constant π = 3.141592…, to available precision|
|```math.e```|The mathematical constant e = 2.718281…, to available precisionn|
|```math.tau```|The mathematical constant τ = 6.283185…, to available precision. Tau is a circle constant equal to 2π, the ratio of a circle’s circumference to its radius|
|```math.inf```|A floating-point positive infinity. (For negative infinity, use -math.inf.) Equivalent to the output of ```float('inf')```|
|```math.nan```|A floating-point “not a number” (NaN) value. Equivalent to the output of float('nan').<br/>To check whether a number is a NaN, use the ```math.isnan()``` function to test for NaNs instead of ```is``` or ```==```|

For the full documentation of all the functions, please find the Reference: [Click Here](https://docs.python.org/3/library/math.html#number-theoretic-and-representation-functions) <br/>

For your information,
Most of the functions or constants can also be accessed in the [```numpy``` module](ChpX_Numpy.md). <br/>
Use ```math``` if you are doing simple computations with only scalars (and no lists or arrays). <br/>
Use ```numpy``` if you are doing scientific computations with matrices, arrays, or large datasets.
