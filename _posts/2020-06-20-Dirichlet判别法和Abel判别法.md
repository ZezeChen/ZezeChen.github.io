---
layout : post
pid : 25
title: Dirichlet判别法和Abel判别法
date: 2020-06-20 
cover_url: http://ww1.sinaimg.cn/large/006bYYnlly1gg08o96rz6j30rs0yjwii.jpg
category: Math
---

# 引理

**部分和公式**

$$
\begin{align}
\sum_{k=m}^n a_{k+1}(b_{k+1}-b_k)+\sum_{k=m}^n b_{k}(a_{k+1}-a_k)=a_n b_n-a_m b_m
\end{align}
$$

**Abel变换**

$$
\sum_{i=m+1}^n a_i b_i =\sum_{i=m+1}^{n-1} (a_i-a_{i+1})B_i+a_nB_n-a_{m+1}B_{m+1}
$$

其中 $B_n$ 为 $b_n$ 的前 $n$ 项和.

**Abel引理**

$a_n$ 单调，且 $\lvert B_i\rvert\leq M$ ，则

$$
\lvert\sum_{i=m+1}^n a_i b_i\rvert\leq2M(\lvert a_{m+1}\rvert+\lvert a_n\rvert).
$$

证明：

$$
\begin{align}
\lvert\sum_{i=m+1}^n a_i b_i\rvert&=\lvert\sum_{i=m+1}^{n-1} (a_i-a_{i+1})B_i+a_nB_n-a_{m+1}B_{m+1}\rvert \\
&\leq\sum_{i=1}^{n-1}\lvert a_i - a_{i+1}\rvert\lvert B_i\rvert+\lvert a_n\rvert\lvert B_n\rvert+\lvert a_{m+1}\rvert\lvert B_{m+1}\rvert \\
&\leq M(\sum_{i=m+1}^{n-1}\lvert a_i\rvert\lvert a_{i-1}\rvert+\lvert a_n\rvert+\lvert a_{m+1}\rvert) \\
&=M(\lvert a_n-a_{m+1}\rvert+\lvert a_n\rvert+\lvert a_{m+1}\rvert) \\
&\leq2M(\lvert a_n\rvert+\lvert a_{m+1}\rvert)
\end{align}
$$

# 数列级数

> **Dirichlet判别法** 设数列 $\{a_n\}$ 单调且趋于 $0$ ，级数 $\sum_{n=1}^\infty b_n$ 的部分和有界，则级数 $\sum_{n=1}^\infty a_n b_n$ 收敛.

证明：

$\exists M>0$ 使得

$$
\sum_{i=1}^\infty b_i < M ( \forall n \geq 1)
$$

由Abel变换及Abel引理

$$
\lvert \sum_{n+1}^{n+p} a_i b_i\rvert\leq 2M(\lvert a_{n+1}\rvert +\lvert a_{n+p}\rvert) \leq 4M\lvert a_{n+1}\rvert\rightarrow 0.
$$

由Cauchy收敛准则知，级数收敛.

> **Abel判别法** 如果  $\{a_n\}$  单调有界， $\sum_{n=1}^\infty b_n$ 收敛，则级数 $\sum_{n=1}^\infty a_n b_n$ 收敛.

证明：

 $\{a_n\}$  单调有界，则极限存在，即 $\lim_{x\to \infty} a_n =a$ .于是 $\{a_n-a\}$ 单调收敛于 $0$ .

由Dirichlet判别法,可知 $\sum_{n=1}^{\infty} (a_n-a)b_n$ 收敛，从而级数

$$
\sum_{n=1}^\infty a_n b_n = \sum_{n=1}^\infty (a_n-a)b_n + \sum_{n=1}^\infty a b_n
$$

收敛.

# 函数项级数

> **Dirichlet判别法** 设 $\sum_{n=1}^\infty a_n(x) b_n(x)$ 是定义在 $E$ 上的函数项级数.若
> 
> $1^\circ$ $\{b_n(x)\}$ 在 $E$ 上一致收敛于 $0$ ，且对于每个固定的 $x$ 是单调递减的；
> 
> $1^\circ$  $A_n(x)=\sum_{k=1}^n a_k(x)$ 在 $E$ 上一致有界，
> 
> 则 $\sum_{n=1}^\infty a_n(x) b_n(x)$ 在 $E$ 上一致收敛.

证明：

设 $\lvert A_n(x)\rvert\leq M \quad (\forall x\in E\quad and\quad n\in\mathbb{N})$ ，则

$$
\lvert\sum_{k=n+1}^{n+p} a_k(x)\rvert=\lvert A_{n+p}(x)-A_n(x)\rvert \leq 2M.
$$

由Abel引理，得 

$$
\lvert\sum_{k=n+1}^{n+p} a_k(x) b_k(x)\rvert \leq 4M (\lvert b_{n+1}(x)\rvert+\lvert b_{n+p}(x)\rvert).
$$

由$1^\circ$知 $\forall  \epsilon > 0$  ,  $\exists N$ 使得当 $n>N$ 时，$\forall x \in E$ ，有 $\lvert b_n(x)\rvert< \frac{\epsilon}{8M}$ .

所以当 $n>N$ 时，有

$$
\lvert\sum_{k=n+1}^{n+p} a_k(x) b_k(x)\rvert < \epsilon\quad(\forall x \in E \quad and \quad p \in \mathbb{N})
$$

于是根据Cauchy准则，结论成立.


> **Abel判别法** 设 $\sum_{n=1}^\infty a_n(x) b_n(x)$ 是定义在 $E$ 上的函数项级数.若
>
> $1^\circ$ $\{b_n(x)\}$ 在 $E$ 上一致有界，且对于每个固定的 $x$ 是单调的；
>
> $2^\circ$ $A_n(x)=\sum_{k=1}^n a_k(x)$ 在 $E$ 上一致收敛，
>
> 则 $\sum_{n=1}^\infty a_n(x) b_n(x)$ 在 $E$ 上一致收敛.

证明：

设 $\lvert b_n(x)\rvert\leq M.$ 由条件 $2^\circ$ ， $\forall\epsilon > 0$ ， $\exists N$ ,使得当 $n>N$ 时， $\forall x\in E\quad and \quad p\in\mathbb{N}$ 有

$$
\lvert\sum_{k=n+1}^{n+p} a_k(x)\rvert<\frac{\epsilon}{4M}.
$$

根据Abel引理 $\forall x \in E$ 及 $p \in \mathbb{N}$ 有

$$
\lvert\sum_{k=n+1}^{n+p} a_k(x)b_k(x)\rvert\leq\frac{\epsilon}{4M}2M (\lvert b_{n+1}(x)\rvert+\lvert b_{n+p}(x)\rvert) < \epsilon.
$$

于是根据Cauchy准则，结论成立.

## 反常积分



> **Dirichlet判别法** 设 $F(A)=\int_a^A f(x)dx$ 在 $[a,\infty)$ 上有界，函数 $g(x)$ 在 $[a,\infty)$ 上单调，且 $\lim_{x \to + \infty} g(x) =0$ ，则积分 $\int_a^{+ \infty} f(x)g(x)dx$ 收敛。

证明：

设

$$
\lvert F(A)\rvert\leq C\quad(\forall A \geq a)
$$

则

$$
\lvert\int_A^B f(x)dx\rvert=\lvert\int_a^B f(x)dx-\int_a^A f(x)dx\rvert\leq 2C ,\quad\forall A,B \geq a
$$

又因为 $\lim_{x \to + \infty} g(x) =0$ 。故 $\forall \epsilon >0$ ， $\exists M>0$ ，使得$x>M$ 时，有 

$$
\lvert g(x)\rvert \leq \frac{\epsilon}{4C}.
$$

由积分第二中值定理，当 $A,B>M$ 时， 

$$
\begin{align}
\lvert\int_A^B f(x)g(x)dx\rvert&=\lvert g(A)\int_A^{\xi} f(x)dx +g(B)\int_{\xi}^Bf(x)dx\rvert\\
&\leq\frac{\epsilon}{4C}\lvert\int_A^{\xi} f(x)dx\rvert+\frac{\epsilon}{4C}\lvert\int_{\xi}^B f(x)dx\rvert\\
&\leq \frac{\epsilon}{4C} \cdot 2C + \frac{\epsilon}{4C} \cdot 2C\\
&=\epsilon
\end{align}
$$

由Cauchy收敛准则知，积分 $\int_a^{+ \infty} f(x)g(x)dx$ 收敛。



> **Abel判别法** 如果广义积分 $\int_a^{+ \infty} f(x)dx$ 收敛，函数 $g(x)$ 在 $[a,\infty)$ 上单调有界，则积分 $\int_a^{+ \infty} f(x)g(x)dx$ 也收敛。

证明：

因为 $g(x)$ 有界，可设 

$$
\lvert g(x)\rvert\leq C , \forall x \in [a,\infty).
$$

又因为 $f$ 积分收敛，故 $\forall \epsilon >0$ ， $\exists M >0$ 使得 $A,B>M$ 时,有

$$
\lvert\int_A^B f(x)dx\rvert\leq\frac{\epsilon}{2C}
$$

由积分第二中值定理可知

$$
\begin{align}
\lvert\int_A^B f(x)g(x)dx\rvert&=\lvert g(A)\int_A^{\xi} f(x)dx +g(B)\int_{\xi}^B f(x)dx\rvert\\
&\leq C\lvert\int_A^{\xi} f(x)dx\rvert+C\lvert\int_{\xi}^B f(x)dx\rvert\\
&\leq \epsilon
\end{align}
$$

由Cauchy准则知，积分收敛。

# 附

> **积分第二中值定理** 设 $f$  在 $[a,b]$ 上可积，则
> 1. 如果 $g$ 在 $[a,b]$ 上递减，且非负，则 $\exists\xi\in[a,b]$ 使得
> 
>$$
>\int_a^b f(x)g(x)dx=g(a)\int_a^\xi f(x)dx
>$$
>
>2. 如果 $g$ 在 $[a,b]$ 上递增，且非负，则 $\exists\xi\in[a,b]$ 使得
> 
>$$
>\int_a^b f(x)g(x)dx=g(b)\int_\xi^b f(x)dx
>$$
>
>3. 一般地，如果 $g$ 为  $[a,b]$ 上的单调函数，则 $\exists\xi\in[a,b]$ 使得
>
>$$
>\int_a^b f(x)g(x)dx=g(a)\int_a^\xi f(x)dx+g(b)\int_\xi^b f(x)dx
>$$
>

