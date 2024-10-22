# Math Def in Prior
**Basis Vector** A set of basis vectors in a vector space is a minimal set of vectors that span the entire space. Any vector in the space can be expressed as a linear combination of these basis vectors.

**Basis Function** In function spaces, basis functions are analogous to basis vectors but applied to functions. They are a set of functions that can be combined(usually linearly) to represent any function within a certain space.

# Discrete Data Transmission

![](./assets/imgs/1-discretedt.png)

Messages are digital sequences of bits(Discrete data)
- Need to be converted to waveforms to get through the communication channel.

Transmitter: Converts discrete data into analog electrical signals(waveforms) that can be sent through the channel

Receiver: Receives the distorted waveforms and tries to recvover the sent messages.(Digital sequence of bits)


**Examples**:
- Ethernet, WiFi, Cable TV

![](./assets/imgs/1-discreteedt2.png)

## Message Source Process

$M$ represents the total number of elements in the sequence.

Message Source: Contains a finite set of messages $\{m_i\}^{M-1}_{i=0}: m_0,m_1, m_2, \dots, m_{M-1}$
- Messages: A digital sequence of bits (e.g.$m_5=$ 0b101)

The number of transmitted bits per message is $b = \log_2 M$

Every $T$ seconds, one of the mssages is transmitted.

Data Rate: Number of transmitted bits per second

$$R = \frac{b}{T} = \frac{\log_2 M}{T} \ \textrm{bits/sec}$$

## Transmission and Reception Process

Transmitter maps each message $m_i$ to a suitable continuous time waveforms $x_i(t)$, **Encoding and Modulation** $[m_i \to x_i(t)]$

Channel distorts and modifies the transmitted waveform $x_i(t)$ and outputs a corrupted waveform $y(t)$

Receiver maps $y(t)$ to an estimated message $\hat{m}$: **Demodulation and Detection** $[y(t) \to \hat{m}]$

----

**What are those suitable continuous-time waveforms and how they are chosen?** 

$x_i(t)$ must be chosen based on channel behavior

Example: Want to transmit a binary message 0 or 1, hence M = 2, and $b = \log_2 M = \log_2 2 = 1, m_0 = 0, m_1 = 1$. Transmit the binary message through the channel:

$$H(f) = \begin{cases} 1, 100 \textrm{Hz} < |f| < 200 \textrm{Hz} \\ 0, \textrm{Otherwise} \end{cases}$$

### Encoder

The encoder maps each message $m_i$ to an N-dimensional real-valued vector: $m_i \to \boldsymbol{x}_i, i = 0, 1, \dots, M-1$

$$\boldsymbol{x}_i \overset{\Delta}{=} \begin{bmatrix}x_{i1} \\ x_{i2} \\ \dots \\ x_{iN}\end{bmatrix} = \begin{bmatrix}x_{i1} &x_{i2} &\dots &x_{iN}\end{bmatrix}^T$$

$\boldsymbol{x}_i$ is called the $i$-th data symnbol corresponding to the $i$-th message $m_i$

The set of vectors $\{\boldsymbol{x}_i\}^{M-1}_{i=0}: \boldsymbol{x}_0, \boldsymbol{x}_1, \boldsymbol{x}_2, \dots, \boldsymbol{x}_{M-1}$ is called Signal Constellation

### Modulator

A set of $N$ functions $\{\varphi_n(t)\}^N_{n=1}$ is called a set of $N$ orthonormal basis functions if:

$$\int_{-\infty}^{\infty}\varphi_n(t) \varphi_m(t) dt = \delta_{nm} = \begin{cases} 1, \textrm{if }n=m \\ 0, \textrm{if } n \neq m\end{cases}$$

- The different function in the set are orthogonal if their inner product is zero,  mathematically when their inner product, i.e. when $\int_{-\infty}^{\infty} \varphi_n(t)\varphi_m(t) dt = 0\ \textrm{if } n \neq m$
- Each function in the set has a norm(magnitude) of 1: $\int_{-\infty}^{\infty} \varphi_n(t)\varphi_n(t) = 1\ \textrm{if }n = m$

and $\varphi_{nm}$ is called a Kronecker delta.

- Kronecker delta is a function for describing the orthogonality property.

Given a set of $N$ orthonormal basis functions $\{\varphi_n(t)\}^N_{n=1}$, a modulator maps the $i$-th data symbol $\boldsymbol{x}_i$ to the $i$-th modulated waveform $x_i(t)$, $\boldsymbol{x}_i \to x_i(t)$ as:

$$x_i(t) = \sum_{n=1}^{N}x_{in}\varphi_n(t)$$

![](./assets/imgs/1-modulatorstructor.png)

#### Inner Product

Inner Product in Vector Space: The inner product of two $N$-dimensional real-valued vectors $\boldsymbol{u} = [u_1u_2 \dots u_N]^\boldsymbol{T}$ and $\boldsymbol{v} = [v_1v_2 \dots v_N]^T$ is defined as 

$$<\boldsymbol{u,v}> \overset{\Delta}{=} \sum_{n=1}^{N}u_nv_n$$
- $\boldsymbol{u,v}$ is orthogonal if $<\boldsymbol{u,v}> = 0$ (For Euclidean Vectors, it is dot product)
- Sqaured-legnth of a vector $\boldsymbol{u}: ||\boldsymbol{u}||^2 = <\boldsymbol{u,u}>$

Inner Product in Continuous-Time Signal Domain: The inner product of two real-valued functions $u(t)$ and $v(t)$ is defined as:
$$<u(t), v(t)> \overset{\Delta}{=}\int_{-\infty}^{\infty}u(t)v(t)dt$$

Considering sampling of a continuous-time function $u(t)$ with infinitely small sampling period of $dt$.
- Given these infinite number of samples, $u(t)$ can be viewed as an infinite dimensional real-valued vector.

The squared-norm of a real valued $u(t)$ is:
$$||u(t)||^2 = <u(t), v(t)> = \int_{-\infty}^{\infty} u^2(t)dt$$

Hence, for modulator, the definition of $N$ orthonormal basis functions $\{\varphi_n(t)\}^N_{n=1}$ as:

$$\int_{-\infty}^{\infty}\varphi_n(t)\varphi_m(t) dt = \delta_{nm} = \begin{cases} 1 \textrm{ if } n = m\\ 0 \textrm{ if } n\neq m \end{cases}$$

> For $n=m$ is basically asking for squared-norm(squared magnitude), and for normalised values, it should be 1. For $n \neq m$ is asking for dot product, and it should be 0 when they are orthogonal

It can be interpreted in terms of inner product as:

$$< \varphi_n(t), \varphi_m(t)> = \begin{cases} 1 \textrm{ if }n = m\\0 \textrm{ if }n \neq m \end{cases}$$

---

**THEOREM** Given a set of orthonormal basis functions $\{\varphi_n(t)\}^N_{n=1}$ and two continuous-time functions $u(t)$ and $v(t)$, such that:

$$u(t) = \sum_{n=1}^{N}u_n\varphi_n(t), v(t) = \sum_{n=1}^{N}v_n\varphi_n(t)$$

for some N, then:

$$<u(t), v(t)> = <\boldsymbol{u, v}> = \sum_{n=1}^{N}u_nv_n$$

where:

$$\boldsymbol{u} \overset{\Delta}{=} \begin{bmatrix}u_1\\u_2\\\dots\\u_N\end{bmatrix}, \boldsymbol{v} \overset{\Delta}{=} \begin{bmatrix}v_1\\v_2\\\dots\\v_N\end{bmatrix}$$

<details>
<summary>PROOF</summary>

![](./assets/imgs/1-proof1.png)

</details>


### Transmitter in General

Transmitter action: $m_i \overset{\textrm{Encoder}}{\longrightarrow} \boldsymbol{x_i} \overset{\textrm{Modulator}}{\longrightarrow}x_i(t)$

The set of modulated waveform $\{x_i(t)\}^{M-1}_{i=0}$ is called the **signal set**.
