# Poisson Process
A Poisson Process is a continuous stochastic process that counts the number of 'events' $N_t$ occuring in the interval $[0,t)$

## Properties of a Poisson Process
The probability of $k$ events occuring in the interval $[t, t+L)$ dependes only on the length of the interval $L$

$$P(N_{t+L} - N_t = k) = P(N_L = k)$$

i.e. the number of events depends only on the interval length

![](./assets/imgs/10-poissonsproper.png)

The second one is not proper, because there's multiple event occuring at the same time. This makes it not a poisson process distribution.

---

For short intervals, the probability is approximatley proportional to the size of the interval

$$P(N_{(t+\delta)} - N_t = 1) \approx \lambda \cdot \delta$$

Where $\lambda > 0$ is the rate of the Poisson process

$\lambda$ means the estimated number of event happened. $\delta$ is the small time interval

This is because the poisson process distribution over a small interval is basically just a binomial distribution. and the expectation of that is just $np$, which n would be $\delta$

The probability of more than one event occuring in a short interval is negligible
$$P(N_{t+\delta)} - N_t \geq 2)\approx 0$$

This is because,

