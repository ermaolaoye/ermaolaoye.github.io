# Finite Difference Formulas

By definition, the derivative of $f(x)$ at a value $x$ is 

$$f'(x) = \lim_{h\to 0} \frac{f(x+h) - f(x)}{h}$$

Taylor's Theorem says that if $f$ is twice continuously differentiable then

$$f(x+h) = f(x) + hf'(x) + \frac{h^2}{2}f''(c)$$

where $c$ is between $x$ and $x +h$

**Two-point forward difference formula** 

$$f'(x) = \frac{f(x+h) - f(x)}{h} - \frac{h }{ 2 }f''(c)$$

First Order Approximation:

$$f'(x) \approx \frac{f(x+h) - f(x)}{h}$$

where the $c$ term is treated as an error. Since the last term is corresponding to $h$, as we make $h$ small enough, we can make the error small.

<details>
<summary>Example on first order formula</summary>

![](./assets/imgs/5-firstorderexample.png)

</details>

**Second Order Formula** 

If $f$ is three times continuously differentiable then

$$f(x+h) = f(x) + hf'(x) + \frac{h^2}{2}f''(x) + \frac{h^3}{6}f'''(c_1)$$

$$f(x-h) = f(x) - hf'(x) + \frac{h^2}{2}f''(x) - \frac{h^3}{6}f'''(c_2)$$

where $x-h < c_2 < x < c_1 < x+h$.

subtracting the equations gives the three-point formula with explicit error term:

$$f'(x) = \frac{f(x+h) - f(x-h)}{2h} - \frac{h^2}{6}f'''(c)$$

where $x-h < c < x+h$

> Proof on the error term neglected

<details>
<summary>Three-point centered difference formula example</summary>

![](./assets/imgs/5-threepointexample.png)

</details>

You can keep Taylor expanding the function to find higher derivatives formula.

**Three-point centered-difference formula for second derivative** 

**f''(x) = \frac{f(x-h) - 2f(x) + f(x+h)}{h^2} - \frac{h^2}{12}f^{(iv)}(c)** 

