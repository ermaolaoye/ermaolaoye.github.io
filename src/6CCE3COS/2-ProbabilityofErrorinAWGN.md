# Normal Distribution Reminder
A normal distribution is a continuous probability distribution characterized by a bell-shaped curve, and it is defined by two parameters:

**Mean** $\mu$: This is the average or expected value of the distribution, and it defines the center of the distribution.

**Variance** $\sigma^2$ This measures the spread or width of the distribution. A higher variance means the distribution is more spread out.

The PDF of a normal distribution is givern by

$$f(x) = \frac{1}{\sqrt{2\pi \sigma^2}}e^{- \frac{(x-\mu)^2}{2 \sigma^2}}$$

## Properties of Normal Distribution

**Symmetry** 

The normal distribution is symmetric about its mean $\mu$. This means that the distribution to the left of the mean is a mirror image of the distribution to the right.

----

**Mean, Median, Mode are Equal** 

The mean, median and mode all coincide at $\mu$, since the distribution is perfectly symmetric.

## Standard Normal Distribution

A special case of normal distribution is where the mean is 0 and variance is 1, the distribution became standard normal distribution:

$$Z \sim \mathcal{N}(0,1)$$

PDF of standard normal distribution is

$$f(z) = \frac{1}{\sqrt{2\pi}}e^{0 \frac{z^2}{2}}$$

Any normal distribution can be converted to a standard normal distribution by using the transformation

$$Z = \frac{X - \mu}{\sigma}$$


# Average Probability of Error, $P_e$

Consider vector AWGN channel: $\boldsymbol{y}= \boldsymbol{x} + \boldsymbol{n}$

$P_e$ is usually calculated for the ML detector, i.e. $P_{\boldsymbol{x}}(i) = \frac{1}{M}$
- The optimum ML detector: $\hat{\boldsymbol{x}} = \boldsymbol{x}_i$ (or $\hat{m} = m_i$), if for all $j \neq i$: $|| \boldsymbol{v} - \boldsymbol{x}_i||^2 \leq || \boldsymbol{v} - \boldsymbol{x}_j||^2$
- $P_e$ for ML detector only depends on the signal constellation and the noise variance $\sigma^2 = \frac{N_0}{2}$


$$P_e = P(\hat{m} \neq m) = \sum_{i=0}^{M-1}P_{e|i}P_x(i)$$

and 

$$P_{e|i} = P(\hat{m} \neq m_i | m = m_i) = P(\hat{\boldsymbol{x}} \neq \boldsymbol{x}_i | \boldsymbol{x } = \boldsymbol{x}_i) = \textrm{Prob.}\{\boldsymbol{n} \textrm{ such that: }\boldsymbol{y} = \boldsymbol{v }\in D_j, j\neq i, \boldsymbol{x } = \boldsymbol{x}_i\}$$

## 1-Dimensional Binary Transmission $P_e$


