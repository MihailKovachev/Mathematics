1. Differential Equation - an equation which contains derivatives

	Examples:

	$$ m \frac{dv}{dt} = F(t,v) $$
	
	$$ ay'' + by' + cy = g(t) $$
	
	**a) order** - the largest derivative present in the differential equation
	
	**b) types**
	- ordinary differential equations (ODEs) - a differential equation with only ordinary derivatives
	- partial differential equations (PDEs) - a differential equation with partial derivatives
	- linear differential equations - any equation which can be written in the following form
	
	$$a_n(x)y^{(n)}(x) + a_{n - 1}(x)y^{(n - 1)}(x) + ... + a_1(x)y' + a_0(x)y = g(x)$$
		- there are no products of the function, $y(x)$ and its derivatives
		- neither the function nor its derivatives occur to a power higher than 1
		- neither the function nor its derivatives are inside other functions such as $\sqrt{y'}$ or $e^y$
	
	**c) initial conditions** - initial conditions help determine which solution from the solution space is sought-after and typically have the form
	
	$$ y(x_0) = y_0 \text{ or } y^{(n)}(x_0) = y_n$$
	
	- Initial Value Problem (IVP) - a differential equation with an appropriate number of initial conditions (typically one for each derivative present and the function itself)
	- Interval of Validity (IOV) - the largest possible interval on which the solution is valid and matches the initial conditions

2. Direction Fields - a method of indirectly obtaining information about the solutions of a differential equation without actually finding them. It works by creating a graph plane with the independent variable on one axis and the function on the other. Then, arbitrary values are chosen for the function and the derivative is evaluated according to the given differential equation. Little arrows are then plotted on the horizontal line for the chosen value of the function. The sign and magnitude of the derivative determine the direction of the arrows.

	For example, this is the direction field for the equation $\frac{dv}{dt} = 9.8 - \frac{v}{5}$
	
	![](../../Resources/Images/Direction%20Field.gif)
	
	**a) equilibrium solution** - the value of the function which results in a horizontal line and can be found by setting the derivative to 0