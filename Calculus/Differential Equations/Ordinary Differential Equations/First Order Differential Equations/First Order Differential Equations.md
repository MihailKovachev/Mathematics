$$ \frac{dy}{dx} = f(x, y(x)) $$

1. Linear Differential Equations - equations of the form
	$$y' + p(x)y = g(x)$$
	where $p(x)$ and $g(x)$ are given functions. Equations of the form $$q(x)y' + p(x)y = g(x)$$ can be converted to the above form by dividing both sides by $q(x)$
	$$q(x)y' + p(x)y = g(x) \Rightarrow y' + \frac{p(x)}{q(x)}y = \frac{g(x)}{q(x)}, q(x) \ne 0$$
	
	Such equations can be solved by the *Method of Integrating Factors*. It begins by multiplying both sides by a yet unknown function, $\mu(x)$. The premise is to turn the left hand-side into a derivative of a single function, namely the product $\mu(x)y(x$), via the product rule.
	$$y' + p(x)y = g(x)$$
	$$\mu(x)\frac{dy}{dx} + p(x)\mu(x)y = \mu(x)g(x)$$
	Now, the product rule tells us that
	$$\frac{d}{dx}\mu(x)y(x) = \mu(x)\frac{dy}{dx} + y(x)\frac{d\mu(x)}{dx}$$
	In order for this to match the left-hand side of equation, we need to find a $\mu(x)$ such that $\frac{d\mu(x)}{dx} = p(x)\mu(x)$. Now, this is a differential equation which is easily solved to give us $\mu(x)$.
	$$\frac{d\mu(x)}{dx} = p(x)\mu(x)$$
	$$\frac{d\mu(x)}{dx}\frac{1}{\mu(x)} = p(x), \mu(x) \ne 0$$
	The left-hand side is a well-known derivative:
	$$\frac{d}{dx}\ln({\mu(x)}) = p(x)$$
	$$\ln(\mu(x)) = \int{p(x) dx} + C$$
	The constant doesn't matter, since
	$$\frac{d}{dx}(f(x) + C)y(x) = \frac{d}{dx}(f(x)y(x) + Cy(x)) = y(x)\frac{df}{dx} + f(x)\frac{dy}{dx} + C\frac{dy}{dx} = \frac{df}{dx}y(x) + (f(x) + C)\frac{dy}{dx}$$
	which still obeys the product rule. This means that we can just set the constant $C$ to 0 for ease. Therefore, taking the exponential of both sides,
	$$\mu(x) = e^{\int{p(x) dx}} = \exp\left(\int{p(x) dx}\right)$$
	Now, since $p(x)$ is a given function, the above integral can typically be evaluated.
	Let's return back to our original equation.
	$$\mu(x)\frac{dy}{dx} + p(x)\mu(x)y = \mu(x)g(x)$$
	Having found a $\mu(x)$ for which $\frac{d\mu(x)}{dx} = p(x)\mu(x)$, we can substitute for the derivative of $\mu(x)$.
	$$\mu(x)\frac{dy}{dx} + \frac{d\mu(x)}{dx}y = \mu(x)g(x)$$
	$$\frac{d}{dx}\mu(x)y = \mu(x)g(x)$$
	$$\mu(x)y = \int{\mu(x)g(x) dx} + C$$
	Ultimately,
	$$y(x) = \frac{1}{\mu(x)}\left(\int{\mu(x)g(x) dx} + C\right)$$
	
	When the differential equation has the form
	$$y' + ay = g(t)$$
	where $a$ is a constant, then the integrating factor is $\mu(t) = e^{at}$. Therefore, the general solution simplifies to
	$$y(t) = e^{-at}\left(\int{e^{at}g(t) dt} + C\right) = e^{-at}\int{e^{at}g(t) dt} + Ce^{-at}$$
	I changed $x$ for $t$ solely because it looks nicer.

