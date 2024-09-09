# Approximation

Approximations before the computation begin:

- Modelling: Physical features of the problem or system might be simplified or omitted(e.g. Friction, Viscosity, Air Resistance)
- Empirical Measurements: Laboratory instruments have finite precision.
- Previous Computations: Input data may have been produced by a previous computational step whose results were only approximate.

Approximations during computation:
- Truncation or discretization: Some features of a mathematical model might be simplified(Replacing derivatives by finite differences or using only a finite number of terms in an infinite series)
- Rounding: Computer and calculator usually have finite amount of precision.

> Example: The surface area of earth might be computed using the formula
> $$A = 4\pi r^2$$
> For the surface area of a sphere of radius $r$. The approximations includes:
> - The earth is modeled as a sphere.
> - The value for the radius is a combination of empirical measurements and previous computation.
> - The value for $\pi$ is given by an infinite limiting process, which must be truncated at some point.
> - The numerical values for the input data, as well as the results of the arithmetic operation performed on them, are rounded in a computer or calculator.

## Absolute Error and Relative Error

$$\textrm{Absolute Error} = \textrm{Approximate Value}-\textrm{True Value}$$

$$\textrm{Relative Error} = \frac{\textrm{Absolute Error}}{\textrm{True Value}}$$

Relative error is expressed as a percentage.

## Data Error and Computational Error
For calculating a function with an input data $f: \R \to \R$. The true value of input is $x$, and the desired result is $f(x)$. The approximated input is $\hat{x}$ and approximated result is $\hat{f}(x)$

Hence,

$$\textrm{Total Error} = (\hat{f}(\hat{x}) - f(\hat{x})) + (f(\hat{x}) - f(x)) = \textrm{computational error} + \textrm{data error}$$

## Truncation Error and Rounding Error

Truncation Error is the difference between the true result and the result that would be produced by a given algorithm using exact arithmetic.

Rounding Error is the difference between the result produced by a given algorithm using exact arithmetic and the result produced by the same algorithm using finite-precision, rounded arithmetic.

Computational error is a combination of truncation error and rounding error.

## Forward and Backward Error

$$y = f(x), f: \R \to \R$$

The discrepancy between the computed and true values, $\Delta y = \hat{y} - y$, is called the *forward error*.

The discrepancy between the true inputs, $\Delta x = \hat{x} - x$, is called the *backward error*.

## Sensitivity and Conditioning
A problem is *insensitive* or *well-conditioned* if a given relative change in the input data causes a reasonably commensurate relative change in the solution.

A problem is *sensitive* or *ill-conditioned* if a relative change in the solution can be much larger than that in the input data.

Condition number of the problem is the ratio of relative change in the solution to the relative change in the input. The greater the condition number, the more the problem is ill-conditioned.

$$\textrm{Condition number} = \frac{|(f(\hat{x}) - f(x)) / f(x)|}{|(\hat{x}-x) / x|} = \frac{|(\hat{y}-y)/y|}{|(\hat{x}-x)/x|} = \frac{|\Delta y /y|}{|\Delta x/x|}$$

$$|\textrm{Relative forward error}| = \textrm{condition number}\times |\textrm{relative backward error}|$$

# Computer Arithmetic

## Floating Point Numbers

Scientific notation exists, because theres a need to express very large number or very small number as a number of moderate size times an appropriate power of ten.

Floating number system $\mathbb{F}$ is characterized by four integers:
- $\beta$, Base or radix
- $p$, Precision
- $[L, U]$, Exponent range

Any floating-point number $x \in F$ has the form

$$x = \pm (d_0 + \frac{d_1}{\beta} + \frac{d_2}{\beta^2} + \dots + \frac{d_{p-1}}{\beta^{p-1}})\beta^E$$

Where $d_i$ is an integer such that

$$0 \leq d_i \leq \beta - 1, i=0,\dots, p-1$$

And $E$ is an integer that 

$$L \leq E \leq U$$

The part in parentheses, represented by a string of $p$ base-$\beta$ digits is called mantissa or significand, and $E$ is called the exponent or characteristic of the floating point number $x$.
- When using binary arithmetic, $\beta = 2$. When using hex, $\beta = 16$ etc.

## Normalisation

A floating-point system is normalized if the leading digit $d_0$ is always none-zero. That satisfies

$$1 \leq m \leq \beta$$

## Rounding
If a given real number $x$ is not exactly representable as a floating-point number, then it must be approximated by some "nearby" floating-point number. We denote this by $\textrm{fl}(x)$.

<++ tbc>
