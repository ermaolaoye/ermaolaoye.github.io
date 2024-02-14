# Linear and Nonlinear Systems
Properties:

**Additivity Property**
If $x-1 \to y_1$ and $x_2 \to y_2$ then $x_1 + x_2 \to y_1 + y_2$, for all $x_1$ and $x_2$

**Homogeneity or scaling property**
If $x \to y$ then $kx \to ky$ for all real and imaginary $k$

**In a single property(superposition)**
If $x_1 \to y_1$ and $x_2 \to y_2$ then $k_1x_1 + k_2x_2 \to k_1y_1 + k_1y_2$, for all values of constants $k_1$ and $k_2$

Hence a system described by a differential equation of the form is a linear system
$$a_0 \frac{d^N y(t)}{dt^N}+ a_1 \frac{d^{N-1}y(t)}{dt^{N-1}} + \cdots + a_Ny(t) = b_{N-M} \frac{d^M x(t)}{dt^M} + \cdots + b_{N-1} \frac{dx(t)}{dt} + b_Nx(t)$$

For example
$\frac{dy(t)}{dt}+ 3y(t) = x(t)$

<details>
<summary>Example 1</summary>

A system with input $x(t)$ produces output $y(t)$ according to

$$y(t) = \frac{d}{dt}x(t-1)$$

Is this system linear?

assuming that $y_1 = \frac{d}{dt}x_1(t-1), y_2 = \frac{d}{dt}x_2(t-1)$

Applying that $ax_1(t) +bx_2(t) \to y(t) = \frac{d}{dt}(ax_1(t-1)) + \frac{d}{dt}(bx_2(t-1))$

$$= a \frac{d}{dt}x_1(t-1) + b \frac{d}{dt}x_2(t-1)$$

Which means

$$= ay_1(t) + by_2(t)$$

Hence the system is linear

</details>

# Time-Invariant and Time-Varying Systems

System whose parameters do not change with time are time-invariant systems

> i.e. If the input is delayed for certain amount of time, the output will also delay certain amount of time, but the shape wouldn't be changed.


<details>
<summary>Example 2</summary>

A system with input $x(t)$ produces output $y(t)$ according to

$$y(t) = \frac{d}{dt}x(t-1)$$

Is this system time-invariant?

Assume $x_2(t) = x(t-\tau)$

Applying $x_2$ to the system yields

$$y_2 = \frac{d}{dt}x_2(t) = \frac{d}{dt}x(t-1-\tau) = y(t-\tau)$$
</details>

# Instantaneous and Dynamic System
A system is instantaneous when its output at any instant $t$ depends on the strength of its input at the same instant $t$, and not on any past or future values of the inputs. E.g. Resistive networks.

A dynamic systen have memory. Finite-memory (over past T seconds), Infinite-memory (e.g. inductive and capacitive networks).

<details>
<summary>Example 3</summary>

Is the system $y(t) = \frac{d}{dt}x(t-1)$ memoryless?

It is clear that the system depends on a past value of the input. At $t=0$, the output $y(0)$ depends on $x(-1)$ a past value.

Hence, no, the system is not memoryless
</details>

# Casual and Noncasual Systems

A casual system is one which the output at any instant $t_0$ depends only on the value of the input $x(t)$ for $t \leq t_0$

> Basically it only depends on current and past input, but not future input.

In a casual system, the output cannot start before the input is applied.

A system that violate this condition is noncasual system.

<details>
<summary>Example 4</summary>
Is the system $y(t) = \frac{d}{dt}x(t-1)$ casual?

By inspection it is casual, as it does not depends on future input.
</details>


# Continuous-Time and Discrete-Time Systems

System whose inputs and outputs are continuous-time signals are continuous-time systems.

System whose inputs and outputs are discrete-time signals are discrete-time systems.

# Invertible and Non-invertible Systems

If we can obtain $x(t)$ back from the corresponding output $y(t)$ by some oepration, the system $S$ is said to be invertible.

When several different inputs result in the same output(as in rectifier), it is impossible to obtain the input from the output, and the system is noninvertible.

<details>
<summary>Example 5</summary>
$y(t) = x^2(t)$ is not invertible
</details>

# Stable and Unstable System

The bounded inputs produces bounded output(BIBO).
> When we say a signal is bounded, we mean its amplitude is bounded within a range.

<details>
<summary>Example 6</summary>
$y(t) = \frac{d}{dt}x(t-1)$ is stable?

It is not, because if the input is a square wave, which is a bounded signal, the output could be infinite, as the slope at a instant could be infinite, hence not bounded, hence not stable.
</details>

# Linear differential System

$$\frac{d^N y(t)}{dt^N} + a_1 \frac{d^{N-1}y(t)}{dt^{N-1}} + \cdots a_Ny(t) = b_{N-M}\frac{d^M x(t)}{dt^M} + b_{N-M+1} \frac{d^{M-1}x(t)}{dt^{M-1}} + \cdots + b_Nx(t)$$

Is a linear differential system, which can be simplified as, $D = \frac{d}{dt}$

$$D^N + a_1D^{N-1} + \cdots + a_Ny(t) = b_{N-M}D^{M} + b_{N-M+1}D^{M-1} + \cdots + b_Nx(t)$$

And

$$Q(D)y(t) = P(D)x(t)$$


# System Response
## Zero Input Response

When input is 0.

When $x(t) = 0$,

$$(D^N + a_1D^{N-1} + \cdots) y_0(t) = 0 $$

Hence

$$c(\lambda^N + a_1\lambda^{N-1} + \cdots + a_N)e^{\lambda t} = 0$$

The characteristic polynomial is $\lambda^N + a_1\lambda^{N-1} + \cdots + a_N$

The characteristic equation is $\lambda^N + a_1\lambda^{N-1} + \cdots + a_N = 0$

The characteristic roots is the solution of the characeristic equation

The characteristic mode is $e^{\lambda n}$

And combining the characterisitc modes, we get the zero input response

$$y_0(t) = c_1e^{\lambda_1 t} + c_2e^{\lambda_2t} + \cdots + c_Ne^{\lambda_N t}$$

### Repeated Characteristic Roots

If the characteristic equation is $(\lambda - \lambda_1)^r (\lambda_2 \cdots)$

The characteristic modes will be

$$(c_1 + c_2t + c_3t^2 + \cdots) e^{\lambda_1t} + \cdots$$

## Zero State Response

When the initial condition is 0.

## The Unit Impulse Response

When input is $\delta(t)$

And the initial condition is 0.

The unit impulse response $h(t)$ can be found using either

$h(t) = \delta(t) +$ characteristic modes

Or the simplified impulse matching method

$h(t) = b_0\delta(t) + [P(D) y_n(t)] u(t)$

$y_0(t) = c_1 e^{\lambda t} + c_2 e^{\lambda_2 t}+ \cdots$

Where $y_n(t)$ is a linear combination of the characteristic modes of the system subject to the initial condition that
$$y_n(0) = \dot{y_n}(0) = \ddot{y_n}(0) =\cdots = y_n^{(N-2)}(0) = 0$$

and only that $y^{(N-1)} = 1$

比如second order de

$y_n(0) = 0, \dot{y_n}(0)= 1$

## Total Response
Total Response = Zero Input Response + Zero State Response


