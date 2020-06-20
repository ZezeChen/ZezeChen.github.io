---
layout : post
pid : 25
title: 级数的Dirichlet判别法和Abel判别法
date: 2020-06-20 
cover_url: https://pic2.zhimg.com/80/v2-67b951679604ead463b8ce06d0ccbfa6_720w.jpg
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


其中$$B_n$$为$$b_n$$的前$$n$$项和.

**Abel引理**

$$a_n$$ 单调，且$$|B_i| \leq M$$，则
$$
|\sum_{i=m+1}^n a_i b_i | \leq 2M(|a_{m+1}|+|a_n|).
$$

证明：

$$
\begin{align}
|\sum_{i=m+1}^n a_i b_i| &=|\sum_{i=m+1}^{n-1} (a_i-a_{i+1})B_i+a_nB_n-a_{m+1}B_{m+1}|
\\\\&\leq
\sum_{i=1}^{n-1}|a_i - a_{i+1}||B_i|+|a_n||B_n|+|a_{m+1}||B_{m+1}|
\\\\&\leq
M(\sum_{i=m+1}^{n-1}|a_i||a_{i-1}|+|a_n|+|a_{m+1}|)
\\\\&=
M(|a_n-a_{m+1}|+|a_n|+|a_{m+1}|)
\\\\&\leq
2M(|a_n|+|a_{m+1}|)
\end{align}
$$

# 数列级数

> **Dirichlet判别法** 设数列$$\{a_n\}$$单调且趋于$$0$$，级数$$\sum_{n=1}^\infty b_n$$的部分和有界，则级数$$\sum_{n=1}^\infty a_n b_n$$收敛.

证明：

$$\exists M>0$$使得
$$
\sum_{i=1}^\infty b_i < M , \forall n \geq 1.
$$

由Abel变换及Abel引理
$$
|\sum_{n+1}^{n+p} a_i b_i | \leq 2M(|a_{n+1}|+|a_{n+p}|) \leq 4M(|a_{n+1}|) \rightarrow 0.
$$

由Cauchy收敛准则知，级数收敛.

> **Abel判别法** 如果$$\{a_n\}$$单调有界，$$\sum_{n=1}^\infty b_n$$收敛，则级数$$\sum_{n=1}^\infty a_n b_n$$收敛.

证明：

$$\{a_n\}$$单调有界，则极限存在，即$$\lim_{x\to \infty} a_n =a$$.于是$$\{a_n-a\}$$单调收敛于$$0$$.

由Dirichlet判别法,可知$$ \sum_{n=1}^{\infty} (a_n-a)b_n$$收敛，从而级数
$$
\sum_{n=1}^\infty a_n b_n = \sum_{n=1}^\infty (a_n-a)b_n + \sum_{n=1}^\infty a b_n
$$
收敛.

# 函数项级数

> **Dirichlet判别法** 设$$\sum_{n=1}^\infty a_n(x) b_n(x)$$是定义在$$E$$上的函数项级数.若
> 
> 1° $$\{b_n(x)\}$$在$$E$$上一致收敛于$$0$$，且对于每个固定的$$x$$是单调递减的；
> 
> 2° $$A_n(x)=\sum_{k=1}^n a_k(x)$$在$$E$$上一致有界，
> 
> 则$$\sum_{n=1}^\infty a_n(x) b_n(x)$$在$$E$$上一致收敛.

证明：

设$$|A_n(x)| \leq M$$,$$\forall x \in E$$及$$n$$成立，则
$$
|\sum_{k=n+1}^{n+p} a_k(x)|=|A_{n+p}(x)-A_n(x)| \leq 2M.
$$
由Abel引理，得$$|\sum_{k=n+1}^{n+p} a_k(x) b_k(x)| \leq 4M (|b_{n+1}(x)|+|b_{n+p}(x)|).$$

由1°知$$\forall  \epsilon > 0$$ , $$\exists N$$使得当$$n>N$$时，$$\forall x \in E$$，有\[|b_n(x)|< \frac{\epsilon}{8M}\].

所以当$$n>N$$时，\[|\sum_{k=n+1}^{n+p} a_k(x) b_k(x)| < \epsilon\] 成立 \[\forall x \in E\]及\[p \in \mathbb{N}\].

于是根据Cauchy准则，结论成立.


> **Abel判别法** 设$$\sum_{n=1}^\infty a_n(x) b_n(x)$$是定义在$$E$$上的函数项级数.若
> 
> 1° $$\{b_n(x)\}$$在$$E$$上一致有界，且对于每个固定的$x$是单调的；
> 
> 2° $$A_n(x)=\sum_{k=1}^n a_k(x)$$在$$E$$上一致收敛，
> 
> 则$$\sum_{n=1}^\infty a_n(x) b_n(x)$$在$$E$$上一致收敛.

证明：

设$$|b_n(x)| \leq M$$.由条件2°，$$\forall  \epsilon > 0$$，$$\exists N$$,使得当$$n>N$$时，$$\forall x \in E$$及$$p \in \mathbb{N}$$有
$$
|\sum_{k=n+1}^{n+p} a_k(x)| < \frac{\epsilon}{4M}.
$$

根据Abel引理有
$$
|\sum_{k=n+1}^{n+p} a_k(x)b_k(x)| \leq \frac{\epsilon}{4M} 2M (|b_{n+1}(x)|+|b_{n+p}(x)|) < \epsilon
$$
$$\forall x \in E$$及$$p \in \mathbb{N}$$成立.

于是根据Cauchy准则，结论成立.

关于广义积分的Dirichlet判别法和Abel判别法我有空再写。
















