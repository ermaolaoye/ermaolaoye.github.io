# Axioms and Properties of Real Numbers
## Definition of the Set of Real Numbers
**DEFINITION 1.** A set $\mathbb{R}$ is called the set of *real numbers* and its elements are *real numbers* if the following list of condition holds

**(I) AXIOMS FOR ADDITION**

$$+ : \mathbb{R} \times \R \to \R$$

The operation of addition is defined, assigning to each ordered pair $(x,y)$ of elements $x,y$ of $\R$ a certain element $x+y \in \R$, called the sum of $x$ and $y$.

This operation satisfies the following conditions:
1. There exists a neutral, or identity element 0 such that
    - $x + 0 = 0 + x = x$ for every $x \in \R$
2. For every element $x\in \R$ there exists an element $-x \in \R$ called the negative of $x$ such that
    - x + (-x) = (-x) + x = 0
3. The operation $+$ is associative,
    - $x + (y + z) = (x + y) + z$ for any elements $x,y,z \in \R$
4. The operation $+$ is commutative
    - $x + y = y + x$, for any elements $x,y \in \R$

**(II) AXIOMS FOR MULTIPLICATION** 

$$\bullet : \R \times \R \to \R$$

The operation of multiplication is defined, assigning to each ordered pair $(x,y)$ of elements $x,y$ of $\R$ a certain element $x\cdot y \in \R$, called product of $x$ and $y$. This operation satisfies the following conditions

> Small note, $\R \setminus 0$ means all the real numbers excluding 0

1. There exists a neutral, or identity element $1 \in \R \setminus 0$ such that
    - $x \cdot 1 = 1 \cdot x = x$ for every $x \in \R$
2. For every element $x \in \R \setminus 0$ there exists an element $x^{-1} \in \R$, called the inverse or reciprocal of $x$
    - $x \cdot x^{-1} = x^{-1} \cdot x = 1$
3. The operation $\cdot$ is associative
    - $x \cdot (y \cdot z) = (x \cdot y) \cdot z$ for any elements $x,y,z \in \R$
4. The operation $\cdot$ is commutative
    - $x \cdot y = y\cdot x$ for any elements $x, y$ in $\R$

Multiplication is distributive with respect to addition $(x + y) z = xz + yz$

**(III)ORDER AXIOMS** 

For elements $x,y \in \R$, one can determine whether $x \leq y$ or not. The following condition must hold:

1. $\forall x \in \R (x \leq x)$
2. $(x\leq y) \wedge (y\leq x) \Rightarrow (x=y)$
3. $(x\leq y) \wedge (y\leq z) \Rightarrow (x\leq z)$
4. $\forall x \in \R \forall y \in \R(x\leq y) \vee(y\leq x)$

The relation $\leq$ on $\R$ is called inequality.

If the axioms 1,2,3 hold, the set is partially ordered.

If in addition axiom 4 hold, the set is linearly ordered.

Thus, the set of real numbers is linearly ordered.

If $x,y,z$ are elements of $\R$, then $(x\leq y) \Rightarrow (x+z \leq y + z)$

If $x, y$ are elements of $\R$, then $(0 \leq x) \wedge (0 \leq y) \Rightarrow (0 \leq x \cdot y)$

**(IV) The AXIOM OF COMPLETENESS(CONTINUITY)** 

If $X,Y$ are nonempty subsets of $\R$ having the property that $x\leq y$ for every $x \in X, y\in Y$, then there exist $c \in \R$ such that $x \leq c \leq y$ for all $x\in X, y\in Y$

## Algebraic Properties of Real Numbers

### Addition Axioms
1. There is only one zero in the set of real numbers
2. Each element of the set of real numbers has a unique negative
3. In the set of real numbers $\R$ the equation $a +x = b$ has the unique solution $x = b + (-a)$

### Multiplication Axioms
1. There is only one multiplicative unit in the real numbers
2. For each $x \neq 0$ there is only one reciprocal $x^{-1}$
3. For $a\in \R \setminus 0$, the equation $a\cdot x = b$ has the unique solution $x = b\cdot a^{-1}$

### Addition and Multiplication Axioms
1. For any $x\in\R$, $x \cdot 0 = 0 \cdot x = 0$
2. $(x\cdot y = 0) \Rightarrow (x = 0) \vee (y=0)$
3. For any $x\in \R$, $-x = (-1)\cdot x$
4. For any $x\in \R$, $(-1)(-x) = x$
5. For any $x\in\R$, $(-x)\cdot(-x) = x\cdot x$

### Connecting Axioms
1. For any $x$ and $y$ in $\R$ precisely one of the following relations holds:
    - $x < y,\ \ \  x = y, \ \ \ x>y$
2. For any $x,y,z \in \R$
    - $(x < y) \wedge (y \leq z) \Rightarrow ( x < z)$
    - $(x \leq y) \wedge (y < z) \Rightarrow ( x < z)$

### Connecting with Addition and Multiplication Axioms

1. For any $x,y,z,w \in \R$
    - $(x < y) \Rightarrow (x + z) < (y + z)$
    - $(0 < x) \Rightarrow (-x < 0)$
    - $(x \leq y) \wedge (z \leq w) \Rightarrow (x+z)\leq (y+w)$
    - $(x \leq y) \wedge (z < w) \Rightarrow (x + z) < (y + w)$
2. If $x,y,z \in \R$
    - $(0 < x) \wedge (0 < y) \Rightarrow (0 < xy)$
    - $(x < 0) \wedge (y < 0) \Rightarrow (0 < xy)$
    - $(x < 0) \wedge (0 < y) \Rightarrow (xy < 0)$
    - $(x < y) \wedge (0 < z) \Rightarrow (xz < yz)$
    - $(x < y) \wedge (z < 0) \Rightarrow (yz < xz)$
3. $0 < 1$
4. $(0 < x) \Rightarrow (0 < x^{-1})$ and $(0 < x) \wedge (x < y) \Rightarrow (0 < y^{-1}) \wedge (y^{-1} < x^{-1})$

## Bounded Completeness Axiom
**DEFINITION 2.** A set $X \subset \R$ is said to be bounded above(resp. bounded below) if there exists a number $c \in \R$ such that $x \leq c$ (resp. $c \leq x$) for all $x \in X$

**DEFINITION 3.** A set that is bounded both above and below is called bounded.

**DEFINITION 4.** An element $a \in X$ is called the largest and maximal (resp. smallest or minimal) element of $X$ if $x \leq a$ (resp. $a \leq x$) for all $x \in X$

$$(a = \max X) := (a\in X \wedge \forall x \in X(x \leq a))$$
$$(a = \min X) := (a\in X \wedge \forall x \in X(a \leq x))$$

**DEFINITION 5.** The smallest number that bounds a set $X \subset \R$ from above is called the least upper bound (or the exact upper bound) of $X$ and denoted $\sup X$("the supremum of X")

$$(s = \sup X) := \forall x \in X((x \leq s) \wedge (\forall s' < s \exist x' \in X( s' < x')))$$

> The expression in the first set of parentheses on the right-hand side here says that $s$ is an upper bound for $X$; the expression in the second set says that $s$ is the smallest number having this property. More precisely, the expression in the second set of parentheses asserts that any number smaller than $s$ is not an upper bound of $X$.

![](./assets/imgs/cs-2-supremum.png)

**DEFINITION 6.** 

$$(i = \inf X) := \forall x \in X ((i \leq x) \wedge (\forall i' > i \exist x' \in X (x' <i')))$$

$\inf X$ (read "the infimum of X") represents the greatest lower bound of X.

Thus, we have

$$\sup X := \min \{c \in \R| \forall x \in X (x \leq c)\}$$
$$\inf X := \max \{c \in \R| \forall x \in X (c \leq x)\}$$

----
**Lemma** 

Every nonempty set of real-numbers that is bounded from above has a unique least upper bound.

----
**Lemma** 
$$(X \textrm{ bounded below})\Rightarrow (\exist!\inf X)$$

# Classes of Real Numbers and Computational Aspects of Operations with Real Numbers

## Natural Numbers
The number $1,2,3,\cdots$ are *natural numbers*

**DEFINITION 1** 

A set $X \subset \R$ is inductive if for each number $x \in X$, it also contains $x+1$

For example, $\R$ is an inductive set; the set of positive numbers is also inductive.

The intersection $X = \cap_{a\in A} X_a$ of any family of inductive sets $X_a$, if not empty, is an inductive set.

$$(x\in X = \cap_{a\in A} X_a) \Rightarrow (\forall a \in A(x\in X_a)) \Rightarrow$$

$$(\exists a \in A((x+1)\in X_a)) \Rightarrow ((x+1)\in \cap_{a\in A} X_a = X)$$

**DEFINITION 2** 

The set of natural numbers is the smallest inductive set containing 1, that is, the intersection of all inductive sets that contain 1.

The set of natural numbers is denoted $\N$, its elements are called natural numbers

From the set-theoretic point of view, it might be more rational to begin the natural numbers with 0.

## The Principle of Mathematical Induction
If a subset $E$ of the set of *natural numbers* $\N$ is such that $1\in E$ and together with each number $x\in E$, the number $x+1$ also belongs to $E$, then $E = \N$

Thus

$$(E\subset \N) \wedge(1\in E) \wedge(\forall x \in E(x \in E \Rightarrow (x+1)\in E)) \Rightarrow E = \N$$
