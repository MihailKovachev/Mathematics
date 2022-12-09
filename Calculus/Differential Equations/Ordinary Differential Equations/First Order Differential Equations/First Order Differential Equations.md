$$\frac{dy}{dx} = f(x, y(x))$$
# Existence and Uniqueness Theorem
Before solving a given initial value problem, it is useful to know if there even is a solution to seek after. This is what the Existence and Uniqueness Theorem for first order differential equations tells us. For the initial value problem of the form,

$$
\begin{cases}
\frac{dy}{dx} = f(x, y(x))\\
y(x_0) = y_0
\end{cases}
$$

If $f(x, y(x))$ is continuous on an open interval $(a,b)$, containing the point $x_0$, then there is *at least one* solution to the given IVP within that interval. If, however, $f(x, y(x))$ is NOT continuous, then the existence of any solutions is NOT guaranteed.

If also $\frac{\partial f}{\partial y}$ is continuous on that same open interval, $(a, b)$, then there is a *unique* solution to the IVP, meaning that there is only one solution to the differential equation which also matches the initial conditions.

# Linear Differential Equations

Equations of the form
$$y' + p(x)y = g(x)$$
where $p(x)$ and $g(x)$ are given functions. Equations of the form $$q(x)y' + p(x)y = g(x)$$ can be converted to the above form by dividing both sides by
$q(x)$
$$q(x)y' + p(x)y = g(x) \Rightarrow y' + \frac{p(x)}{q(x)}y = \frac{g(x)}{q(x)}, q(x) \ne 0$$
	
Such equations can be solved by the *Method of Integrating Factors*. It begins by multiplying both sides by a yet unknown function, $\mu(x)$. The premise is to turn the left hand-side into a derivative of a single function, namely the product $\mu(x)y(x$), via the product rule.
$$y' + p(x)y = g(x)$$
$$\mu(x)\frac{dy}{dx} + p(x)\mu(x)y = \mu(x)g(x)$$
Now, the product rule tells us that
$$\frac{d}{dx}\mu(x)y(x) = \mu(x)\frac{dy}{dx} + y(x)\frac{d\mu(x)}{dx}$$
In order for this to match the left-hand side of the equation, we need to find a $\mu(x)$ such that $\frac{d\mu(x)}{dx} = p(x)\mu(x)$. Now, this is a differential equation which is easily solved to give us $\mu(x)$.
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

Example:
$$\begin{cases}\\
ty' + (t+1)y = t, t \ne 0\\
y(\ln(2)) = 1\\
\end{cases}$$
$$\Downarrow$$
$$y' + \frac{t+1}{t}y = 1$$
$$\mu(t)y' + \mu(t)\frac{t+1}{t}y = \mu(t)$$
$$\Downarrow$$
$$\frac{d\mu(t)}{dt} = \mu(t)\frac{t+1}{t}$$
$$\frac{d\mu(t)}{dt}\frac{1}{\mu(t)} = \frac{t+1}{t}, \mu(t) \ne 0$$
$$\ln(\mu(t)) = \int{\frac{t+1}{t} dt} = \int{1 dt} + \int{\frac{1}{t} dt}$$
$$\ln(\mu(t)) = t + \ln(t) + C$$
$$\mu(t) = te^t$$
$$\Downarrow$$
$$te^t\frac{dy}{dt} + te^t\frac{t+1}{t}y = te^t$$
$$\frac{d}{dt}te^ty = te^t$$
$$te^ty = \int{te^t dt} + C$$
$$y(t) = \frac{e^{-t}}t\left(e^t(t-1) + C\right) = \frac{t-1}{t} + \frac{Ce^{-t}}{t} = 1 - \frac{1}{t} + \frac{Ce^{-t}}{t}$$
Now, this was an initial value problem so we can solve for the correct value of $C$ by substituting for $t$ and $y(t)$ with $\ln(2)$ and $1$, respectively.
$$1 = 1 - \frac{1}{\ln(2)} + \frac{Ce^{-\ln(2)}}{\ln(2)}$$
$$\frac{1}{\ln(2)} = \frac{C}{2\ln(2)}$$
$$C = 2$$
$$\Downarrow$$
$$y(t) = 1 - \frac{1}{t} + \frac{2e^{-t}}{t}$$

# Separable Differential Equations
Any first-order differential equation which can be written in the following form is called separable.

$$f(x) + g(y)\frac{dy}{dx} = 0$$

Such equations can be easily solved by splitting the differential, moving the two terms on separate sides of the equation and integrating.

$$f(x) + g(y)\frac{dy}{dx} = 0$$
$$\Downarrow$$
$$f(x)dx + g(y)dy = 0$$
$$f(x)dx = -g(y)dy$$
$$\int{f(x) dx} = -\int{g(y) dy}$$

Now, splitting the differential like that is cheating in general, but it does make our lives much easier. The reason why we are allowed to do this is explained in the following proof.

Let $F(x)$ and $G(y)$ be antiderivatives of $f(x)$ and $g(y)$, respectively. Then,
$$F'(x) + G'(y)\frac{dy}{dx} = 0$$
Since $y$ is a function of $x$, then by the chain rule we have that
$$G'(y) = G'(y)\frac{dy}{dx}$$
And so we can substitute in the above equation.
$$F'(x) + G'(y)\frac{dy}{dx} = 0$$
$$\Downarrow$$
$$F'(x) + G'(y) = 0$$
$$\Downarrow$$
$$\frac{d}{dx}(F(x) + G(y)) = 0$$
And integrating with respect to $x$, we obtain that
$$F(x) + G(y) = C$$

This gives us an *implicit* solution to the differential equation. Note that it i often not possible to analytically find an explicit one.

Example:

$$\frac{dy}{dx} - \sqrt{xy}\ln(x) = 0$$
$$\frac{dy}{dx} = \sqrt{x}\ln(x)\sqrt{y}$$
$$\frac{1}{\sqrt{y}}dy = \sqrt{x}\ln(x)dx, y \ne 0 \text{ (note that it is a solution still)}$$
$$\int{\frac{1}{\sqrt{y}} dy} = \int{\sqrt{x}\ln(x)dx}$$
$$2\sqrt{y} = \frac{2}{9}\sqrt{x^3}(3\ln(x) - 2) + C$$
$$\sqrt{y} = \frac{1}{9}\sqrt{x^3}(3\ln(x) - 2) + C$$
$$y(x) = \left(\frac{1}{9}\sqrt{x^3}(3\ln(x) - 2) + C\right)^2 $$
$$\Downarrow$$
$$y(x) = \left(\frac{1}{9}\sqrt{x^3}(3\ln(x) - 2) + C\right)^2 \text{ or } y(x) = 0$$

# Exact Differential Equations
These are differential equations of the form
$$\frac{\partial \psi}{\partial x} + \frac{\partial \psi}{\partial y}\frac{dy}{dx} = 0$$
for some function $\psi(x, y)$ such that $\psi(x, y) = c$ implicitly defines $y = \phi(x)$ as a differentiable function of $x$. Equations of this type can be rewritten as
$$\frac{d}{dx}\psi(x, \phi(x)) = 0$$

## Identifying Exact Differential Equations
Let the functions $M$, $N$, $M_y$, and $N_x$, where the subscripts denote the partial derivative with respect to the relative variable, be continuous in the region $R: \alpha \lt x \lt \beta, \gamma \lt y \lt \delta$. Then the equation
$$M(x, y) + N(x, y)\frac{dy}{dx} = 0$$
is an exact differential equation in $R$ if and only if
$$M_y(x, y) = N_x(x, y)$$
That is, there exists a function $\psi(x, y)$ such that
$$\psi_x(x, y) = M(x, y) \text{ and } \psi_y(x, y) = N(x, y)$$
So, in general
$$M_y(x, y) = N_x(x, y)\\\iff
\begin{cases}\\
\exists \psi(x, y)\\
\psi_x(x, y) = M(x, y)\\
\psi_y(x, y) = N(x, y)
\end{cases}$$

### Proof
The proof has two parts.

First, suppose that there is a function $\psi(x, y)$ such that
$$\psi_x(x, y) = M(x, y) \text{ and } \psi_y(x, y) = N(x, y)$$
It then follows that
$$M_y(x, y) = \psi_{xy}(x, y) \text{ and } N_x(x, y) = \psi_{yx}(x, y)$$

Since $M_y$ and $N_x$ are continuous, then $\psi_{xy}$ and $\psi_{yx}$ are also continuous which guarantees their equality.

#### Solving Exact Differential Equations
The second part of the above theorem also gives us the solution to the equation since it involves the construction of $\psi$. 
Suppose that
$$M_y(x, y) = N_x(x, y)$$ 
and let there be a function $\psi(x, y)$ for which
$$\psi_x(x, y) = M(x, y) \text{ and } \psi_y(x, y) = N(x, y)$$

Begin by integrating the first equation with respect to $x$.
$$\frac{\partial \psi}{\partial x}(x, y) = M(x, y)$$
$$\Downarrow$$
$$\psi(x, y) = \int{M(x, y) dx} + h(y)$$
$$\psi(x, y) = Q(x, y) + h(y)$$
Where $Q(x, y)$ is any differentiable function such that $Q_x = M$

The function $h(y)$ here plays the role of an arbitrary constant, but instead of just a constant, it is function of $y$, since we $M$ is a function of both $x$ and $y$ and we are only integrating with respect to $x$.

Now we must show that it is always possible to find an $h(y)$ such that $\psi_y = N$.
$$\psi(x, y) = Q(x, y) + h(y)$$
Differentiate both sides with respect to $y$:
$$\frac{\partial \psi}{\partial y}(x, y) = \frac{\partial Q}{\partial y}(x, y) + h'(y)$$
Set this result equal to $N$ and solve for $h'(y)$
$$\frac{\partial Q}{\partial y}(x, y) + h'(y) = N(x, y)$$
$$h'(y) = N(x, y) - \frac{\partial Q}{\partial y}(x, y)$$
In order to determine $h(y)$ from this equation, the right-hand side must be a function of $y$ only. This can be proven by showing that its derivative with respect to $x$ is zero.
Differentiating the right-hand side with respect ot $x$, we obtain
$$\frac{\partial N}{\partial x}(x, y) - \frac{\partial}{\partial x}\frac{\partial Q}{\partial y}(x, y)$$
$$\Downarrow$$
$$\frac{\partial N}{\partial x}(x, y) - \frac{\partial}{\partial y}\frac{\partial Q}{\partial x}(x, y)$$
Since $Q_x = M$,
$$\frac{\partial N}{\partial x}(x, y) - \frac{\partial M}{\partial y}(x, y)$$
Now, this is equal to $0$ based on our initial supposition that $M_y(x, y) = N_x(x, y)$.

Therefore,
$$h'(y) = N(x, y) - \frac{\partial Q}{\partial y}(x, y)$$
$$h(y) = \int{N(x, y) dy} - Q(x, y)$$
$$\Downarrow$$
$$h(y) = \int{N(x, y) dy} - \int{M(x, y) dx} + C$$
