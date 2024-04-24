# Binary System
# Boolean Algebra
The operator '.' has precedence over '+'
## Single Variable Theorems
- $X + 0 = X, X.1 = X$ (Identitiees)
- $X+1 = 1, X.0 = 0$ (Null elements)
- $X+X = X, X.X = X$ (Idempotency)
- $(X')' = X$ (Involution)
- $X + X' = 1, X.X' = 0$ (Complements)

## Two/three Variable Theorems
- $X + Y = Y + X, X.Y = Y.X$ (Commutativity)
- $(X+Y) + Z = X + (Y + Z), (X.Y).Z = X.(Y.Z)$ (Associativity)
- $X.Y + X.Z = X. (Y + Z), (X + Y) . (X + Z) = X + (Y . Z)$ (Distributivity)
- $X + X.Y = X, X.(X+Y) = X$ (Covering)
- $X . Y + X.Y' = X, (X+Y).(X+Y') = X$ (Combining)
- $X.Y+X'.Z+Y.Z = X.Y + X'.Z, (X+Y).(X'+Z).(Y+Z) = (X+Y).(X'+Z)$ (Consensus)

<details>
<summary>Proof of Consensus Theorem</summary>

![](./assets/imgs/cs-proofofconsensus.png)

</details>

## Canonical Forms
Boolean functions can be expressed in canonical form

> Sum 就是 OR, Product 就是 AND

Minterm - Each term in Sum of Product canonical expression
- 把1的term全部Sum起来

Maxterm - Each term in Product of Sum canonical expression
- 把0的term全部Product起来

![](./assets/imgs/cs-canonicalexpression.png)

![](./assets/imgs/cs-canonicalexpression2.png)

### Converting SoP and PoS

Interchange the symbol and list numbers missing from original form

![](./assets/imgs/cs-convertingsoppos.png)

## Minimising Boolean Functions
### De Morgan's Theorem
$$\overline{X_1 + X_2} = \overline{X_1} . \overline{X_2}$$

$$\overline{X_1 . X_2} = \overline{X_1} + \overline{X_2}$$

### Karnaugh Map
There may be more than one way to simplify using K-map

![](./assets/imgs/cs-karnaughmap.png)

只圈最少的1、4、8方块。

# Combinational Logic Circuit
Usually inverting gates NOT NAND NOR are faster than non-inverting gates AND NOT OR
## Logic Gates
De Morgan's Theorem can be used to produce alternative logic gates.
### AND Gate
![](./assets/imgs/cs-andgate.png)

![](./assets/imgs/cs-andgatetruthtable.png)

### OR Gate
![](./assets/imgs/cs-orgate.png)

![](./assets/imgs/cs-orgatetruthtable.png)

### NOT Gate
![](./assets/imgs/cs-notgate.png)

### NAND Gate
![](./assets/imgs/cs-nandgate.png)

![](./assets/imgs/cs-nandgatetruthtable.png)

### NOR Gate
![](./assets/imgs/cs-norgate.png)

![](./assets/imgs/cs-norgatett.png)

### XOR and XNOR Gate
2 input XOR: Output is high only if both inputs are different

![](./assets/imgs/cs-xorgate.png)

This gate can be implement using NAND gate

$$X \oplus Y = XY' + X'Y = XY' + XX' + X'Y + YY' = (X' + Y')X + Y(X'+Y')$$

$$= \overline{\overline{(X.Y)'.X}.\overline{(X.Y)'.Y}}$$

----

2 input XNOR: Output is high only if both inputs are same

$$\overline{X \oplus Y} = (X'+Y)(X+Y') = XY + X'Y'$$

![](./assets/imgs/cs-xnorgate.png)

----

n-input XOR - output high when inputs have odd number of 1's -parity checker

n-input XNOR - output high when inputs have even number of 1's

Implement using NAND gate can save elements

![](./assets/imgs/cs-usingnandgate.png)

![](./assets/imgs/cs-xorkarnaughmaps.png)

The following circuit is a Even-Parity-Generator, which generate a parity bit for a given set of data bits. Its objective is to ensure that the total number of 1s including the parity bit is even.

![](./assets/imgs/cs-xortruthtables.png)

The following circuit is a Even-Parity-Checker is to check the received data includes the parity bit, determine whether an error has occured during transmission.

> For instance, if the parity bit is 1 indicating an odd parity, however the received bits are not odd, it indicates an transmission error.

![](./assets/imgs/cs-evenparitychecker.png)

<details>
<summary>Combinational logic analysis example</summary>

![](./assets/imgs/cs-combinationlogicexp1.png)

![](./assets/imgs/cs-combinationalogicexp2.png)

![](./assets/imgs/combinationalogicexp3.png)
</details>

# Combinational Logic Synthesis
- From problem specification identify the inputs and outputs
- Obtain boolean function for each output as function of input variables
    - Directly from problem statement
    - Constructing the truth table
- Simplify the Boolean function using Karnaugh map or alegbraic manipulation
- Draw logic circuit diagram and verify correct operation

## Direct Implementation
For example, we derive a boolean function $F = A'BC + B'C' + AD$

![](./assets/imgs/cs-directimple.png)

## Implement using NAND gates
NAND gate are typically faster

We can use DeMorgan's Theorem to transform:

$$F = A'BC + B'C' + AD$$

$$= \overline{\overline{A'BC + B'C' + AD}}$$

$$= \overline{\overline{(A'BC)}.\overline{(B'C')}\overline{(AD)}}$$

![](./assets/imgs/cs-implementnand.png)

<details>
<summary>Question 4.1</summary>

(a)Rewrite A+B using 2 NOT and 1 NAND Operator

$$A+B = \overline{\overline{A+B}} = \overline{\overline{A}.\overline{B}}$$

![](./assets/imgs/cs-question41.png)

(b)Rewrite A+B+C+D using only NOT and two-input NAND operator

$$A+B+C+D = \overline{\overline{A+B}}$$

![](./assets/imgs/cs-question412.png)

</details>

## Bubble to Bubble Logic
Transform the logic gate to nandgate by replacing using alternative symbols.

![](./assets/imgs/cs-bubbletobubble.png)

## Implement using NAND gates second method
Remember that the following gates are equivalent

![](./assets/imgs/cs-nandequivalentgate.png)

- Draw the circuit using AND or OR gate
- Change every AND to NAND, OR to NOR
- Check for complements
- Change XOR to NAND

<details>
<summary>Example</summary>

![](./assets/imgs/cs-nandgateexample.png)

![](./assets/imgs/cs-nandgateexample2.png)

![](./assets/imgs/cs-nandgateexample3.png)

</details>

## Minimisation using Karnaugh Map

Construct the truth table for each output, and then write down canonical expression

![](./assets/imgs/cs-minimisationusingkarnaugh.png)

![](./assets/imgs/cs-minimisationusingkarnaugh2.png)

![](./assets/imgs/cs-minimisationusingkarnaugh3.png)

Multiple output require multiple karnaugh map for each output

![](./assets/imgs/cs-multipleoutput.png)

![](./assets/imgs/cs-multipleoutput2.png)

![](./assets/imgs/cs-multipleoutput3.png)

# Medium Scale Combinational Logic Circuits

## Multiplexers

MUX are combinational devices with several input lines and one output line

![](./assets/imgs/cs-mux.png)

![](./assets/imgs/cs-mux2.png)

![](./assets/imgs/cs-mux3.png)

![](./assets/imgs/cs-mux4.png)

## Adder

![](./assets/imgs/cs-binaryaddition.png)

When two binary number are added together, S is the sum bit, C is the carry out bits

### Half Adder

![](./assets/imgs/cs-halfadder.png)

### Full Adder

![](./assets/imgs/cs-fulladder.png)

![](./assets/imgs/cs-fulladder2.png)

### Parallel/Ripple Adder

![](./assets/imgs/cs-parallelrippleadder.png)

### Subtractors

![](./assets/imgs/cs-subtractors.png)

### Adder Delay

![](./assets/imgs/cs-adderdelay.png)

## Decoder

![](./assets/imgs/cs-decoder.png)

## Encoder

![](./assets/imgs/cs-encoder.png)

![](./assets/imgs/cs-encoder2.png)

## Comparator

![](./assets/imgs/cs-comparator.png)

![](./assets/imgs/cs-comparator2.png)
