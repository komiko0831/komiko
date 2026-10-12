---
title: "Introduction to Classical and Quantum Computing"
description: "Introduction to Classical and Quantum Computing reading notes"
slug: introduction-to-classical-and-quantum-computing
date: 2026-08-15 00:00:00+0000
categories:
    - 量子计算
tags:
    - note
    - quantum
math: true
---

## chapter 1

![image-20260910160613021](/images/introduction-to-classical-and-quantum-computing/image-20260910160613021.png)

### 1.Reverible

The equality of input and output is a necessary but not sufficient condition for the reversibility of a logic gate

#### 1.1Toffoli Gate: A Reversible AND Gate

![image-20260910160904614](/images/introduction-to-classical-and-quantum-computing/image-20260910160904614.png)

#### 1.2Making Irreversible Gates Reversible

Say a gate has inputs A and B and one output f (A, B), which is a function that outputs 0 or 1 depending on the inputs A and B:

![image-20260910160849147](/images/introduction-to-classical-and-quantum-computing/image-20260910160849147.png)

To make it reversible, we add a fourth input D that we XOR with f (A, B,C):

![image-20260910160955569](/images/introduction-to-classical-and-quantum-computing/image-20260910160955569.png)

In the output, every permutation of A, B, and C shows up twice, once with \(f(A,B,C)\) and \(\overline{f(A,B,C)}\)

### 2.Error Correction

#### error-correcting code

* three physical bits:

let p denote the probability of a single bit flipping

![image-20260910161653261](/images/introduction-to-classical-and-quantum-computing/image-20260910161653261.png)

the repetition code with three bits is better when the probability of a single bit flip is

$$
0 \lt p \lt \frac{1}{2}, p \gt 1
$$

Since p is a probability, it cannot be less than 0 or greater than 1. So, the 3-bit repetition code is better than no error correction when

$$
p \lt \frac{1}{2}
$$

### 3.Computational Complexity

![image-20260910162114213](/images/introduction-to-classical-and-quantum-computing/image-20260910162114213.png)

* class P：Problems that can be solved efficiently (in polynomial time) by a classical computer

* class NP ：the problems for which a solution can be quickly verified by a computer in polynomial time.

### summary

The smallest unit of classical information is the bit, which has two possible states, 0 or 1. Bits can be used to encode information, such as using ASCII. Bits are operated on by logic gates, including NOT, AND, OR, XOR, NAND, and NOR. Together, these gates can be used to perform any computation, and subsets of these gates are also universal, such as {NOT, AND, OR} and {NAND}. The mathematics that describes logic gates is called boolean algebra. Logic gates can be made reversible, and

the Toffoli gate is a reversible version of the AND gate. In physical systems, errors sometimes occur, but as long as the error rates are sufficiently low, they can be corrected. Classical computers can efficiently solve some problems, while other problems take a superpolynomial amount of time. It is believed that quantum computers can efficiently solve some of the problems that are hard for classical computers.

## chapter2 ：One Quantum Bit

### 1

#### 1.1 zero or one

ket：\(|0\rangle, |1\rangle\)

We can visualize these distinct states, |0⟩ and |1⟩, as the north and south poles of a sphere of radius 1 called the Bloch sphere:

![image-20260910163622469](/images/introduction-to-classical-and-quantum-computing/image-20260910163622469.png)

|0⟩ corresponds to the (x, y, z) point (0, 0, 1), and |1⟩ corresponds to (0, 0, −1)

#### 1.2 superposition

$$
\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)
$$

![image-20260910164018762](/images/introduction-to-classical-and-quantum-computing/image-20260910164018762.png)

$$
\begin{gathered}
|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle),\\ |-\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle),\\ |i\rangle = \frac{1}{\sqrt{2}}(|0\rangle + i|1\rangle), \\|-i\rangle = \frac{1}{\sqrt{2}}(|0\rangle - i|1\rangle)
\end{gathered}
$$

![image-20260910164319638](/images/introduction-to-classical-and-quantum-computing/image-20260910164319638.png)

| A qubit can be any point on the Bloch sphere.

#### 1.3 Review of Complex Numbers

**Cartesian form**:

$$
\begin{gathered}
z = x + iy\\real component:\Re(z) = x
\\imaginary component:\text{Im}(z) = \Im(z) = y
\end{gathered}
$$

**polar form**:

$$
z = re^{i\theta}
$$

$$
r = \sqrt{x^2 + y^2} \quad
$$

$$
\theta = \tan^{-1} \left( \frac{y}{x} \right) \quad
$$

$$
x = r \cos \theta \quad
$$

$$
y = r \sin \theta
$$

![image-20260910165321143](/images/introduction-to-classical-and-quantum-computing/image-20260910165321143.png)

#### 1.4 Measurement in the Z-Basis

The probability is given by the norm-square of the amplitude.

Measurement collapses the qubit.

eg：

![image-20260910204524536](/images/introduction-to-classical-and-quantum-computing/image-20260910204524536.png)

#### 1.5 Normalization

We say a quantum state is normalized if its total probability is 1

#### 1.6 Measurement in Other Bases

In quantum mechanics, measurement is not a passive process of reading out a value, but rather the projection of a quantum state onto a specific basis. Any pair of antipodal points on the Bloch sphere can define a measurement basis.

The three common bases are:

| Basis Name  | States | Axis |
| :---------- | :----- | :--- |
| **Z-basis** | 0，1   | z    |
| **X-basis** | +，-   | x    |
| **Y-basis** | i，-i  | y    |

Where:

$$
|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle), \quad |-\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)
$$

$$
|i\rangle = \frac{1}{\sqrt{2}}(|0\rangle + i|1\rangle), \quad |-i\rangle = \frac{1}{\sqrt{2}}(|0\rangle - i|1\rangle)
$$

### 2.Bloch Sphere Mapping

#### 2.1 Global and Relative Phases

$$
∣e^{iθ}∣=1
$$

Global phases are physically irrelevant.

#### 2.2 Spherical Coordinates

A generic quantum state

$$
\begin{gathered}
|\psi\rangle=\alpha|0\rangle+\beta|1\rangle\\|\alpha|^2 + |\beta|^2 = 1
\end{gathered}
$$

$$
\begin{gathered}
\alpha = \cos\left(\frac{\theta}{2}\right), \quad \beta = e^{i\phi}\sin\left(\frac{\theta}{2}\right).\\|\psi\rangle = \cos\left(\frac{\theta}{2}\right)|0\rangle + e^{i\phi}\sin\left(\frac{\theta}{2}\right)|1\rangle
\end{gathered}
$$

**Conversion from State to Angle:** Given a qubit state, it needs to be expressed in the standard form \(\cos\left(\frac{\theta}{2}\right)|0\rangle + e^{i\phi} \sin\left(\frac{\theta}{2}\right)|1\rangle\), and then identify \(\theta\) and \(\phi\).

**Cartesian Coordinates:** Points on the sphere can also be represented using Cartesian coordinates \((x, y, z)\) as follows:

$$
x = \sin \theta \cos \phi
$$

$$
y = \sin \theta \sin \phi
$$

$$
z = \cos \theta
$$

### 3. quantum gates

Quantum gates act on qubits, like logic gates act on bits.We use capital letter U to denote a quantum gate

For this to be a valid quantum gate, the total probability must remain 1\(|\alpha|^2 + |\beta|^2 = 1\)

#### 3.1Classical Reversible Gates

A classical logic gate is reversible if its outputs are unique.

How would this gate act on a qubit? It would map the following:

$$
\begin{gathered}
\mathrm{Gate}|0\rangle = |1\rangle\\
\mathrm{Gate}|1\rangle = |0\rangle\\
\text{Gate}\left(\alpha|0\rangle+\beta|1\rangle\right)=\alpha|1\rangle+\beta|0\rangle=\beta|0\rangle+\alpha|1\rangle\\|\beta|^2 + |\alpha|^2 = |\alpha|^2 + |\beta|^2 = 1
\end{gathered}
$$

Consider a irreversible gate:

$$
\begin{gathered}
\mathrm{Gate}|0\rangle = |0\rangle\\
\mathrm{Gate}|1\rangle = |0\rangle\\\operatorname{Gate}(\alpha|0\rangle+\beta|1\rangle)=\alpha|0\rangle+\beta|0\rangle=(\alpha+\beta)|0\rangle\\|\alpha+\beta|^2 = |\alpha|^2 + |\beta|^2 + \alpha^*\beta + \alpha\beta^* = 1 + \alpha^*\beta + \alpha\beta^* \neq 1
\end{gathered}
$$

#### 3.2 Common One-Qubit Quantum Gates

* **identity gate**：

$$
\begin{gathered}
I|0\rangle = |0\rangle\\I|1\rangle = |1\rangle
\end{gathered}
$$

* **Pauli X gate**(or NOT gate):

$$
\begin{gathered}
X|0\rangle = |1\rangle\\\quad X|1\rangle = |0\rangle
\end{gathered}
$$

* **Pauli Y gate**:

$$
\begin{gathered}
Y|0\rangle = i|1\rangle\\
  Y|1\rangle = -i|0\rangle
\end{gathered}
$$

* **Pauli Z gate**:

$$
\begin{aligned} Z|0\rangle &= |0\rangle\\ Z|1\rangle &= -|1\rangle \end{aligned}
$$

* **Phase gate**：

$$
\begin{aligned} S|0\rangle &= |0\rangle \\ S|1\rangle &= i|1\rangle \end{aligned}
$$

* **T gate**:

$$
\begin{aligned} T|0\rangle &= |0\rangle \\ T|1\rangle &= e^{i\pi/4}|1\rangle \end{aligned}
$$

* **Hadamard gate**:

$$
\begin{gathered}
H|0\rangle = \frac{1}{\sqrt{2}}\left(|0\rangle + |1\rangle\right) = |+\rangle\\
  H|1\rangle = \frac{1}{\sqrt{2}}\left(|0\rangle - |1\rangle\right) = |-\rangle
\end{gathered}
$$

#### 3.3 General One-Qubit Gates

The quantum gates from the last section were rotations by some angle around some axis. This is true in general: **One-qubit quantum gates are rotations on the Bloch sphere.**

### 4.Quantum Circuits

#### 1.1

\(HSTH|0⟩\) is：

![image-20260915155416093](/images/introduction-to-classical-and-quantum-computing/image-20260915155416093.png)

A great web-based tool for simulating quantum circuits is Quirk at https://algassert.com/quirk:

![image-20260915160231406](/images/introduction-to-classical-and-quantum-computing/image-20260915160231406.png)

### 4.Summary

The smallest unit of quantum information is the qubit. Besides having two orthogonal states |0⟩ and |1⟩, a qubit can be a superposition of them with complex amplitudes. The norm-square of the amplitudes gives the probability of measuring the qubit as a 0 or 1, and depending on the outcome, the qubit collapses to |0⟩ or |1⟩. Qubits can also be measured in other bases. A qubit can be visualized on the Bloch 2.8 Summary 113  sphere. Qubits are operated on by quantum gates, which are linear maps that keep the total probability equal to 1. A single-qubit gate is a rotation on the Bloch sphere. A quantum circuit is a drawing to depict what quantum gates act on a qubit, and an online simulator for quantum circuits is Quirk.

## chapter3: Linear Algebra

### 3.1 Quantum States

#### 3.1.1 Column Vectors

We write \(|0\rangle\) and \(|1\rangle\) as column vectors, which are vertical lists of numbers:

$$
|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \qquad
|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}.
$$

Then any superposition can be written directly:

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
= \alpha\begin{pmatrix} 1 \\ 0 \end{pmatrix} + \beta\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= \begin{pmatrix} \alpha \\ \beta \end{pmatrix}.
$$

For example, \(|i\rangle\) can be written as a column vector:

$$
|i\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{i}{\sqrt{2}}|1\rangle
= \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}.
$$

#### 3.1.2 Row Vectors

The transpose of a column vector is a row vector, denoted by \(\top\) (a superscript letter T):

$$
\begin{pmatrix} \alpha \\ \beta \end{pmatrix}^\top = \begin{pmatrix} \alpha & \beta \end{pmatrix}.
$$

In quantum computing, we typically use the conjugate transpose, obtained by taking the complex conjugate of each component of the transpose. It is denoted by \(\dagger\) (a dagger):

$$
\begin{pmatrix} \alpha \\ \beta \end{pmatrix}^\dagger = \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix}.
$$

In bra-ket notation, this is written with an angle bracket and a vertical bar, called a bra:

$$
\langle\psi| = \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix}.
$$

A bra is the conjugate transpose of a ket, and a ket is the conjugate transpose of a bra. Flipping between kets and bras is called "taking the dual". For example, the Z-basis vectors as bras are:

$$
\langle0| = \begin{pmatrix} 1 & 0 \end{pmatrix}, \qquad
\langle1| = \begin{pmatrix} 0 & 1 \end{pmatrix}.
$$

Then \(\langle\psi|\) can be written as

$$
\langle\psi| = \alpha^*\langle0| + \beta^*\langle1|.
$$

**Note:** when going from \(|\psi\rangle\) to \(\langle\psi|\), we take the complex conjugate of the amplitudes.

**Summary: flipping between kets and bras**

$$
|\psi\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}
\;\Longleftrightarrow\;
\langle\psi| = \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix},
$$

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
\;\Longleftrightarrow\;
\langle\psi| = \alpha^*\langle0| + \beta^*\langle1|.
$$

### 3.2 Inner Products

#### 3.2.1 Inner Products Are Scalars

Say we have two states,

$$
|\psi\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}, \qquad
|\phi\rangle = \begin{pmatrix} \gamma \\ \delta \end{pmatrix}.
$$

The inner product is defined as \(\langle\psi|\) times \(|\phi\rangle\). We combine the two vertical bars into one and write it as \(\langle\psi|\phi\rangle\), called a bra-ket or bracket — the word "bracket" is the origin of the terms "bra" and "ket". To evaluate it, we multiply the row vector and column vector entry-by-entry and add:

$$
\langle\psi|\phi\rangle
= \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix}\begin{pmatrix} \gamma \\ \delta \end{pmatrix}
= \alpha^*\gamma + \beta^*\delta.
$$

The result is just a number, or scalar, so an inner product is also called a scalar product.

The inner product of \(|\phi\rangle\) and \(|\psi\rangle\) is the complex conjugate of the inner product of \(|\psi\rangle\) and \(|\phi\rangle\):

$$
\langle\phi|\psi\rangle = \langle\psi|\phi\rangle^*.
$$

#### 3.2.2 Orthonormality

Several properties can be expressed using the inner product:

- **Normalized:** the inner product of \(|\psi\rangle\) with itself is the total probability

$$
\langle\psi|\psi\rangle = \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix}\begin{pmatrix} \alpha \\ \beta \end{pmatrix}
= |\alpha|^2 + |\beta|^2 = 1.
$$

- **Orthogonal:** two states with zero inner product

$$
\langle0|1\rangle = 0, \qquad \langle+|-\rangle = 0, \qquad \langle i|-i\rangle = 0.
$$

In fact, any two states on opposite sides of the Bloch sphere have zero inner product. Orthogonal states are distinct measurement outcomes.

- **Orthonormal:** each state is individually normalized, and they are orthogonal to each other. So \(|0\rangle,|1\rangle\) are orthonormal; \(|+\rangle,|-\rangle\) are orthonormal; and \(|i\rangle,|-i\rangle\) are orthonormal.

#### 3.2.3 Projection, Measurement, and Change of Basis

Inner products can be used to find the amplitudes of quantum states, which can be norm-squared to yield measurement probabilities. The amplitudes can also be used to change the basis.

As an example, consider \(|\psi\rangle = \frac{\sqrt3}{2}|0\rangle + \frac{1}{2}|1\rangle\).

In the Z-basis, the amplitude of \(|0\rangle\) is

$$
\langle0|\psi\rangle = \langle0|\left(\frac{\sqrt3}{2}|0\rangle + \frac{1}{2}|1\rangle\right)
= \frac{\sqrt3}{2}\underbrace{\langle0|0\rangle}_{1} + \frac{1}{2}\underbrace{\langle0|1\rangle}_{0}
= \frac{\sqrt3}{2}.
$$

The amplitude from \(|1\rangle\) vanishes because \(|0\rangle\) and \(|1\rangle\) are orthogonal. Similarly, the amplitude of \(|1\rangle\) is

$$
\langle1|\psi\rangle = \frac{1}{2}.
$$

Taking the norm-square of each, the possible measurement outcomes are \(|0\rangle\) with probability \(3/4\) and \(|1\rangle\) with probability \(1/4\). Since \(\langle0|\psi\rangle\) and \(\langle1|\psi\rangle\) are the amplitudes of \(|0\rangle\) and \(|1\rangle\), we can write

$$
|\psi\rangle = \langle0|\psi\rangle\,|0\rangle + \langle1|\psi\rangle\,|1\rangle.
$$

This technique is more useful when we cannot just read off the amplitudes, such as when measuring in other bases. In the X-basis \(\{|+\rangle,|-\rangle\}\), the amplitude of \(|+\rangle\) is

$$
\langle+|\psi\rangle = \frac{1}{\sqrt2}(\langle0|+\langle1|)\left(\frac{\sqrt3}{2}|0\rangle + \frac{1}{2}|1\rangle\right)
= \frac{\sqrt3+1}{2\sqrt2}.
$$

The amplitude of \(|-\rangle\), computed using linear algebra:

$$
\langle-|\psi\rangle = \frac{1}{\sqrt2}\begin{pmatrix} 1 & -1 \end{pmatrix}\begin{pmatrix} \sqrt3/2 \\ 1/2 \end{pmatrix}
= \frac{\sqrt3-1}{2\sqrt2}.
$$

Thus the state in the \(\{|+\rangle,|-\rangle\}\) basis is

$$
|\psi\rangle = \langle+|\psi\rangle\,|+\rangle + \langle-|\psi\rangle\,|-\rangle.
$$

**In general:** for an orthonormal basis \(\{|a\rangle,|b\rangle\}\), the state of a qubit can be written as

$$
|\psi\rangle = \alpha|a\rangle + \beta|b\rangle, \qquad
\alpha = \langle a|\psi\rangle,\ \ \beta = \langle b|\psi\rangle.
$$

\(\langle a|\psi\rangle\) is the projection of \(|\psi\rangle\) onto \(|a\rangle\).

### 3.3 Quantum Gates

#### 3.3.1 Gates as Matrices

A quantum gate \(U\) turns \(|0\rangle\) and \(|1\rangle\) into superpositions of \(|0\rangle\) and \(|1\rangle\):

$$
U|0\rangle = a|0\rangle + b|1\rangle = \begin{pmatrix} a \\ b \end{pmatrix}, \qquad
U|1\rangle = c|0\rangle + d|1\rangle = \begin{pmatrix} c \\ d \end{pmatrix}.
$$

We arrange the resulting amplitudes side-by-side, resulting in a matrix:

$$
U = \begin{pmatrix} a & c \\ b & d \end{pmatrix}.
$$

This is a \(2\times2\) matrix because it has two rows and two columns. To get the first (second) entry of a matrix-vector product, we take the first (second) row of the matrix and multiply it component-by-component with the vector, then add:

$$
U|0\rangle = \begin{pmatrix} a & c \\ b & d \end{pmatrix}\begin{pmatrix} 1 \\ 0 \end{pmatrix}
= \begin{pmatrix} a \\ b \end{pmatrix}, \qquad
U|1\rangle = \begin{pmatrix} a & c \\ b & d \end{pmatrix}\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= \begin{pmatrix} c \\ d \end{pmatrix}.
$$

For a superposition \(|\psi\rangle = \alpha|0\rangle + \beta|1\rangle\):

$$
U|\psi\rangle = \begin{pmatrix} a & c \\ b & d \end{pmatrix}\begin{pmatrix} \alpha \\ \beta \end{pmatrix}
= \begin{pmatrix} a\alpha + c\beta \\ b\alpha + d\beta \end{pmatrix}.
$$

In the language of linear algebra, quantum gates are matrices. The matrix must keep the total probability equal to 1:

$$
|a\alpha + c\beta|^2 + |b\alpha + d\beta|^2 = 1.
$$

> Quantum gates are matrices that keep the total probability equal to 1.

#### 3.3.2 Common One-Qubit Gates as Matrices

| Gate         | Action on computational basis                           | Matrix                                                  |
| :----------- | :------------------------------------------------------ | :------------------------------------------------------ |
| Identity \(I\) | \(I\vert 0\rangle=\vert 0\rangle,\ I\vert 1\rangle=\vert 1\rangle\)           | \(\begin{pmatrix}1&0\\0&1\end{pmatrix}\)                  |
| Pauli \(X\)    | \(X\vert 0\rangle=\vert 1\rangle,\ X\vert 1\rangle=\vert 0\rangle\)           | \(\begin{pmatrix}0&1\\1&0\end{pmatrix}\)                  |
| Pauli \(Y\)    | \(Y\vert 0\rangle=i\vert 1\rangle,\ Y\vert 1\rangle=-i\vert 0\rangle\)        | \(\begin{pmatrix}0&-i\\i&0\end{pmatrix}\)                 |
| Pauli \(Z\)    | \(Z\vert 0\rangle=\vert 0\rangle,\ Z\vert 1\rangle=-\vert 1\rangle\)          | \(\begin{pmatrix}1&0\\0&-1\end{pmatrix}\)                 |
| Phase \(S\)    | \(S\vert 0\rangle=\vert 0\rangle,\ S\vert 1\rangle=i\vert 1\rangle\)          | \(\begin{pmatrix}1&0\\0&i\end{pmatrix}\)                  |
| \(T\)          | \(T\vert 0\rangle=\vert 0\rangle,\ T\vert 1\rangle=e^{i\pi/4}\vert 1\rangle\) | \(\begin{pmatrix}1&0\\0&e^{i\pi/4}\end{pmatrix}\)         |
| Hadamard \(H\) | \(H\vert 0\rangle=\frac{1}{\sqrt2}(\vert 0\rangle+\vert 1\rangle)\)      | \(\frac{1}{\sqrt2}\begin{pmatrix}1&1\\1&-1\end{pmatrix}\) |

Of particular note is \(I = \begin{pmatrix}1&0\\0&1\end{pmatrix}\), the \(2\times2\) identity matrix. When it acts on a vector, it does nothing. In general, an \(N\times N\) matrix with 1's on the diagonal and 0's everywhere else is the \(N\times N\) identity matrix.

#### 3.3.3 Sequential Quantum Gates

Using linear algebra, we can compute the effect of a sequence of quantum gates by multiplying each matrix onto the vector. For example (the same result as Eq. (2.9)):

$$
HSTH|0\rangle = \frac{1}{2}\begin{pmatrix}1&1\\1&-1\end{pmatrix}\begin{pmatrix}1&0\\0&i\end{pmatrix}\begin{pmatrix}1&0\\0&e^{i\pi/4}\end{pmatrix}\frac{1}{\sqrt2}\begin{pmatrix}1&1\\1&-1\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}
= \frac{1}{2}\begin{pmatrix}1+e^{i3\pi/4}\\1-e^{i3\pi/4}\end{pmatrix}.
$$

That is,

$$
HSTH|0\rangle = \frac{1}{2}\left[(1+e^{i3\pi/4})|0\rangle + (1-e^{i3\pi/4})|1\rangle\right].
$$

#### 3.3.4 Circuit Identities

We can also prove circuit identities using matrix multiplication. For example, \(HXH = Z\):

$$
HXH = \frac{1}{\sqrt2}\begin{pmatrix}1&1\\1&-1\end{pmatrix}\begin{pmatrix}0&1\\1&0\end{pmatrix}\frac{1}{\sqrt2}\begin{pmatrix}1&1\\1&-1\end{pmatrix}
= \begin{pmatrix}1&0\\0&-1\end{pmatrix} = Z.
$$

#### 3.3.5 Unitarity

If a quantum gate \(U\) acts on \(|\psi\rangle\), we have \(U|\psi\rangle = |U\psi\rangle\). Taking the conjugate transpose, and using the property \((AB)^\dagger = B^\dagger A^\dagger\):

$$
|U\psi\rangle = U|\psi\rangle, \qquad
\langle U\psi| = \langle\psi|U^\dagger. \tag{3.1}
$$

For \(U\) to be a quantum gate, \(|U\psi\rangle\) must be normalized. That is, the inner product of \(|U\psi\rangle\) with itself must equal 1:

$$
\langle U\psi|U\psi\rangle = 1
\quad\Longrightarrow\quad
\langle\psi|U^\dagger U|\psi\rangle = \langle\psi|\psi\rangle
\quad\Longrightarrow\quad
U^\dagger U = I.
$$

A matrix that satisfies \(U^\dagger U = I\) (and \(UU^\dagger = I\)) is called unitary. Thus,

> Quantum gates are unitary matrices, and unitary matrices are quantum gates.

This is why we typically use \(U\) to denote a quantum gate — it stands for unitary.

As an example, is \(U = \frac{1}{\sqrt2}\begin{pmatrix}1&i\\-i&1\end{pmatrix}\) a quantum gate? We check whether it is unitary:

$$
U^\dagger U = \frac{1}{2}\begin{pmatrix}1&i\\-i&1\end{pmatrix}\begin{pmatrix}1&i\\-i&1\end{pmatrix} \neq I.
$$

So no, it is not a quantum gate.

#### 3.3.6 Reversibility

A matrix \(M\) is reversible or invertible if there exists a matrix \(M^{-1}\) such that

$$
M^{-1}M = MM^{-1} = I.
$$

Since a quantum gate \(U\) must be unitary, it satisfies \(U^\dagger U = UU^\dagger = I\). So the inverse of \(U\) is simply its conjugate transpose:

$$
U^{-1} = U^\dagger.
$$

> A quantum gate \(U\) is always reversible, and its inverse is \(U^\dagger\).

If we applied a quantum gate \(U\), we can undo it by applying \(U^\dagger\):

$$
U^\dagger U|\psi\rangle = I|\psi\rangle = |\psi\rangle.
$$

### 3.4 Outer Products

#### 3.4.1 Outer Products Are Matrices

Consider two states \(|\psi\rangle = \alpha|0\rangle+\beta|1\rangle\) and \(|\phi\rangle = \gamma|0\rangle+\delta|1\rangle\). Instead of the inner product \(\langle\psi|\phi\rangle\), where the bra is on the left and the ket is on the right, we can multiply with the ket on the left and the bra on the right — an outer product:

$$
|\psi\rangle\langle\phi|
= \begin{pmatrix} \alpha \\ \beta \end{pmatrix}\begin{pmatrix} \gamma^* & \delta^* \end{pmatrix}
= \begin{pmatrix} \alpha\gamma^* & \alpha\delta^* \\ \beta\gamma^* & \beta\delta^* \end{pmatrix}.
$$

The result is a \(2\times2\) matrix. So, whereas inner products result in scalars, outer products result in matrices, and we can add outer products together to construct quantum gates.

For example, consider \(U = |1\rangle\langle0| + |0\rangle\langle1|\). Acting on \(|\psi\rangle = \alpha|0\rangle + \beta|1\rangle\):

$$
U|\psi\rangle = (|1\rangle\langle0|+|0\rangle\langle1|)(\alpha|0\rangle+\beta|1\rangle)
= \alpha|1\rangle\underbrace{\langle0|0\rangle}_{1} + \beta|0\rangle\underbrace{\langle1|1\rangle}_{1}
= \beta|0\rangle + \alpha|1\rangle.
$$

Applying \(U\) swapped \(|0\rangle\) and \(|1\rangle\), so it is just the \(X\) gate. As a matrix:

$$
U = |1\rangle\langle0| + |0\rangle\langle1|
= \begin{pmatrix}0\\1\end{pmatrix}\begin{pmatrix}1&0\end{pmatrix} + \begin{pmatrix}1\\0\end{pmatrix}\begin{pmatrix}0&1\end{pmatrix}
= \begin{pmatrix}0&1\\1&0\end{pmatrix} = X.
$$

The outer product of \(|\phi\rangle\) and \(|\psi\rangle\) is the conjugate transpose of the outer product of \(|\psi\rangle\) and \(|\phi\rangle\):

$$
|\phi\rangle\langle\psi| = (|\psi\rangle\langle\phi|)^\dagger.
$$

#### 3.4.2 Completeness Relation

Recall from Section 3.2.3 that for any orthonormal basis \(\{|a\rangle,|b\rangle\}\), a qubit can be written as

$$
|\psi\rangle = \langle a|\psi\rangle\,|a\rangle + \langle b|\psi\rangle\,|b\rangle.
$$

The inner products \(\langle a|\psi\rangle\) and \(\langle b|\psi\rangle\) are just scalars, so instead of multiplying them on the left, we can multiply them on the right:

$$
|\psi\rangle = |a\rangle\langle a|\psi\rangle + |b\rangle\langle b|\psi\rangle
= (|a\rangle\langle a| + |b\rangle\langle b|)\,|\psi\rangle.
$$

For this to be true for all \(|\psi\rangle\), we must have

$$
|a\rangle\langle a| + |b\rangle\langle b| = I.
$$

This is called the completeness relation, and it says \(\{|a\rangle,|b\rangle\}\) forms a complete orthonormal basis. All the bases we have discussed (any two states on opposite sides of the Bloch sphere) are complete.

> A complete orthonormal basis \(\{|a\rangle,|b\rangle\}\) satisfies the completeness relation \(|a\rangle\langle a| + |b\rangle\langle b| = I\).

### 3.5 Summary

The mathematical language of quantum computing is linear algebra. Quantum states are represented by column vectors called kets, and the conjugate transpose of a ket is a bra. Multiplying a bra and a ket is an inner product that yields the projection or amplitude of the states onto each other. A state whose inner product with itself is 1 is normalized, and states with zero inner product are orthogonal. Quantum gates are unitary matrices, which satisfy \(U^\dagger U = I\). Unitary matrices are always reversible with \(U^{-1} = U^\dagger\). Multiplying a ket and a bra is an outer product, which is a matrix. A complete orthonormal basis satisfies the completeness relation, meaning the sum of the outer products of each basis vector with itself equals the identity matrix.
