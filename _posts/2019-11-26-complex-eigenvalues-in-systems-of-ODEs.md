---
layout: post
title:  "Systems of ODEs with Complex Eigenvalues"
author: johnpiwinski
categories: [ Differential Equations ]
image: https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Mode_Shape_of_a_Tuning_Fork_at_Eigenfrequency_440.09_Hz.gif/220px-Mode_Shape_of_a_Tuning_Fork_at_Eigenfrequency_440.09_Hz.gif
---

## Complex Eigenvalues

We now examine cases of $$\vec{x}'=A\vec{x}$$ where the eigenvalues of A are non-real, complex numbers. Complex eigenvalues occur in complex conjugate pairs (for every $$r=\lambda+i\mu$$ there is an $$\bar{r}=\lambda-i\mu$$, for every $$\Omega=\vec{a}+i\vec{b}$$ there is an $$\bar{\Omega}=\vec{a}-i\vec{b}$$).

For $$\Omega$$ and $$\bar{\Omega}$$, $$a$$ and $$b$$ are real vectors, $$x^{(1)}(t)=\Omega{e^{rt}}=\left(\vec{a}+i\vec{b}\right)e^{(\lambda+i\mu)t}$$ and $$x^{(2)}(t)=\bar{\Omega}e^{\bar{r}}t=\left(\vec{a}-i\vec{b}\right)e^{(\lambda-i\mu)t}$$. To produce real valued solutions, we must employ a technique similar to that of solving second order ODEs in possession of complex-rooted characteristic polynomials. We begin with the assertion of the following lemma. If $$\Phi(t)=f(t)+ig(t)$$ is a vector function satisfying $$\vec{x}'=Ax$$, where $$A$$, $$f$$, and $$g$$ are real. Then, the real valued vector functions $$f$$ and $$g$$ must also solve $$\vec{x}'=A\vec{x}$$.

###### Proof:

$$\Phi'=A\Phi$$ may be expressed as $$(f+ig)'=A(f+ig)\rightarrow f'+ig'=Af+iAg$$ to yield separable real and imaginary components $$Re(Af+iAg)=Af$$ and $$Im(Af+iAg)=Ag$$. By equating the real and imaginary components, we find $$f'=Af$$ and $$g'=Ag$$. Thus, $$Re(\Phi)=f$$ and $$Im(\Phi)=g$$ both satisfy $$x'=Ax$$.

By applying this to the generalized problem

$$x^{(1)}(t)=(\vec{a}+i\vec{b})e^{(\lambda+i\mu)t}=(\vec{a}+i\vec{b})e^{\lambda t}(cos\mu t+ isin\mu t)$$

$$Re(x^{(1)}(t))=u(t)=e^{\lambda t}(acos\mu t- bsin\mu t)$$

$$Im(x^{(1)}(t))=v(t)=e^{\lambda t}(asin\mu t + b cos \mu t)$$

The functions $$u(t)$$ and $$v(t)$$ for a fundamental set of solutions to the system of ODEs with complex eigenvalues.

###### Proof:

From the above lemma, $$u(t)$$ and $$v(t)$$ both satisfy the system of ODEs. It suffices to affirm that $$u(t)$$ and $$v(t)$$ are linearly independent.

###### Subproof $$\vec{a}$$ and $$\vec{b}$$ are linearly dependent:

Since $$r$$ is complex, $$r\neq\bar{r}$$, so $$\Omega$$ and $$\bar{\Omega}$$ are linearly independent over the complex plane $$\mathbb{C}$$, which allows us to assume the existence of $$c_1$$ and $$c_2$$ such that $$c_1a+c_2b=0$$. $$c_1\frac{\Omega+\bar{\Omega}}{2}+c_2\frac{\Omega-\bar{\Omega}}{2i}=c_1\vec{a}+c_2\vec{b}=0$$ By setting $$\frac{1}{i}$$ to $$-i$$ and multiplying by $$2$$, $$c_1\left(\Omega+\bar{\Omega}\right)-ic_2\left(\Omega-\bar{\Omega}\right)=0$$, $$c_1\Omega+c_2\bar{\Omega}-ic_2\Omega+ic_2\bar{\Omega}=0$$, and $$(c_1-ic_2)\Omega+(c_1+ic_2)\bar{\Omega}=0$$. $$c_1-ic_2=0=c_1+ic_2$$ as $$c_1$$ and $$c_2$$ are real coefficients, the prior may only occur if $$c_1=c_2=0$$. Thus, $$\Omega$$ and $$\bar{\Omega}$$ are linearly independent.

Final Steps: $$u(t)=e^{\lambda t}(acos\mu t- bsin\mu t)$$ and $$v(t)=e^{\lambda t}(asin\mu t + b cos \mu t)$$ must be shown to be linearly independent. If the real coefficients $$c_1$$ and $$c_2$$ exist such that $$c_1u(t)+c_2v(t)=0$$. We must show that $$\begin{bmatrix}c_1 \\ c_2 \end{bmatrix}=\vec{0}$$. Using the definitions of $$u(t)$$ and $$v(t)$$ and collecting coefficients,

$$c_1e^{\lambda t}(acos\mu t- bsin\mu t)+c_2e^{\lambda t}(asin\mu t + bcos\mu t)=0$$

$$a(c_1cos\mu t + c_2sin\mu t)+b(c_2cos\mu t - c_1sin\mu t)=0$$

As $$a$$ and $$b$$ are linearly independent, the superposition of the sinusoids and cosinusoids must sum to zero.

$$c_1cos\mu t + c_2sin\mu t = 0 = c_2 cos\mu t -c_1sin\mu t$$

$$\begin{bmatrix}c_1 & c_2 \\ c_2 & -c_1\end{bmatrix}\begin{bmatrix}cos\mu t \\ sin\mu t\end{bmatrix}=\begin{bmatrix}c_1cos\mu t + c_2sin\mu t\\ c_2cos\mu t-c_1sin\mu t\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}$$ because $$\begin{bmatrix}cos\mu t \\ sin\mu t\end{bmatrix}\neq\begin{bmatrix}0 \\ 0 \end{bmatrix}$$

$$Det\begin{bmatrix}c_1 & c_2 \\ c_2 & -c_1\end{bmatrix}=-(c_1^2+c_2^2)=0$$ Thus, $$c_1=c_2=0$$

$$u(t)$$ and $$v(t)$$ are linearly independent and form a  fundamental set of solutions to the system of ODEs with complex eigenvalues.
