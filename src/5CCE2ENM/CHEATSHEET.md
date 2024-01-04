# Table of Contents
<!-- toc -->
----

# Vectors Algebra
## Addition Properties
- Associativity: $\vec{a} + (\vec{b} + \vec{c}) = (\vec{a} + \vec{b}) + \vec{c}$
- Commutativity: $\vec{a} + \vec{b} = \vec{b } + \vec{a}$
- Additive Inverse: $\vec{a } + (- \vec{a}) = 0$

## Multiplication Properties
- Associativity: $k(t \vec{a}) = (kt) \vec{a}$
- Distributivity over vector addition: $k(\vec{a} + \vec{b }) = k \vec{a} + k \vec{b}$
- Distributivity over scalar addition: $(k+t) \vec{a} = k \vec{a} + t \vec{a}$

## Scalar Product
$$\vec{A} \cdot \vec{B} = \begin{bmatrix}a_1 \\ a_2 \\a_3\end{bmatrix} \cdot \begin{bmatrix}b_1 \\ b_2 \\b_3\end{bmatrix} = a_1b_1 + a_2b_2 + a_3b_3$$

Also it have the equivalent form
$$\vec{A} \cdot \vec{B} = ||\vec{A}|| \ ||\vec{B}|| \cos(\theta)$$

## Vector/Cross Product
$$\vec{A} \times \vec{B} = \begin{bmatrix}\vec{i} & \vec{j} &\vec{k}\\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3\end{bmatrix}$$

Also it have the equivalent form
$$\vec{A} \times \vec{B} = ||\vec{A}||\ ||\vec{B}|| \sin(\theta)$$

### Area of the Parallelogram
$||\vec{A} \times \vec{B}||$ is equal to the area of the parallelogram spaned by $\vec{A}, \vec{B}$

## Matrix Multiplication
Matrix 就是长和宽不相等的vector

简单来说就是横着和竖着的dot product(The dot product of rows and columns)

![](./assets/imgs/cheat-matrixmultiplication.png)

# Vector Calculus
## Gradient

## Divergence

**THEOREM** The divergence of a curl is always 0.

## Curl
**THEOREM** Not conservative means the curl of $\vec{F} \neq 0$ 

## Laplacian

# Path Integration
## Parametrize a Path

## Velocity / Tangent Vector
Let $\gamma : [a,b] \to \R^3$ be a parametrized path. Then the **tangent* to $\gamma$ at time $t$ is given by the **velocity vector**
$$r'(t) = \frac{dx }{dt }\vec{i} + \frac{dy }{dt } \vec{j} + \frac{dz }{dt } \vec{k}$$

The length $||r'(t)||$ is the rate at which the path is traversed

Unit tangent vector is simply $\vec{T} = \frac{\gamma ' (t)}{||\gamma'(t)||}$

## Path Integration over Scalar Fields
Let $f: \R^3 \to \R$ be a continuous scalar field on $\R^3$, and let $\gamma: [a,b] \to \R^3$ be a differentiable path in $R^3$

The path integral of $f$ along the path $\gamma$ is given by

$$\int_{\gamma }^{}fds = \int_{a }^{b }f(\gamma(t)) ||\frac{d \gamma }{dt}||dt = \int_{a }^{b }f(\gamma(t))||\gamma '(t)||dt$$

The $s$ denotes displacement, not a separate variable

## Path Integration over Vector Field
Let $\vec{F} \R^3 \to \R^3$ be a continuous vector field on $\R^3$, and let $\gamma:[a,b] \to \R^3$ be a piecewise differentiable path in $R^3$. The path integral of $\vec{F}$ along the path $\gamma$ is given by
$$\int_{\gamma}^{}F \cdot d \vec{s} = \int_{a }^{b }\vec{F}(\gamma(t))\cdot \vec{T}(t)||\gamma'(t)||dt = \int_{a}^{b} \vec{F}(\gamma(t)) \cdot \gamma '(t)dt$$

where
$$\vec{T}(t) = \frac{\gamma'(t) }{||\gamma'(t)||}$$

is the unit vector tangent to the path $\gamma$ at time $t \in [a,b]$

## Length of an Arc
Let $C \subseteq \R^3$ be a piecewise differentiable curve, then the length of $C$ is given by the path integral
$$\int_{C }^{}1ds = \int_{a }^{b }||\gamma '(t)|| dt$$

where $\gamma:[a,b] \to \R^3$ is a simple path that parametrized $C$.

## Simple Path/Curve
Path/Curve is simple if it does not intersect itself, except possibly at its endpoints.

# Area and Volume Integration
## Simple Region
### X-Simple Region
A region is said to be x-simple if it can be described as a set of points $(x,y)$ where $x$ ranges between two functions of $y$
$$a(y) \leq x \leq b(y)$$

And $y$ ranges between two constants $c \leq y \leq d$, or each $y$ is in the interval of $[c,d]$
### Y-Simple Region
Its the same shit, only change x to y, y to x.

### Simple Region
If a region is both x-simple and y-simple, its a 很他妈fuckin simple region.

## Double Integration
Let $f:\R^2 \to \R$ be a continuous function and let $\R = [a,b] \times [c,d]$ be a rectangular region of the xy-plane

Then

$$\iint_R f(x,y)dA = \int_{a }^{b }[\int_{c }^{d }f(x,y)dy]dx = \int_{c }^{d }[\int_{a }^{b }f(x,y)dx]dy$$

---

Let $f:\R^2 \to \R$ be a continuous function.

(i) If $R \subseteq \R^2$ be a y-simple region bounded above and below by $\phi^-, \phi^+:[a,b] \to \R$, then
$$\iint_R f(x,y) dA = \int_{a }^{b }[\int_{\phi^-(x) }^{\phi^+(x)}f(x,y)dy]dx$$

(i) If $R \subseteq \R^2$ be a x-simple region bounded left and right by $\psi^-, \psi^+:[c, d] \to \R$, then
$$\iint_R f(x,y) dA = \int_{c }^{d }[\int_{\psi^-(y) }^{\psi^+(y)}f(x,y)dx]dy$$

## Triple Integration

Let $f:\R^3 \to \R$ be a continuous function on $\R^3$ and let $W \subseteq \R^3$ be a region of space in $\R^3$. Then the triple integral of f over the region $W$ is denoted
$$\iiint_W f(x,y,,z)dV = \textrm{The mass of the region W whose density at }(x,y,z)\textrm{ is }f(x,y,z)$$

The dV indicates that we are integrating with respect to the volume of $W$


# Surface Integration
## Tangent Vectors
Let $\Phi: D \to \R^3$ be a parametrized surface, for some $D \subseteq \R^2$, the tangent vectors to the surface are given by the partial derivatives of $\Phi$ with respect to $u$ and $v$

$$\vec{T}_u = \frac{\partial x }{\partial u }\vec{i }+ \frac{\partial y }{\partial u}\vec{j} + \frac{\partial z}{\partial u}\vec{k}$$

and

$$\vec{T}_v = \frac{\partial x }{\partial v }\vec{i }+ \frac{\partial y }{\partial v}\vec{j} + \frac{\partial z}{\partial v}\vec{k}$$

Any linear combination of $\vec{T_u} and \vec{T_v}$ will also be a tangent vector to the surface
## Normal Vector
A normal vector to the surface is any vector that is perpendicular to the tangent vectors $\vec{T_u}$ and $\vec{T_v}$

The most obvious choice is 
$$\vec{N = \vec{T_u}}\times \vec{T_v}$$

The cross product is perpendicular to both vector

## Surface Integration over Scalar Fields
Let $f:\R^3 \to \R$ be a continuous scalar field on $\R^3$ and let $\Phi:D\to\R^3$ be a regular surface in $\R^3$

The surface integral of $f$ across the surface $\Phi$ is given by

$$\iint_\Phi f(x,y,z)dS = \iint_D f(\Phi(u,v)) ||\vec{T_u}\times \vec{T_v}||du\ dv$$

## Surface Integration over Vector Fields
Let $\vec{F}:\R^3 \to \R^3$ be a continuous vector field on $\R^3$, and let $\\Phi: D \to \R^3$ be a regular parametrized surface in $\R^3$, then the surface integral of $\vec{F}$ across the surface $\Phi$ is given by

$$\iint_\Phi \vec{F}(x,y,z)\cdot d \vec{S} = \iint_D (\vec{F}\cdot \hat{N})||\vec{T_u}\times \vec{T_v}||du\ dv= \iint_D \vec{F}\cdot (\vec{T_u} \times \vec{T_v})du\ dv$$

Where $\hat{N} = \frac{\vec{T_u}\times \vec{T_v}}{||\vec{T_u} \times \vec{T_v}||}$ is a unit vector to the surface of $\Phi$

We can further simplify the surface integration formula by cancelling the denominator of $||\vec{T_u}\times \vec{T_v}||$ from $\hat{N}$ (Since the dot product is linear).

Another name for the surface integral $\iint_\Phi \vec{F}\cdot d \vec{S}$ is the flux of $\vec{F}$ across the surface $\Phi$

## Surface Area of a Parametrized Surface
Let $\Phi: D \to \R^3$ be a regular parametrized surface. Then the surface area of $\Phi$ is given by the integral
$$\iint_\Phi 1dS = \iint_D ||\vec{T_u} \times \vec{T_v}|| du\ dv$$

## Green's Theorem

