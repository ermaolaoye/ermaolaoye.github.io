# Laplace Transform
$$X(s) = \int_{-\infty}^{\infty} x(t)e^{-st}dt$$

$$x(t) = \frac{1}{2\pi j} \int_{c-j\infty}^{c+j\infty} X(s)e^{st}dt$$

Hence, $\mathcal{L}\{x(t)\} = X(s)$, and $\mathcal{L}^{-1}\{X(s)\} = x(t)$

## The Difference Between Laplace and Fourier Transform
Laplace transform is applicable for analysing both stable and unstable system from zero time ($t=0^+$) onwards.

Fourier Transform is generally used for analyzing stable systems or stable portions of signals.

## Laplace Table
![](./assets/imgs/cs-laplacetable.png)

## Laplace Property
> These Properties are Provided in the Exam

![](./assets/imgs/cs-laplaceproperties.png)

<details>
<summary>Find Laplace Transform using table and time shifting property</summary>

1. $u(t) - u(t-1)$

$$F(s) = \frac{1}{s} - \frac{1}{s}e^{-s}$$

2. $e^{-(t-\tau)}u(t-\tau)$

$$F(s) = \frac{1}{s+1}e^{-s\tau}$$

3. $e^{-(t-\tau)}u(t)$

$$f(t) = e^{\tau} e^{-t}u(t)$$

therefore

$$F(s) = e^{\tau}\frac{1}{s+1}$$

4. $te^{-t}u(t-\tau)$

![](./assets/imgs/cs-laplaceexampletutorial1.png)

</details>

## ROC
Converge means the inetgral that defines the laplace transform results in a finite number(converge). If it does not, then the integral diverges.

Usually just investigate the term $e^{-st}$, and usually investigate the real part $\sigma$ of $s$, which affect the exponential decay or growth rate.

> If $\sigma$ is positive, $e^{-\sigma t}$ will decay as $t \to \infty$, ensuring that the integral converges. In contrast, it diverge.

Region of Convergence is the set of values in the complex plane for which the integral defining the laplace transform converges.

![](./assets/imgs/cs-rocexample.png)

<details>
<summary>Example on Direct Integration and Finding the ROC</summary>

By direct integration, find the laplace transforms and the region of convergence of the following functions:

$$u(t) - u(t-1)$$

$$F(s) = \int_{0}^{\infty} e^{-st}f(t) dt = \int_{0}^{1}e^{-st}dt$$

![](./assets/imgs/integratingest.png)

$$ = - \frac{e^{-st}}{s}|^1_0$$
$$ = \frac{1}{s}[1-e^{-s}]$$

and this is valid for all value of s

![](./assets/imgs/cs-rocexample2.png)

The Re means the real part of, which is $\sigma$

</details>

## Partial Fraction
![](./assets/imgs/cs-partialfraction.png)

If it is a improper fraction, do a long division first

![](./assets/imgs/cs-improperpartialfraction.png)

## Inverting Laplace Transforms
$$F(s) = \frac{b_ms^m + b_{m-1}s^{m-1} + \cdots + b_1s + b_0}{a_ns^n + a_{n-1}s^{n-1} + \cdots + a_1s + a_0}$$
$$= \frac{a_1}{s-p_1} + \frac{a_2}{s-p_2} + \cdots + \frac{a_q}{s-p_q}$$

And then inverse to find the $f(t)$

<details>
<summary>Finding the inverse laplace Example 1</summary>

![](./assets/imgs/cs-inverselaplace1.png)

</details>

<details>
<summary>Finding the inverse laplace Example 2</summary>

![](./assets/imgs/cs-inverselaplacce2.png)

</details>

<details>
<summary>Using inverse laplace to find ODE solution</summary>

![](./assets/imgs/cs-inverselaplace3.png)

![](./assets/imgs/cs-inverselaplace4.png)

![](./assets/imgs/cs-inverselaplace5.png)

</details>

<details>
<summary>Tutorial on inverse laplace</summary>

![](./assets/imgs/cs-inverselaplacetutorial1.png)

</details>

<details>
<summary>Tutorial Difficult Example</summary>

Find the inverse laplace of the following function
$$\frac{e^{-(s-1)} + 3}{s^2-2s+5}$$

![](./assets/imgs/cs-tutorial4-4solution.png)

</details>

<details>
<summary>Tutorial on Using LT to find solution of DE</summary>

![](./assets/imgs/cs-tutorialonltfindde.png)

</details>


### Zero Input and Zero State Response
ZIR is when inputs are 0 all the time.

When a system is described as

$$\frac{d^m y}{dt^n} + a_{n-1} \frac{d^{m-1}y}{d^{n-1}t} + \cdots + a_0 y = b_0 x$$

And when $x$ is 0 all the time

ZSR describes how system reacts to an input starting from a zero initial state. Basically the response of a system which initially is at rest, and any output is due solely to the inpuit applied.

The total response of a CLTI system is the sum of the zero input and zero state responses.
$$y(t) = y_{zi}(t) + y_{zs}(t)$$


The laplace transform gives the total response. It is possible to separate the two components if we desire.

感觉应该不会考让我们从laplace transform分离一个zir这么傻逼的东西，除非出卷那个人的脑子被狗屎强奸了

如果考了的话，就直接把input全部改成0然后硬算inverse laplace就完事了

### Transfer Function
Basically $Y(s) = H(s) X(s)$

$$H(s) = \frac{P(s)}{Q(s)}$$

![](./assets/imgs/cs-transferfunction.png)

<details>
<summary>Transfer Function Example</summary>


![](./assets/imgs/cs-transferfunctionexample.png)

</details>

<details>
<summary>Tutorial Transfer Function Example</summary>

![](./assets/imgs/cs-transfertutorial1.png)

![](./assets/imgs/cs-transfertutorial2.png)

</details>


Poles are the values that makes the denominator zero. Holes(Zeros) are the value that makes the numerator zero.

### Stability of Transfer Function

> $H(s) = \frac{s+2}{(s+1)(s+3)}$
> Poles are $s=-1, s=-3$, Zeros are $s = -2$

If all the poles of $H(s)$ are in the left half of the complex plane, When $s < 0$, the system is stable. The poles may be simple or repeated

If the (i) at least one pole of $H(s)$ is in the RHP, or (ii) there are repeated poles of $H(s)$ on the imaginary axis, the LTI is unstable.

If and only if there are no poles of $H(s)$ in the RHP and some unrepeated poles on the imaginary axis, the LTI is marginally stable.

### Inverse System (Inverse Transfer Function)
$$H_i(s) = \frac{1}{H(s)}$$

### Block Diagrams
#### Cascade interconnection
![](./assets/imgs/cs-cascadeinter.png)

#### Parallel Interconnection
![](./assets/imgs/cs-parallel.png)

#### Feedback Interconnection

![](./assets/imgs/cs-feedbackinter.png)

![](./assets/imgs/cs-feedbackinterproof.png)

<details>
<summary>Example of Determine the transfer function</summary>

![](./assets/imgs/cs-transferexample.png)

</details>

# Frequency Response

When the input of the function is a sinusoidal function, then the system response is given by

$$y(t) = |H(j\omega)| \cos [\omega t + \theta + \angle H (j\omega)]$$

The input and output have the same frequency

The amplitude of the output sinusoid is $|H(j\omega)|$ times the input amplitude

The phase of the output sinusoid is shifted by $\angle H(j\omega)$ with respect to the input phase

- $|H(j\omega)|$ is the **amplitude response**
- $\angle H(j\omega)$ is the **phase response**

Therefore, $H(j\omega)$ has the information of both response, hence is called **frequency response**

<details>
<summary>Example of finding the frequency response</summary>

![](./assets/imgs/cs-frequencyresponseexp1.png)

</details>

<details>
<summary>Example of Ideal Integrator and Ideal Differentiator</summary>

![](./assets/imgs/cs-frequencyresponseexp2.png)

</details>

## Bode Plots

The amplitude and phase response plots of a function of $\omega$ on a logarithmic scale are known as Bode plots

The Bode plots are a graphical way to  represent the frequency response of a linear time-invariant (LTI) system. They consist of two separate plots:

- Magnitude Plot: shows the magnitude of the system's frequency response, $|H(j\omega)|$ in decibels (dB), plotted against frequency on a logarithmic scale.
> To convert the magnitude to decibels, the following formula is used $20\log_{10}|H(j\omega)|$
- Phase Plot: shows the phase angle of the frequency response, $\angle H(j\omega)$, plotted against frequency on a logarithmic scale.

<++>

# Filters
![](./assets/imgs/cs-analogfilters.png)

![](./assets/imgs/cs-filters2.png)

## 行业黑话
### Spectrum 
Spectrum refers to the representation of a signal in freuqency domain.

Basically after FT is applied to the signal,  the graph is a fuckin spectrum.

### Carrier

A carrier is a waveform(usually a sinusoidal) that is modulated with an input signal to carry information.

### Bandwidth (W)

Bandwidth is the range of frequencies within a continuous set of freqquencies. Which measure the width of the spectrum.

### Envelope
Envelope of a signal refers to a smooth curve that outlines its extremes.

# Fourier Transforms
> **FT的Formula都需要自己记住，Formula Sheet没有提供**

The fourier transform of a continuous time-domain signal $x(t)$ is given by the following integral:
$$X(\omega) = \int_{-\infty}^{\infty}x(t)e^{-j\omega t}dt$$
> which $\omega = 2\pi f$

The result $X(\omega)$ is generally a complex function, where
- The magnitude $|X(\omega)|$ is the magnitude of the frequency components
- The phase arg $\angle X(\omega)$ is the phase shift of the frequency components

> For real $x(t)$, the amplitude will be an even function(mirror symmetry with respect to the y-axis), the phase will be a odd function(rotational symmetry, 180 degree rotate around the origin) of $\omega$

<details>
<summary>Draw FT Diagram Example</summary>

![](./assets/imgs/cs-drawftexample.png)

![](./assets/imgs/cs-drawftexample2.png)

</details>

<details>
<summary>Use Fourier Integral to find FT</summary>

![](./assets/imgs/cs-usefourierintegraltofindft.png)

</details>

## Euler's Formula

Good to remember in this section

$$e^{j\theta} = \cox(\theta) + j\sin(\theta)$$

And

$$\cos(\theta) = \frac{e^{j\theta} + e^{-j\theta}}{2}$$
$$\sin(\theta) = \frac{e^{j\theta} - e^{-j\theta}}{2j}$$


## Inverse Fourier Transform
$$x(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty} X(\omega)e^{j\omega t}d\omega$$

<details>
<summary>Example of using Fourier Integral to find FT</summary>

![](./assets/imgs/cs-fourierintegralexp.png)

</details>

<details>
<summary>Find Zero-State Response given Input of LTIC and Transfer Function</summary>

![](./assets/imgs/cs-5-3tutorial.png)

</details>


## Fourier Table
![](./assets/imgs/cs-fouriertable.png)

## Useful Functions
<details>
<summary>Examples of drawing these functions</summary>

![](./assets/imgs/cs-exampleofdrawingfunction.png)

</details>

<details>
<summary>Using FT to find these funtion's signals</summary>

![](./assets/imgs/cs-tutorial6-4ftandsignal.png)

![](./assets/imgs/cs-tutorial6-4ftandsignal2.png)

![](./assets/imgs/cs-6-4explaination.png)
</details>


### Unit Gate Function
![](./assets/imgs/cs-unitgate.png)

### Unit Triangle Function
![](./assets/imgs/cs-unittriangle.png)

<details>
<summary>Fourier Integral</summary>

![](./assets/imgs/cs-fourierintegraloftriangle.png)

![](./assets/imgs/fourierintegraloftriangle2.png)

</details>


### Interpolation Function $\textrm{sinc}(x)$
![](./assets/imgs/cs-sincx.png)

- $\textrm{sinc}(x)$ is an even function of $x$
- $\textrm{sinc}(x) = 0$ when $\sin x = 0$ except at $x = 0$.
- Using L'Hopital rule, $\textrm{sinc}(0) = 1$

### Unit Impulse
![](./assets/imgs/cs-unitimpulse.png)

## Fourier Properties
![](./assets/imgs/cs-fourierproperties.png)

![](./assets/imgs/cs-fourierpropertiesgpt.png)

<details>
<summary>Fourier Properties Example</summary>

![](./assets/imgs/cs-tutorial6-6.png)

</details>


## Signal Energy
> 没有公式
As we known the signal energy formula is
$$E_x = \int_{-\infty}^{\infty} |x(t)|^2dt$$

For FT signals, the signal energy can also be obtained by

$$E_x = \frac{1}{2\pi}\int_{-\infty}^{\infty} |X(\omega)|^2 d\omega$$

For real FT signals, its formula is
$$E_x = \frac{1}{\pi} \int_{0}^{\infty} |X(\omega)|^2 d\omega$$

Therefore, the energy contributed by spectral components of frequencies between $\omega_1$ and $\omega_2$ is
$$\Delta E_x = \frac{1}{\pi} \int_{\omega_1}^{\omega_2} |X(\omega)|^2 d\omega$$

<details>
<summary>Example on Finding Energy</summary>

![](./assets/imgs/cs-exampleonfindingenergy.png)

</details>

# Signal Transmission

## Distortion During Transmission

Transmission is distortionless if the input and output have identical waveshapes within a multiplicative constant

<details>
<summary>Example given by chatGPT</summary>

![](./assets/imgs/cs-distortionexample.png)

</details>

The input $x(t)$ and the output $y(t)$ satisfy the condition

$$y(t) = G_0x(t-t_d)$$

The Fourier trnasform of this equation yields

$$Y(\omega) = G_0X(\omega)e^{-j\omega t_d}$$

And also

$$Y(\omega)=  X(\omega)H(\omega), \textrm{ and } H(\omega) =G_0e^{-j\omega t_d}$$

It follows that  $|H(\omega)| = G_0, \angle H(\omega)$

Hence, for distortless transmission, $|H(\omega)|$ must be a constant, and the phase response $\angle H(\omega)$ must be a  linear function of $\omega$ with slope $-t_d$.

The group delay is the negative derivative of the phase response, it measures the time delay experienced by the different frequency components of a signal, which is crucial for understanding how a system affects the signal's phase.

$$t_g (\omega) = - \frac{d}{d\omega}\angle H(\omega)$$

## Modulation

$$m(t)\cos \omega_c t \Longleftrightarrow \frac{1}{2}[M(\omega + \omega_c) + M(\omega - \omega_c)]$$

<details>
<summary>Modulation Example</summary>

![](./assets/imgs/cs-modexamp.png)

![](./assets/imgs/cs-modexamp2.png)

![](./assets/imgs/cs-modexamp3.png)

</details>

## Discrete Time Fourier Transform

![](./assets/imgs/cs-dtft.png)


# Sampling

Sampling is a process by which a continuous-time signal is converted into a discrete-time signal by taking snapshots, or samples, of the continuous signal at fixed time intervals.

## Nyquist Rate

Nyquist rate is the minimum rate at which the signal must be sampled to accurately reconstruct the original signal from its samples without any loss of information.

The Nyquist rate is formally defined as twice the highest frequency present in the signal, which is the bandwidth (B) of the signal. If a signal is bandlimited to B Hz, then the Nyquist rate ($f_N$) is given by:
$$f_S = 2B$$

If two signals $x_1(t),x_2(t)$ are multiplied, in the frequency domain, it corresponds to the convolution of their spectra $X_1(\omega)$ and $X_2(\omega)$

The resulting spectrum $X_{\textrm{product}}(\omega)$ will have a bandwidth that is the sum of the individual bandwidths

<details>
<summary>Nyquist Rate Example</summary>

![](./assets/imgs/cs-exampleofnyquistrate.png)

</details>


## Nyquist Interval
The Nyquist interval is the time interval between successive samples when sampling at the Nyquist rate. It is the reciprocal of the Nyquist rate. 

$$T = \frac{1}{f_S} = \frac{1}{2B}$$

<details>
<summary>Nyquist Interval Example</summary>

![](./assets/imgs/cs-nyquistsamplinginterval.png)

The bandwidth of $\textrm{sinc}(50\pi t) = 25 \textrm{Hz}$
The bandwidth of $\textrm{sinc}(100\pi t) = 50 \textrm{Hz}$

![](./assets/imgs/cs-nyquistsamplinginterval2.png)

Multiple signal => Convolution in F

$$B = B_1 + B_2 = 75 \textrm{Hz}$$

Nyquist $F_S = 150 \textrm{Hz}$

Nyquist $T_s = \frac{1}{150} = 0.0066666s$

</details>


## Nyquist Samples
Samples of a signal taken at its Nyquist rate are the Nyquist samples of that signal.

$$\omega_s = \frac{2\pi}{T} = 2\pi f_s$$

$$\bar{x}(t) - x(t)\delta_T(t) = \frac{1}{T}[x(t) + 2x(t)\cos\omega_s t + 2x(t)\cos 2\omega_s t + \cdots]$$

The forier transform of this signal is 

$$\bar{X} (\omega) = \frac{1}{T} = \sum_{n=-\infty}^{\infty}X(\omega- n\omega_s)$$

<details>
<summary>Example on Over and Undersampling</summary>

![](./assets/imgs/cs-overandundersampleing.png)

![](./assets/imgs/cs-overandundersampling2.png)

![](./assets/imgs/cs-overandundersampling3.png)
</details>

## Signal Reconstruction
The process of reconstructing a continuous-time signal $x(t)$ from its samples is also known as interpolation.

For the case of Nyquist sampling rate, $T = \frac{1}{2B}$, the interpolation formula is

$$x(t ) = \sum_{n}^{}x(nT)\textrm{sinc}(2\pi Bt - n\pi)$$

<details>
<summary>Signal Reconstruction Example</summary>

![](./assets/imgs/cs-signalreconstruction.png)

![](./assets/imgs/cs-signalreconstruction2.png)

</details>


## Analog to Digital Signal Sampling
这个涉及到log有涉及到很多乱七八糟的计算，感觉不会出，如果出了纯粹他没屁眼.

## Anti Aliasing

Aliasing:
Aliasing occurs when higher frequency components in a signal appear as lower frequencies in the sampled signal, leading to distortion. This happens when the signal is sampled below its Nyquist rate.

Loss of the Tail:
The "loss of the tail" refers to the attenuation or elimination of signal components beyond a certain frequency, which can lead to missing information or signal distortion.

We can eliminate these components before sampling. Such supression of higher frequencies can be accomplished by an ideal lowpass filter of cutoff $\frac{f_s}{2} \textrm{Hz}$. This is called the anti aliasing filter

![](./assets/imgs/cs-analogtodigital.png)

# Z-Transform

The Z-Transform of a discrete time signal $x[n]$ is a generalization of the DTFT(Discrete-Time-Fourier Transform) of $x[n]$ and is defined as

$$X(z) = \sum_{n=-\infty}^{\infty}x[n]z^{-n}$$

Where $z$ is a complex number, in its general form, on the complex Z-plane

$$z=  re^{j\omega}$$

> $r$ is the magnitude $|z|$

We denote the Z-Transform of $x[n]$ as

$$x[n] \Longleftrightarrow X(z)$$

## Relationship between DTFT and Z-Transform

![](./assets/imgs/cs-relationshipztransform.png)

## ROC of Z-Transform

The ROC of Z-transform is a set of points $z$ for which $X(z)$ converges to bounded  value:

$$X(z) < \infty \rightarrow \sum_{n=-\infty}^{\infty} |x[n]|r^{-n} < \infty$$

## Z-Transform Table
![](./assets/imgs/cs-ztransformtable.png)

## Z-Transform Properties

![](./assets/imgs/cs-ztransformproper.png)

## Convergence of some series

Geometric Series 

$$\sum_{n=0}^{\infty}ar^n$$

Convergence Condition $|r| < 1$

Converges to $\frac{a}{1-r}$

## Complex Number Reminder
![](./assets/imgs/cs-complexnumber.png)
