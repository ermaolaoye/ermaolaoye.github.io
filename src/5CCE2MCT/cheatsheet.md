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
## Mathematical
用dc motor当例子, 首先先找到variales, parameters and units

![](./assets/imgs/cs-mathmodelling1.png)

![](./assets/imgs/cs-mathmodelling2.png)

通过这些东西deduce他的equation出来，通过circuit analysis或者mechanical analysis啥的

$$V(t) = Ri(t) + L \frac{di(t)}{dt } + e(t)$$

$$e(t) := k_e \dot{\theta(t)}$$

考试会把那个问题用到的system的mathematical equation提供给我们

### State Vector

### State Space Form

### Laplace Transform and Transfer Function

## Physical
就是用电脑跑simulation考试必不可能考

## Data-Driven
就是look up table, 考试也必不可能考

# Linear System Analysis

## Pole Zero Maps

## Root Locus

## Pole Placement

## Bode Plot

## Eigenvalues

# Signal Processing and Filter

# Model Based Trajectory Tracking Control
