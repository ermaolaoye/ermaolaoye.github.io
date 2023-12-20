# Table of Contents
<!-- toc -->
----

# Vector and Vector Space
Vector space(linear space) is a set of vectors which may be added together and multiplied by scalars.
## Vector Properties
### Properties of Vector Addition
- Associativity: $\vec{a} + (\vec{b} + \vec{c}) = (\vec{a} + \vec{b}) + \vec{c}$
- Commutativity: $\vec{a} + \vec{b} = \vec{b } + \vec{a}$
- Additive Inverse: $\vec{a } + (- \vec{a}) = 0$
### Properties of Scalar Multiplication
- Associativity: $k(t \vec{a}) = (kt) \vec{a}$
- Distributivity over vector addition: $k(\vec{a} + \vec{b }) = k \vec{a} + k \vec{b}$
- Distributivity over scalar addition: $(k+t) \vec{a} = k \vec{a} + t \vec{a}$
### Linear combination
A vector $\vec{a} \in \R^n$ is a linear combination of the vectors $\vec{v}_1, \dots, \vec{v }_m \in \R^n$ if 
$$\vec{a } = k_1 \vec{v }_1 + k_2 \vec{v }_2 + \dots + k_m \vec{v}_m$$
### Linear Independence 
A set of vectors $\vec{v}, \dots, \vec{v}_m \in \R^n$ is linearly independent if no vector can be written as a linear combination of the others, i.e.
$$k_1 \vec{v}_1 + k_2 \vec{v}_2 + \dots + k_m \vec{v }_m = \vec{0}$$

就是比如[1,2]和[2,4]，其中后者可以写作2[1,2]，这就说明他们是linear dependent的。如果一个set里面所有的vector都不能写作其他vector乘以scalar，那他们就是linearly independent的

Which also implies that $k_1 = k_2 = \dots = k_m = 0$

### Basis
A basis for $\R^n$ is a set of linearly independent unit vectors $\vec{e}_1, \dots, \vec{e}_n \in \R^n$ span the whole of $\R^n$ such that for any $\vec{a}\in \R^n$
$$\vec{a } = a_1 \vec{e}_1 + a_2 \vec{e}_2 + \dots + a_n \vec{e}_n$$

In 3-dimensional $\R^3$, we choose three vectors as the standard basis $\vec{i}, \vec{j}, \vec{k}$

## Vector Calculation
### Vector Magnitude
The lenght of the vector is defined using Pythagoras' Theorem
$$||\vec{a}|| = \sqrt{a^2_1 + a^2_2 + a^2_3}$$

we use $||a||$ to distinguish vectors from real numbers
### Dot Product
Given two vectors $\vec{a}, \vec{b} \in \R^n$, we define their dot product to be
$$\vec{a} \cdot \vec{b} = \begin{bmatrix}a_1 \\ a_2 \\ a_3\end{bmatrix} \cdot \begin{bmatrix}b_1 \\ b_2 \\ b_3\end{bmatrix} = a_1b_1 + a_2b_2 + a_3b_3$$

Dot product have Commutativity, Linearity, Distributivity

**Equivalent Form**

Let $\vec{a},\vec{b} \in \R^n$ be any two vectors, and let $\theta$ be the angle between them, then
$$\vec{a} \cdot \vec{b} = ||\vec{a}||\ ||\vec{b}|| \cos \theta$$

**The Cauchy-Schwarz Inequality**

Let $\vec{a},\vec{b} \in \R^n$ be any two vectors, then
$$|\vec{a }\cdot \vec{b} | \leq ||\vec{a}||\ ||\vec{b}|| $$

Basically, the dot product is never larger than the product of the lengths
### Cross Product
Let $\vec{a} = a_1 \vec{i} + a_2 \vec{j} + a_3 \vec{k}$ and $\vec{b} = b_1 \vec{i} + b_2 \vec{j} + b_3 \vec{k}$ be any two vectors in $\R^3$, then their cross product is given by
$$\vec{a } \times \vec{b } = \begin{vmatrix}\vec{i } &\vec{j } &\vec{k } \\ a_1 &a_2  &a_3  \\ b_1  &b_2 &b_3\end{vmatrix} = \begin{vmatrix}a_2 &a_3 \\ b_2 &b_3\end{vmatrix}\vec{i} + \begin{vmatrix}a_1 &a_3\\b_1 &b_3\end{vmatrix} \vec{j} + \begin{vmatrix}a_1 &a_2 \\ b_1 &b_2\end{vmatrix} \vec{k}$$
$$= (a_2b_3 - a_3b_2) \vec{i} - (a_1b_3 - a_3b_1)\vec{j} + (a_1b_2 - a_2b_1)\vec{k}$$

where $|\boldsymbol{A}|$ denotes the determinant of the matrix $\boldsymbol{A}$

Cross product has linearity and distributivity but anti-commutivity $\vec{a } \times \vec{b} = -(\vec{b} \times \vec{a})$

**Equivalent Form**

Let $\vec{a }, \vec{b} \in \R^3$ be any two vectors, and let $\theta$ be the angle between them, then
$$||\vec{a}\times \vec{b}|| = ||\vec{a}||\ ||\vec{b}|| \sin \theta$$

**Area of Parallelogram**

The length of the vector $\vec{a} \times \vec{b}$ is equal to the area of the parallelogram spanned by $\vec{a}, \vec{b}$
# Scalar and Vector Fields
## Scalar Fields
就是在这个field的每一个点都是一个scalar

A scalar field on $\R^n$ is a real-valued function
$$f:\R^n \to \R$$
That assigns a scalar to every point of the vector space $\R^n$

Example: $f(x,y) = e^{-(x^2+y^2)}$

![](./assets/imgs/scalarfields.png)

## Vector fields
就是在这个field的每一个点都是一个vector

A **vector field** on $\R^n$ is a vector-valued function
$$\vec{F}: \R^n \to \R^n$$
that assigns a vector from $\R^n$ to every point of the vector space $\R^n$

Example: $\vec{F}(x,y) = y \vec{i}- x \vec{j}$
![](./assets/imgs/vectorfield.png)

## Component Functions
Vector field is often defined over $\R^3$ by 3 scalar valued functions $\boldsymbol{P, Q, R}$

$$\vec{F}(x,y,z) = \boldsymbol{P}(x,y,z)\vec{i} + \boldsymbol{Q}(x,y,z)\vec{j} + \boldsymbol{R}(x,y,z)\vec{k}$$
