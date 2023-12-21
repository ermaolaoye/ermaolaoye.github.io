# Table of Contents
<!-- toc -->
----

# Quadratic Funciton

$x = \frac{-b \pm \sqrt[]{b^2 - 4ac}}{2a}$


<a id="orga35c4ab"></a>

# Trignometry

$\sin^2(\theta) + \cos^2(\theta)=1$

$\tan (\theta) = \frac{\sin(\theta)}{\cos(\theta)}$

$\sin(x \pm y) = \sin x\cos y \pm \cos x \sin y$

$\cos(x\pm y) = \cos x\cos y \mp \sin x \sin y$

$\tan(x\pm y) = \frac{\tan x \pm \tan y}{1\mp \tan x \tan y}$

$\frac{\sin \alpha}{a} = \frac{\sin \beta}{b} = \frac{\sin \gamma}{c}$


<a id="org30d81ce"></a>

# Vectors


<a id="orgda39798"></a>

## Scalar Product

$\vec{a} \cdot \vec{b} = |\vec{a}||\vec{b}|\cos\theta$


<a id="orgde86af3"></a>

## Vector Product

$\boldsymbol{a} \times \boldsymbol{b} = |\boldsymbol{a}||\boldsymbol{b}|\sin \theta \hat{n}$

$$ \boldsymbol{a} \times \boldsymbol{b} = \begin{vmatrix}
\boldsymbol{i} &\boldsymbol{j} &\boldsymbol{k} \\
a_1 &a_2 &a_3 \\
b_1 &b_2 &b_3 \\
\end{vmatrix} = \boldsymbol{i} \begin{vmatrix}
a_2 &a_3 \\
b_2 &b_3
\end{vmatrix} - \boldsymbol{j} \begin{vmatrix}
a_1 &a_3 \\
b_1 &b_3
\end{vmatrix} + \boldsymbol{k} \begin{vmatrix}
a_1 &a_2 \\
b_1 &b_2
\end{vmatrix}$$


<a id="orgca142aa"></a>

# Matrix


<a id="org68bd14d"></a>

## Matrix Multiplication
To mutiply a matrix by another matrix, we do dot product of rows and columns.

![](./assets/imgs/matrixmultiplication.png)

![](./assets/imgs/matrixmultiplication2.png)

## Inverse Matrix

$\boldsymbol{A}^{-1} = \frac{adj \boldsymbol{A}}{|\boldsymbol{A}|}$

$adj \boldsymbol{A} = \begin{bmatrix}
A_{11} &A_{12} &A_{13} \\
A_{21} &A_{22} &A_{23} \\
A_{31} &A_{32} &A_{33} \\
\end{bmatrix}^T$

$\textrm{cofactor} \boldsymbol{A}_{ij} = (-1)^{i+j} a_{ij}M_{ij}$

$det \boldsymbol{A} = | \boldsymbol{A} | = \sum_{j}^{}a_{ij}\boldsymbol{A}_{ij}$


<a id="orgea68c0b"></a>

## Skew-Symmetric Matrix

$\boldsymbol{A} = - \boldsymbol{A}^T$


<a id="org8fa50db"></a>

## Singular Matrix

$|\boldsymbol{A}| = 0$


<a id="orged1c5dd"></a>

## Eigen Value and Characteristic Equation

$\boldsymbol{AX} = \lambda \boldsymbol{X}$
$\lambda$ is the eigen value

How to solve
$(\boldsymbol{A} - \lambda \boldsymbol{I}) \boldsymbol{X} = 0$

This is the characteristic equation
$c(\lambda) = |\lambda I - \boldsymbol{A}| = 0$
The solution to this characteristic equation will be our eigen value
$c(\lambda) = 0$


<a id="org12828d9"></a>

# Limits


<a id="org560a670"></a>

## L'Hopital's Rule

If the limit $\lim \frac{f(x)}{g(x)}$ is of independent type $\frac{0}{0}$ or $\frac{+\infty}{-\infty}$, then

$\lim \frac{f(x)}{g(x)} = \lim \frac{f'(x)}{g'(x)}$

provided this last limit exists. Here, lim stands for $\lim_{x\to a}, \lim_{x\to a^{\pm}}, \lim_{x\to \pm \infty}$


<a id="org6d9d2e4"></a>

# Differentiation


<a id="org68beb4d"></a>

## Derivatives of basic functions

$\frac{d}{dx}[c] = 0\ \textrm{(c, constant)}$

$\frac{d}{dx}[x^n] = nx^{n-1}$

$\frac{d}{dx}[e^x] = e^x$

$\frac{d}{dx}[a^x] = a^x \ln a$

$\frac{d}{dx}[\ln |x|] = \frac{1}{x}$

$\frac{d}{dx}[\log _a |x|] = \frac{1}{x \ln a}$

$\frac{d}{dx}[\sin x] = \cos x$

$\frac{d}{dx}[\cos x] = -\sin x$

$\frac{d}{dx}[\tan x] = \sec ^2 x$

$\frac{d}{dx}[\cot x] = -\csc ^2 x$

$\frac{d}{dx}[\sec x] = \sec x \tan x$

$\frac{d}{dx}[\csc x] = -\csc x \cot x$

$\frac{d}{dx}[\sin ^ {-1} x] = \frac{1}{\sqrt[]{1-x^2}}$

$\frac{d}{dx}[\cos ^{-1} x] = - \frac{1}{\sqrt[]{1-x^2}}$

$\frac{d}{dx}[\tan ^{-1} x]= \frac{1}{1+x^2}$

$\frac{d}{dx}[\cot ^{-1} x] = - \frac{1}{1+x^2}$

$\frac{d}{dx}[\sec^{-1} x] = \frac{1}{x \sqrt[]{x^2-1}}$

$\frac{d}{dx}[\csc ^{-1}x] = - \frac{1}{x \sqrt[]{x^2 -1}}$


<a id="orgfc9195b"></a>

## Basic Rules


<a id="orge2462e4"></a>

### Product Rule

We already seen the sum rule

$\frac{d}{dx}[f(x)+g(x)] = \frac{d}{dx}[f(x)] + \frac{d}{dx}[g(x)]$

But the product rule does not work like this,

$\frac{d}{dx}[f(x)g(x)] \neq \frac{d}{dx}[f(x)] \frac{d}{dx}[g(x)]$

PRODUCT RULE, for function f and g

$\frac{d}{dx}[f(x)g(x)] = \frac{d}{dx}[f(x)]g(x) + f(x) \frac{d}{dx}[g(x)]$


<a id="org2c1cf60"></a>

### Quotient Rule

$\frac{d}{dx}[\frac{f(x)}{g(x)}] = \frac{g(x) \frac{d}{dx}[f(x)] - f(x) \frac{d}{dx}[g(x)]}{(g(x))^2}$


<a id="org39fb007"></a>

### Chain Rule

$\frac{d}{dx}[f(g(x))] = f'(g(x)) \times g'(x)$


<a id="org0eddf69"></a>

## Implicit Differentiation

Implicit differentiation basically means we implicitly consider y as a function of x, and use the chain rule to differentiate them.

METHOD OF IMPLICIT DIFFERENTIATION
Give an equation involving the variables x and y, the derivative of y is found using **implicit differentiation**

-   Apply $\frac{d}{dx}$ to both sides of the equation. (In the process of applying the derivative rules. $y'$ will appear, possibly more than once)
-   Solve for $y'$


<a id="orgecee019"></a>

## Logarithmic differentiation

LOGARITHMIC DIFFERENTIATION
Given an equation $y = y(x)$ expressing y explicitly as a function of x, the derivative $y'$ is found using **logarithmic differentiation** as follows:

-   Apply the natural logarithm ln to both sides of the equation and use laws of logarithms to simplify the right-hand side.
-   Find y' using implicit differentiation
-   Replace y with y(x)


<a id="orgbd2e3ad"></a>

# Integration


<a id="org8943331"></a>

## Basic Integrals

$\int_{}^{}k dx = kx + C,\ \textrm{(any number k)}$

$\int x^n dx = \frac{x^{n+1}}{n+1}+ C,\ (n \neq -1)$

$\int_{}^{} \frac{1}{x} dx = \ln|x| + C$

$\int e^x dx = e^x + C$

$\int a^x dx = \frac{a^x}{\ln a} + C,\ (a > 0, a \neq 1)$

$\int \sin x dx = -\cos x + C$

$\int \cos x dx = \sin x + C$

$\int \sec ^2 x dx = \tan x + C$

$\int \csc^2 x dx = - \cot x + C$

$\int \sec x \tan x dx = \sec x + C$

$\int \csc x \cot x dx = -\csc x + C$

$\int \tan x dx = \ln |\sec x| + C$

$\int \cot x dx = \ln |\sin x| +C$

$\int \sec x dx = \ln | \sec x + \tan x | + C$

$\int \csc x dx = -\ln |\csc x + \cot x | + C$

$\int \sinh x dx = \cosh x + C$

$\int \cosh x dx = \sinh x + C$

$\int \frac{1}{\sqrt{a^2 - x^2}} dx = \sin^{-1}(\frac{x}{a}) + C$

$\int \frac{1}{a^2 + x^2} dx =\frac{1}{a} \tan^{-1}(\frac{x}{a}) + C$

$\int \frac{1}{x \sqrt{x^2 - a^2}} dx =\frac{1}{a} \sec^{-1}|\frac{x}{a}| + C$

$\int \frac{1}{\sqrt{a^2 + x^2}} dx = \sinh^{-1}(\frac{x}{a}) + C,\ (a >0)$

$\int \frac{1}{\sqrt{x^2 - a^2}} dx = \cosh^{-1}(\frac{x}{a}) + C,\ (x > a > 0)$


<a id="org5603ce0"></a>

## Integration by Parts

$\int_{a}^{b} u(x)v'(x)dx = [u(x) v(x)]_a^b - \int_{a}^{b}v(x)u'(x)dx$


<a id="org9fe8bcd"></a>

# First Order Differential Equation

FORMAT Equation: $\frac{dy}{dx} + P(x)y = Q(x)$

Find v(x) $v(x) = e^{\int P(x)dx}$

$y = \frac{1}{v(x)}\int v(x)Q(x)dx$


<a id="org3f5c155"></a>

# Directional Derivative

$D_u f|_{\boldsymbol{u},p_0} = \nabla f|_{p_0} \cdot \boldsymbol{u}$

$\nabla f = \frac{\partial f}{\partial x}i + \frac{\partial f}{\partial y}j$


<a id="org2703020"></a>

## Properties: $D_uf = \nabla f \cdot u = |\nabla f||u| \cos (\theta)$

1.  The function f increases most rapidly when $\cos \theta = 1$ which means that $\theta = 0$ and **u** is the direction of $\nabla f$.
    That is, at each point P in its domain, f increases most rapidly in the direction of the graident vector $\nabla f$ at P.
    The derivative in this direction is
    $D_u f = |\nabla f| \cos (0)  = |\nabla f|$

2.  Similarly, f decreases most rapidly in the direction of $- \nabla f$.
    The derivative in this direction is $D_uf = |\nabla f| \cos (\pi) = - | \nabla f|$

3.  Any direction **u** orthogonal to a gradient $\nabla f \neq 0$ is a direction of zero change in f because $\theta$ then equals $\frac{\pi}{2}$ and
    $D_u f = |\nabla f| cos(\frac{\pi}{2}) = |\nabla f| \cdot 0 = 0$


<a id="orgbf23fd8"></a>

# Tangent Line to a Level Curve

$\frac{\partial f}{\partial x}|_{x_0,y_0} (x-x_0) + \frac{\partial f}{\partial y}|_{(x_0,y_0)}(y-y_0)=0$


<a id="org0db778e"></a>

# How to find maximum minimum

$f_x(a,b) = f_y(a,b) = 0$

Then do second derivative test

i. $f$ has a **local maximum** at $(a,b)$ if $f_{xx} < 0$ and $f_{xx}f_{yy} - f_{xy}^2 >0$ at $(a,b)$

ii. $f$ has a **local minimum** at $(a,b)$ if $f_{xx} > 0$ and $f_{xx}f_{yy} - f_{xy}^2 >0$ at $(a,b)$

iii. $f$ has a **saddle point** at $(a,b)$ if $f_{xx}f_{yy} - f_{xy}^2 < 0$ at $(a,b)$

iv. the test is inconclusive at $(a,b)$ if $f_{xx}f_{yy} - f_{xy}^2 = 0$ at $(a,b)$

In this case, we must find other way to determine the behavior of f at (a,b)


<a id="orgbb8754c"></a>

# Multiple Integral Find Volume

If $f(x,y)$ is continuous throughout the rectangular region $R: a\leq x \leq b, c\leq y\leq d$ then

$\int \int_{R}^{} f(x,y)dA = \int_{c}^{d} \int_{a}^{b}f(x,y)dxdy = \int_{a}^{b}\int_{c}^{d}f(x,y)dydx$


<a id="org4818175"></a>

# Multiple Integral Find Area

The **area** is closed, bounded plane region R is

$A = \int \int_{R}^{}dA$

