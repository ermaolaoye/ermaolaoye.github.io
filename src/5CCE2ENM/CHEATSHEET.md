# Table of Contents
<!-- toc -->
----

# Directional Derivatives
Directional Derivatives in 2D in the direction of a unit vector $\vec{u} = a \vec{i} + b \vec{j}$, ($||\vec{u}|| = 1$, i.e. $\sqrt{a^2+b^2} = 1$) is given by:

$$D_{\vec{u}}f(x,y) = a \frac{\partial f(x,y)}{\partial x} + b \frac{\partial f(x,y)}{\partial y}$$
## Directional Derivatives in 3 Dimensions
Directional Derivatives in 2D in the direction of a unit vector $\vec{u} = a \vec{i} + b \vec{j} + c \vec{k}$, ($||\vec{u}|| = 1$, i.e. $\sqrt{a^2+b^2+c^2} = 1$) is given by:

$$D_{\vec{u}}f(x,y,z) = a \frac{\partial f(x,y,z)}{\partial x} + b \frac{\partial f(x,y,z)}{\partial y} + c\frac{\partial f(x,y,z)}{\partial z}$$

## Partial Derivatives
By choosing $\vec{u } \in \R^3$ to be one of the standard basis vectors, we can isolate the rate of change of $f$ as we vary $x,y,z$ respectively.

These are the **partial derivatives** with respect to $x,y,z$
$$\frac{\partial f }{\partial x}=D_{\vec{i}}f(\vec{x}),\frac{\partial f }{\partial y}=D_{\vec{j}}f(\vec{y}),\frac{\partial f }{\partial z}=D_{\vec{k}}f(\vec{z}),$$



# Vectors Algebra
## Linear Independent
如果他给了你三个式子
$$f(x) = x_1 + x_2 + x_3$$
$$g(y) = y_1 + y_2 + y_3$$
$$h(z) = z_1 + z_2 + z_3$$

如果他想让你证明三个式子是linearly independent的，只需要证明他们作为column的matrix的determinant不等于0就行

$$det \begin{bmatrix}x_1 & y_1 & z_1 \\ x_2 & y_2 & z_2 \\ x_3 & y_3 & z_3\end{bmatrix} \neq 0$$
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
Let $f: \R^3 \to \R$ be a scalar field on $\R^3$. The gradient of $f$ is the vector field given by
$$\nabla f = \frac{\partial f}{\partial x} \vec{i } + \frac{\partial f}{\partial y} \vec{j } + \frac{\partial f}{\partial z} \vec{k }$$

Let $f:\R^3 \to \R$ be a real-valued function. Then the directional derivative of $f$ with respect to $\vec{u}$ is given by
$$D_{\vec{u}}f(\vec{x }) = \nabla f(x) \cdot \vec{u}$$
for any unit vector $\vec{u}\in \R^3$


## Divergence
Let $\vec{F} = P \vec{i} + Q \vec{j} + R \vec{k}$ be a vector field on $\R^3$. The divergence of $\vec{F}$ is the scalar field given by
$$\textrm{div}\vec{F} = \nabla \cdot \vec{F} = (\partial_x \vec{i} + \partial_y \vec{j}+ \partial_z \vec{k}) \cdot (P \vec{i} + Q \vec{j} + R \vec{k})$$
$$= \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z} $$

A vector field is said to be incompressible if its divergence is zero at every point in $\R^3$
$$\nabla \cdot \vec{F}(x,y,z) = 0$$
for all $(x,y,z) \in \R^3$

----
**THEOREM** The divergence of a curl is always 0.

## Curl
Let $\vec{F } = P \vec{i } + Q \vec{j } + R \vec{k}$ be a vector field on $\R^3$ the curl of $\vec{F}$ is another vector field given by

$$\textrm{curl} \vec{F} = \nabla \times \vec{F} = \begin{vmatrix}
\vec{i} &\vec{j} &\vec{k}\\
\partial_x &\partial_y &\partial_z\\
P &Q &R
\end{vmatrix}$$

$$ = (\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z})\vec{i}-(\frac{\partial R}{\partial x} - \frac{\partial P}{\partial z})\vec{i})+(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y})\vec{i}$$

The curl can be interpreted as **a measure of the angular rotation of a small rigid body sitting in the field at a given point**

The axis of rotation is the direction of $\nabla \times \vec{F}$ and the angular velocity is $\frac{1 }{2 }||\nabla \times \vec{F}||$

A vector field is said to be **irrotational** if its curl is the zero vector at every point in $\R^3$ i.e.
$$\nabla \times \vec{F}(x,y,z) = \vec{0}$$

for all $(x,y,z) \in \R^3$

---
**THEOREM** Not conservative means the curl of $\vec{F} \neq 0$ 

If mathvecF: \R^2 \to \R^2 is a conservative vector field, the curl of a conservative vector field is 0.

## Laplacian
Let $f:\R^3 \to \R$be a scalar field on $\R^3$. The Laplacian of $f$ is the scalar field given by the sum of the second partial derivatives
$$\nabla^2 f = \nabla \cdot (\nabla f) = \frac{\partial^2 f }{\partial x^2 } + \frac{\partial^2 f }{\partial y^2} + \frac{\partial^2 f }{\partial z^2}$$

i.e. It is the divergence of the gradient of $f$


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
$$\vec{N} = \vec{T_u}\times \vec{T_v}$$

The cross product is perpendicular to both vector

## Surface Integration over Scalar Fields
Let $f:\R^3 \to \R$ be a continuous scalar field on $\R^3$ and let $\Phi:D\to\R^3$ be a regular surface in $\R^3$

The surface integral of $f$ across the surface $\Phi$ is given by

$$\iint_\Phi f(x,y,z)dS = \iint_D f(\Phi(u,v)) ||\vec{T_u}\times \vec{T_v}||du\ dv$$

## Surface Integration over Vector Fields
Let $\vec{F}:\R^3 \to \R^3$ be a continuous vector field on $\R^3$, and let $\Phi: D \to \R^3$ be a regular parametrized surface in $\R^3$, then the surface integral of $\vec{F}$ across the surface $\Phi$ is given by

$$\iint_\Phi \vec{F}(x,y,z)\cdot d \vec{S} = \iint_D (\vec{F}\cdot \hat{N})||\vec{T_u}\times \vec{T_v}||du\ dv= \iint_D \vec{F}\cdot (\vec{T_u} \times \vec{T_v})du\ dv$$

Where $\hat{N} = \frac{\vec{T_u}\times \vec{T_v}}{||\vec{T_u} \times \vec{T_v}||}$ is a unit vector to the surface of $\Phi$

We can further simplify the surface integration formula by cancelling the denominator of $||\vec{T_u}\times \vec{T_v}||$ from $\hat{N}$ (Since the dot product is linear).

Another name for the surface integral $\iint_\Phi \vec{F}\cdot d \vec{S}$ is the flux of $\vec{F}$ across the surface $\Phi$

## Surface Area of a Parametrized Surface
Let $\Phi: D \to \R^3$ be a regular parametrized surface. Then the surface area of $\Phi$ is given by the integral
$$\iint_\Phi 1dS = \iint_D ||\vec{T_u} \times \vec{T_v}|| du\ dv$$

# Integration Theorem
凡是和Simple Region with boundary $\partial D$ 相关的题目都是这个section的

这堆东西和前面挺不相关的
## Path Orientation
Path Orientation refer to the direction in which the path is traversed.

Let $D \subseteq \R^2$ be a simple region with boundary $\partial D$

Then a closed path parametrizing $\partial D$ can either have:
![](./assets/imgs/4-pathorientation.png)


## Green's Theorem
Let $D \subseteq \R^2$ be a simple region of $\R^2$, and let $\partial D$ be its positively oriented boundary. Suppose that $P, Q : D \to \R$ are differentiable real-valued functinos. Then we have that
$$\oint_{\partial D} P dx + Q dy = \iint_D(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y})dx\ dy$$

Green's Theorem can only be used for a two-dimensional vector field $\vec{F} = P \vec{i} + Q \vec{j}$

----
**Vector Form** 
$$\oint_{\partial D}\vec{F } \cdot d\vec{S} = \iint_D (\nabla \times \vec{F})\cdot \vec{k}dA$$

If $\vec{F}: \R^2 \to \R^2$ is a conservative vector field, the curl of a conservative vector field is 0. i.e. $\oint_{\partial D} \vec{F} \cdot d \vec{S} = 0$

----
**Proof**

**Step 1)** Show that
$$\oint_{\partial D} Pdx = -\iint_D \frac{\partial P}{\partial y}dx\ dy$$
$$\oint_{\partial D} Qdy = \iint_D \frac{\partial Q}{\partial x}dx\ dy$$

**Step 2)** Add them together 这他妈不是废话吗

### Green's Theorem on y-simple region
Let $D \subseteq \R^2$ be a y-simple region of $\R^2$ whose boundary is $\partial D$, and let $P: D \to \R$ be a differentiable real-valued function. Then we have that
$$\oint_{\partial D}P dx = - \int\int_D \frac{\partial P}{\partial y }dx\ dy$$

--- 
**Proof** 

**Step 1)** Since $D$ is y-simple, we have that
$$D = \{(x,y)\in \R^2: a \leq x \leq b \textrm{ and } f(x)\leq y \leq g(x)\}$$

**Step 2)** Evaluate the double integral
$$\iint_D \frac{\partial P}{\partial y}(x,y)dx\ dy = \int_{a}^{b}[\int_{f(x)}^{g(x)}\frac{\partial P}{\partial y}(x,y)dy]dx$$

$$= \int_{a}^{b}[P(x,y)]^{g(x)}_{f(x)}dx$$

$$= \int_{a}^{b}[P(x,g(x))-P(x,f(x))]dx$$
$$= \int_{a}^{b}P(x,g(x))dx - \int_{a}^{b}P(x,f(x))dx$$

_FINISHED PROOFING LHS_

**Step 3)** Evaluate the path integral in four pieces
$$\oint_{\partial D}Pdx = \int_{A}^{}P dx + \int_{C}^{}Pdx + \int_{B}^{}P dx + \int_{D}^{}Px$$

![](./assets/imgs/cheatsheet-greenproof.png)

**Step 4)** Parametrize Path

Path A can be parametrized as $A^+(t) = t \vec{i} + f(t) \vec{j}$

$$\int_{A^+}^{}P(x,y)dx = \int_{a}^{b}P(t,f(t)) \frac{dx}{dt}dt = \int_{a}^{b}P(t,f(t))dt$$

Path B can be parametrized as $B^-(t) = t \vec{i} + g(t) \vec{j}$

$$\int_{B^-}^{}P(x,y)dx = \int_{a}^{b}P(t,g(t)) \frac{dx}{dt}dt = \int_{a}^{b}P(t,g(t))dt$$

> Note that the direction of $B$ along $\partial D$ is reversed

Path C can be parametrized as $C^+(t) = b \vec{i} + t \vec{j}$

$$\int_{C^+}^{}P(x,y)dx = \int_{f(b)}^{g(b)}P(b,t) \frac{dx}{dt}dt = 0$$

> Since the x component of $C$ is constant, so $\frac{dx}{dt} = 0$

Path D can be parametrized as $D^-(t) = a \vec{i} + t\vec{j}$

$$\int_{D^-}^{}P(x,y)dx = \int_{f(a)}^{g(a)}P(a,t) \frac{dx}{dt }dt = 0$$

> Since the x component of D is also constant, so $\frac{dx}{dt} = 0$

**Step 5)** Hence,

$$\oint_{\partial D}Pdx = \int_{A}^{}P dx + \int_{C}^{}Pdx + \int_{B}^{}P dx + \int_{D}^{}Px$$

$$ = \int_{a }^{b } P(t,f(t))dt - \int_{a}^{b}P(t,g(t))dt$$

Which is the same fuckin thing LHS = RHS

### Green's Theorem on x-simple region

Let $D \subseteq \R^2$ be a x-simple region of $\R^2$ whose boundary is $\partial D$, and let $Q: D \to \R$ be a differentiable real-valued function. Then we have that
$$\oint_{\partial D}Q dy =  \iint_D \frac{\partial Q}{\partial x }dx\ dy$$

The Proof of this is similar as LHS, but remember its positive.

## Gauss' Divergence Theorem
Let $\vec{F}$ be a vector field on $\R^3$, and let $W \subseteq \R^3$ be a simple region of $\R^3$, with boundary $\partial W$. Then
$$\oiint_{\partial W} \vec{F}\cdot d\vec{S} = \iiint_W(\nabla \cdot \vec{F})dV$$

**Lemma**

Let $R:\R^3 \to \R$ be a real valued function, and let $W \subseteq \R^3$ be a z-simple region of $\R^3$, then
$$\iiint_W \frac{\partial R}{\partial z}dV = \iint_{\partial W}R \vec{k}\cdot d \vec{S}$$

----
**PROOF**

Just like before, we divide the problem into separate components

也就是证明这三个然后加起来

$$\oiint_{\partial W} P \vec{i} \cdot d \vec{S} = \iiint_W \frac{\partial P}{\partial x}dV$$


$$\oiint_{\partial W} Q \vec{j} \cdot d \vec{S} = \iiint_W \frac{\partial Q}{\partial y}dV$$


$$\oiint_{\partial W} R \vec{k} \cdot d \vec{S} = \iiint_W \frac{\partial R}{\partial z}dV$$

证明最下面那个:

**Step 1)** Since $W$ is z-simple, there is some region $D \subseteq \R^2$
$$W = \{(x,y,z) \in \R^3 : (x,y) \in D \textrm{ and }f(x,y)\leq z \leq g(x,y)\}$$

where $f,g: D \to \R$ is the lower and upper bound on $z$

**Step 2)** Evaluate the triple integral
$$\iint_W \frac{\partial R}{\partial z} dV = \iint_D [\int_{f(x,y)}^{g(x,y)} \frac{\partial R}{\partial z}dz]dA$$
$$= \iint_D [R(x,y,z)]^{g(x,y)}_{f(x,y)}dA$$

$$= \iint_DR(x,y,g(x,y))dA - \iint_DR(x,y,f(x,y))dA$$

_Finish RHS Proof_

**Step 3)** Divide the surface $\partial W$ into three pieces $S_1, S_2, S_3$

![](./assets/imgs/cheetsheet-greendiv.png)

$$\oiint_{\partial W} R \vec{k} \cdot d \vec{S} = \iint_{S_1}^{}R \vec{k}\cdot d \vec{S} + \iint_{S_2}R \vec{k}\cdot d \vec{S} - \iint_{S_3}R \vec{k} \cdot d \vec{S}$$
> $S_3$ 是负的因为他的方向是反的，我也不知道为什么他他妈是反的，我也他妈不在乎他他妈为什么是反的，但他他妈的就是反的

**Step 4)** Parametrize

Parametrize $S_1$ as $S_1(u,v) = u \vec{i} + v \vec{j} + g(u,v) \vec{k}$

So
$$\vec{T_u} = \vec{i} + \frac{\partial g}{\partial u}\vec{k}$$

$$\vec{T_v} = \vec{j} + \frac{\partial g}{\partial v}\vec{k}$$

$$\vec{T_u}\times \vec{T_v} = - \frac{\partial g}{\partial u} \vec{i} - \frac{\partial g}{\partial v}\vec{j} + \vec{k}$$

> Inparticular, we note that $\vec{k} \cdot (\vec{T_u} \times \vec{T_v}) = 1$

Hence

$$\iint_{S_1} R \vec{k} \cdot d \vec{S} = \iint_D R(S_1(x,y))\vec{k}\cdot (\vec{T_u}\times \vec{T_v})dA$$

$$\iint_D R(u,v,g(u,v))dA$$

Similar, the surface integral of $S_3$
$$\iint_{S_3} = R \vec{k}\cdot d \vec{S} = \iint_D R(u,v,f(u,v))dA$$

BUT FOR $S_2$, 他是个臭傻逼

Parametrize $S_2$ as $S_2(u,v) = x(u)\vec{i} + y(u)\vec{j} + v \vec{k}$

And then you will find out
$$\vec{T_u}\times \vec{T_v} = x'(u)\vec{i} + y'(u)\vec{j} + 0 \vec{k}$$

Hence that $\vec{k}\cdot (\vec{T_u}\times \vec{T_v}) = 0$

Hence
$$\iint_{S_2} R \vec{k}\cdot d \vec{S} = 0$$

Hence the whole LHS will be 
$$\iint_D R(x,y,g(x,y))dA - \iint_D R(x,y,f(x,y))dA$$

## Stoke's Theorem
Let $\vec{F}$ be a vector field on $\R^3$, and let $\Phi: D \to \R^3$ be a parametrized surface with boundary $\partial \Phi$, where $D \subseteq \R^2$ is a region to which Green's Theorem applies. Then
$$\oint_{\partial\Phi} \vec{F}\cdot d \vec{s} = \iint_\Phi(\nabla \times \vec{F})\cdot d \vec{S}$$

----
**Proof** 

**Step 1)** Consider the following special case
$$\Phi(u,v) = u \vec{i} + v \vec{j} + f(u,v) \vec{k}$$

**Step 2)** Evaluate the RHS double integral
$$\vec{T_u} = \vec{j} + \frac{\partial f}{\partial u} \vec{k}$$

$$\vec{T_v} = \vec{j} + \frac{\partial f }{\partial v }\vec{k}$$

Cross product is
$$\vec{T_u}\times \vec{T_v} = - \frac{\partial f }{\partial u }\vec{i} - \frac{\partial f }{\partial v }\vec{j} + \vec{k}$$

$$(\nabla\times \vec{F})\cdot (\vec{T_u}\times \vec{T_v}) = - (\frac{\partial R }{\partial y } - \frac{\partial Q }{\partial z} ) \frac{\partial f }{\partial u } + \dots$$

反正是一个很长的傻逼东西

**Step 3)** Evaluate LHS

$$\gamma(t) = u(t) \vec{i} + v(t) \vec{j} + f(u(t),v(t))\vec{k}$$

So that
$$\gamma'(t) = \frac{du }{dt }\vec{i} + \frac{dv }{dt }\vec{j} + (\frac{\partial f }{\partial u } \frac{du }{dt } + \frac{\partial f }{\partial v }\frac{dv }{dt })\vec{k}$$

$$\vec{F }(\gamma(t)) \cdot \gamma'(t) = (P + R \frac{\partial f }{\partial u })\frac{du }{dt } + (Q + R \frac{\partial f }{\partial v})\frac{dv }{dt}$$

Integrate them we get
$$\oint_{\partial \Phi}^{} \vec{F} \cdot d \vec{S} = \oint_{\partial D}(P + R \frac{\partial f }{\partial u })du + (Q + R \frac{\partial f }{\partial v})dv$$

把两个括号各当成单独的一个完整的term，然后用Green's Theorem

$$= \oint_{\partial D } \frac{\partial }{\partial u }(Q + R \frac{\partial f }{\partial v }) - \frac{\partial }{\partial v}(P + R \frac{\partial f }{\partial u })dA$$

这个东西接下来会非常的屎，我们一个一个来

首先 $\vec{F} = P(x,y,z)\vec{i} + Q(x,y,z)\vec{j}+ R(x,y,z) \vec{k}$ 而且 $z = f(x,y)$

And because of $u=x, v=y$,Hence

$$\frac{\partial Q}{\partial u} = \frac{\partial Q }{\partial x} + \frac{\partial Q }{\partial z} \frac{\partial f}{\partial u}$$

The second term, $\frac{\partial }{\partial u }(R \frac{\partial f }{\partial v})$ 需要用到product rule

$$ = \frac{\partial R }{\partial u } \frac{\partial f }{\partial v } + R \frac{\partial f^2}{\partial u \partial v}$$

然后这个的第一个term $\frac{\partial R }{\partial u}$又可以按照前面的那个来integrate

$$\frac{\partial R }{\partial u }= \frac{\partial R }{\partial x } + \frac{\partial R }{\partial z }\frac{\partial f }{\partial u }$$

全部结合在一起就会变成

$$\frac{\partial }{\partial u }(Q + R \frac{\partial f }{\partial v }) = (\frac{\partial Q }{\partial x } + \frac{\partial Q }{\partial z }\frac{\partial f }{\partial u}) + (\frac{\partial R }{\partial x } + \frac{\partial R }{\partial z } \frac{\partial f }{\partial u}) \frac{\partial f }{\partial v} + R \frac{\partial^2 f }{\partial u \partial v}$$

另一个term则是

$$\frac{\partial }{\partial v }(Q + R \frac{\partial f }{\partial v }) = (\frac{\partial Q }{\partial y } + \frac{\partial Q }{\partial z }\frac{\partial f }{\partial v}) + (\frac{\partial R }{\partial y } + \frac{\partial R }{\partial z } \frac{\partial f }{\partial v}) \frac{\partial f }{\partial u} + R \frac{\partial^2 f }{\partial u \partial v}$$

这俩按照之前提到的关系结合一下就成为了 LHS = RHS

