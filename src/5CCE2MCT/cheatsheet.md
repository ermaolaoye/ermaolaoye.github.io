> **! hint 这个傻逼module用的mathematical notation和之前SAS那个老师用的很他妈不一样**

A dynamical system can be modelled as a function that relates inputs to outputs.
![](./assets/imgs/cs-dynamicsystemmodel.png)

# Models of dynamic systems
A dynamical system has states, $x(t)$, and state derivatives $\dot{x}(t)$
> state 就是 time dependent variable 比如position and velocity of a pendulum. angle and angular rate of motor.

A generalised continuous form of the dynamical system equation is
![](./assets/imgs/cs-generaliseddynamicsystemequation.png)

> PROVIDED IN FORMULA SHEET

> Noise(internal), Disturbance(external)

![](./assets/imgs/cs-graphofthatgeneralisedform.png)

## 行业黑话
![](./assets/imgs/cs-heihua1.png)

![](./assets/imgs/cs-heihua2.png)

# Modelling Approaches
Linear System satisfies superposition principle

It means they met these properties:

1. Homogeneity: $f(\eta \cdot A) = \eta \cdot f(A)$
2. Additivity: $f(A+B) = f(A) + f(B)$

Hence, to summarize

$$f(\eta_1 \cdot A + \eta_2 \cdot B) = \eta_1 \cdot f(A) + \eta_2 \cdot f(B)$$
## Mathematical
用dc motor当例子, 首先先找到variales, parameters and units

![](./assets/imgs/cs-mathmodelling1.png)

![](./assets/imgs/cs-mathmodelling2.png)

通过这些东西deduce他的equation出来，通过circuit analysis或者mechanical analysis啥的

$$V(t) = Ri(t) + L \frac{di(t)}{dt } + e(t)$$

$$e(t) := k_e \dot{\theta(t)}$$

考试会把那个问题用到的system的mathematical equation提供给我们

### Laplace Transform

没什么可讲的，就还是用LT去find solution of ODEs

#### Transfer Function
The transfer function $G(s)$:

$$Y(s) = G(s)U(s) + \textrm{initial value terms}(y_0^k, u_0^k)$$

但如果system是assume to be at rest prior to application of the input, 那他就是

$$Y(s) = G(s)U(s)$$

Hence, the transfer function is calculated as

$$G(s) = \frac{Y(s)}{U(s)}$$

> Roots of the numerator: system **zeros**

> Roots of denominator: system **poles**

If all the poles have **negative real parts**, the system is stable.

### State Vector

### State Space Form
<details>
<summary>Matrix Multiplication Reminder</summary>

![](./assets/imgs/cs-matrixmultiplication.png)

</details>

$$\boldsymbol{\dot{x}}(t) = \boldsymbol{Ax}(t) + \boldsymbol{Bu}(t)$$
$$\boldsymbol{y}(t) = \boldsymbol{Cx}(t) + \boldsymbol{Du}(t)$$

- $\boldsymbol{x}(t)$ represents the 'state' vector
- $\boldsymbol{y}(t)$ represents the output vector
- $\boldsymbol{u}(t)$ is the input vector
- $\boldsymbol{A}$ is the state transition matrix
- $\boldsymbol{B}$ is the input matrix
- $\boldsymbol{C}$ is the output(selection) matrix
- $\boldsymbol{D}$ is the feedthrough matrix

<details>
<summary>SS of SISO example</summary>

![](./assets/imgs/cs-sisoss.png)

</details>

#### Linearization
Given a non linear system $\dot{\boldsymbol{x}}(t) = f(\boldsymbol{x}(t), \boldsymbol{u}(t), t)$

Firstly choose a equilibrium point $(x_0, u_0)$ where

$$\dot{x_0} = 0 \Longleftrightarrow f(x_0, u_0) = 0$$

And then make a first order Taylor series expansions of f and g around $(x_0, u_0)$

And then introduce $\delta \boldsymbol{x} = \boldsymbol{x}-\boldsymbol{x}_0$

$$\delta \boldsymbol{\dot{x}}(t) = \boldsymbol{A}(t)\delta \boldsymbol{x}(t) + \boldsymbol{B} (t) \delta \boldsymbol{u}(t)$$

$$\delta \boldsymbol{y}(t) = \boldsymbol{C}(t) \delta \boldsymbol{x}(t) + \boldsymbol{D}(t) \delta \boldsymbol{u}(t)$$

$$A = [\frac{\partial f}{\partial \boldsymbol{x}}]_0 = \frac{\partial }{\partial \boldsymbol{x}} f(x_0, u_0)$$

etc

usually with small angle approximation, when linearisihng around 0 $\sin(\theta) \approx \theta, \cos(\theta)\approx 1$

when linearising around $\pi$, $\sin(\theta) \approx -\theta$, $\cos(\theta) \approx -1$



### Laplace Transform and Transfer Function

## Physical
就是用电脑跑simulation考试必不可能考

## Data-Driven
就是look up table, 考试也必不可能考

# Feedback Control

![](./assets/imgs/cs-feedbackcontrol.png)

- **plant** is the system being controlled
- **reference** is the desired output, or system behaviour
- **feedback** is a collection of state measurements(a subset of the output)
- **error** is the difference between the desired and actual states
- **gain** multiplies the current error, and the resulting product/signal is used to control the plant in a way that minimize the subsequent error

----

- **sensors** measure the quantity that is subject to control
- **actuators** acts on the plant by providing motion
- **control law** is the mathematical equation(rules) that maps sensor signal to actuators signals
- **controller** processes the sensory feedback, and the control law, delivers the resulting input signal to the actuators.

## Full state feedback

Full state feedback(FSF) 就是干他娘的塞爆feedback, 把所有的state全都塞进去

## PID Control
PID control relies upon a weighted combination of Proportional, Integral, and Derivative terms

$$u(t) = k_p e(t) + k_D \cdot{e}(t) + k_I \int_{0}^{t}e \cdot dt$$

- $r(t)$ reference signal
- $e(t)$ error signal
- $e(t) = r(t) - y(t)$
- $k_P, k_I, k_D$ controller gains

![](./assets/imgs/cs-piddiagram.png)

![](./assets/imgs/cs-piddiagram2.png)

$k_P$ the controller gain determines how **quickly** the system respond to the error, increasing $k_P$ will cause
- Rise time decreases
- Overshoot increases
- Settling time small change
- Steady-state error decreases

如果最后的output没有converge，反而在oscillate,那就要用i

$k_I$ mainly used to address the steady-state offset problem associated with P-only controllers, increasing $k_I$ wil cause
- Rise time decreases
- Overshoot increases
- Settling time increases
- Steady-state error eliminated
- Stability decreases

如果他妈的overshoot烂掉了就要用d term

$k_D$ is known as the 'damping gain' in robotics, used to supresses oscillations and overshoot, however, damping terms are **sensitive to noise**. Increasing $k_d$ will cause.
- Rise time minor change
- Overshoot decreases
- Settling time decreases
- Steady-state error minor to no effect
- Stability improves

PD control yields fast, oscillation free response, but unable to guarantee steady-state error minimisation, and may amplify high-frequency noise.

### LT Transfer Function of PID Controller
$$U(s) = k_P E(s) + k_D E(s)s + \frac{k_I E(s)}{s} = (k_P + k_D s + \frac{k_I}{s})E(s)$$

$$G(s) = \frac{U(s)}{E(s)} = k_P + k_D s + \frac{k_I}{s}$$

<details>
<summary>Example</summary>

![](./assets/imgs/cs-ltpidexample.png)

</details>

# Linear System Analysis

## Pole Zero Maps

## Root Locus

## Pole Placement

## Bode Plot

## Eigenvalues

# Signal Processing and Filter

# Model Based Trajectory Tracking Control
