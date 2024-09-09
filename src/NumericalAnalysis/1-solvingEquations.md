# The Bisection Method
## Bracketing a root

**DEFINITION 1.1** : The function $f(x)$ has a **root** at $x=r$ if $f(r)=0$

**THEOREM 1.2** : Let $f$ be a *continuous function* on $[a,b]$, satisfying $f(a)f(b) < 0$. Then $f$ has a root between $a$ and $b$. There's a number $r$ satisfying $a < r < b$ and $f(r) = 0$

**DEFINITION 1.3** : A solution is correct within $p$ decimal places if error is less than $0.5 \times 10^{-p}$

**Bisection Method** 

```
Given initial interval [a,b] such that f(a)f(b) < 0
while ( b - a ) / 2 > TOL
    c = (a + b) / 2
    if f(c) = 0, stop, end
    if f(a)f(c) < 0
        b = c
    else
        a = c
    end
end
```

> TOL is the tolerance which is a small positive number that determines how close the algorithm's approximation should be to the actual root before stopping.

Bisection method keep bisecting the interval between $a$ and $b$, until tolerance or 0 is met to find the approximated root.

After $n$ steps of the Bisection Method, for the midpoint $x_c$ estimate the solutoin $r$, we find that

$$\textrm{Solution Error} = | x_c - r | < \frac{b-a }{2^{n+1}}$$

and

$$\textrm{Function Evaluations} = n + 2$$

<details>
<summary>Example on Bisecting and Requirement of Accuracy</summary>

![](./assets/imgs/2-exampleonbisecting.png)

</details>
