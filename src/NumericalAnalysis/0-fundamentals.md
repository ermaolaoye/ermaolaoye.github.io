# Calculus Reminder
## Taylor's Theorem with Remainder

Taylor's theorem with remainder states that any smooth function can be expressed as sum of its Taylor series expansion up to a certain degree, plus a "remainder" term that represents the error of this approximation.

If a function $f(x)$ is $k+1$ times continuously differentiable on the interval between $x, x_0$, then there exist a number $c$ between $x$ and $x_0$ such that

$$f(x) = f(x_0) + f'(x_0)(x-x_0) + \frac{f''(x_0)}{2!}(x-x_0)^2 + \frac{f'''(x_0 )}{3!} (x-x_0)^3 + \dots \\ + \frac{f^{(k)}(x_0 )}{k! } (x-x_0)^k + \frac{f^{(k+1)}(c)}{(k+1)!}(x-x_0)^{k+1}$$

- The polynomial part of the result, the term up to degree $k$, is called the *degree $k$ Taylor polynomial* for $f$ centered at $x_0$. (used to approximate the result of polynomial)

- The last term is called the *Taylor Remainder*.(usually is small)

**THEOREM** (Intermediate Value Theorem) Let $f$ be a continuous function on the interval $[a,b]$. Then $f$ realizes every value between $f(a)$ and $f(b)$. More precisely, if $y$ is a number between $f(a)$ and $f(b)$, then there exists a number $c$ with $a \leq c \leq b$ such that $f(c) = y$.

**THEOREM** (Continuous Limits) Let $f$ be a continuous function in a neighborhood of $x_0$, and assume $\lim_{n\to \infty} x_n = x_0$. Then

$$\lim_{n  \to \infty} f(x_n) = f (\lim_{n  \to \infty }x_n) = f(x_0)$$

