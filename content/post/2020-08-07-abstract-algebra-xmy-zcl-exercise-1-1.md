---
title: 《抽象代数I》习题解答：第一章 群环体域的基本概念
author: Shuai Shi
date: '2020-08-07'
categories:
  - Exercises
tags:
  - Group
---

### 1.1 群的基本概念

1、证明群的定义可以简化为：如果一个非空集合$G$上定义了一个二元运算`$\circ$`，满足：
1) **结合律：** `$(a\circ b)\circ c=a\circ(b\circ c)\ (\forall a,b,c\in G)$`；
2) 存在**左幺元：** 存在`$e\in G$`，使得对任意的$a\in G$，恒有
   `$$e\circ a=a;$$`
3) 存在**左逆元：** 对任意的`$a\in G$`，存在`$b\in G$`，使得
   `$$b\circ a=e;$$`
则`$G$`关于运算`$\circ$`构成一个群。

**解答：** `$\forall a\in G$`，存在`$b\in G$`，使得`$b\circ a=e$`，则对于`$b$`，存在`$c\in G$`，使得`$c\circ b=e$`，则
`$$
\begin{aligned}
& b\circ (a\circ e)=(b\circ a)\circ e=e\circ e=e =b\circ a \\
\Rightarrow & c\circ (b\circ (a\circ e))=c\circ (b\circ a) \\
\Rightarrow & (c\circ b)\circ (a\circ e)=(c\circ b)\circ a \\
\Rightarrow & e\circ (a\circ e)=e\circ a \\
\Rightarrow & a\circ e=a
\end{aligned}
$$`
因此，存在`$e\in G$`,对任意`$a\in G$`，`$e\circ a=a\circ e=a$`，即`$G$`存在幺元。假设存在另一个`$e_1\in G$`，使得`$e_1\circ a=a\circ e_1=a$`，则
`$$e_1=e\circ e_1=e_1\circ e=e$$`
即，`$G$`存在唯一的幺元。

由于`$b\circ a=e$`，则
`$$
\begin{aligned}
& (b\circ a)\circ b=b \\
\Rightarrow & c\circ ((b\circ a)\circ b))=c\circ b \\
\Rightarrow & (c\circ b)\circ (a\circ b)=e \\
\Rightarrow & e\circ (a\circ b)=e \\
\Rightarrow & a\circ b=e \\
\end{aligned}
$$`
因此，对任意`$a\in G$`，存在`$b\in G$`，使得`$a\circ b=b\circ a=e$`，即`$G$`中每个元素存在逆元。假设存在另一个`$b_1\in G$`，使得`$a\circ b_1=b_1\circ a=e$`，则
`$$b_1=b_1\circ(a\circ b)=(b_1\circ a)\circ b=b$$`
即，`$G$`中任意元素存在唯一的逆元。
综上所述，`$G$`是群。

***

2、举例说明：在上题中将条件3.改为“存在**右逆元：** 对任意的`$a\in G$`，存在`$b\in G$`，使得`$a\circ b=e$`”，则`$G$`不一定是群。

**解答：** 令`$G=\{e,a\}$`，其中`$e,a$`是二阶矩阵，`$G$`上的运算`$\circ$`为矩阵的乘法，`$e,a$`的值为
`$$e=\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}, a=\begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix},$$`
`$G$`显然满足条件1.。而
`$$e\circ a=\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix}=\begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix}=a$$`
`$$e\circ e=\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}=\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}=e$$`
即存在`$e\in G$`，对任意`$a\in G$`，都有`$a\circ a=a$`，因此`$G$`满足条件2.。又有
`$$a\circ e=\begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}=\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}=e$$`
即对任意的`$a\in G$`，存在`$b\in G$`，使得`$a\circ b=e$`，因此`$G$`满足新的条件3.。但，由上可知`$e\circ a\ne a\circ e$`，因此`$e$`不满足幺元定义，因此`$G$`不是群。

***

3、设`$G$`是一个非空集合，其中定义了一个二元运算`$\circ$`。证明：如果此运算满足结合律，并且对`$G$`中的任意两个元素`$a,b$`，方程`$a\circ x=b$`和`$y\circ a=b$`都在`$G$`中有解，则`$(G,\circ)$`是群。

**解答：** 由题可知，对`$\forall a, c \in G$`，存在`$x\in G$`，使得`$c\circ x=a$`，同时存在`$e\in G$`，使得`$e\circ c=c$`，即`$e\circ a=a$`。由`$a$`的任意性可知，`$G$`存在左幺元。而又存在`$b\in G$`，使得`$b\circ a=e$`，由`$a$`的任意性可知，`$G$`的每个元素存在左逆元。综上，`$(G,\circ)$`是群。

***

4、设`$G$`是一个非空的有限集合，其中定义了一个二元运算`$\circ$`。证明：如果此运算满足结合律，并且对于`$G$`中任意三个元素`$a,b,c$`，都有（左消去律）`$ab=ac\Rightarrow b=c$`，以及（右消去律）`$ba=ca\Rightarrow b=c$`，则`$(G,\circ)$`是群。

**解答：** 由于`$G$`为有限集合，不妨令`$G=\{g_1,\dots,g_n\}$`，其中`$n$`为`$G$`的元素个数。由题可知，对`$\forall i,j,k\in [1,n]$`，`$g_ig_j=g_ig_k\Rightarrow g_j=g_k$`，因此`$g_ig_1,\dots,g_ig_n$`两两不同，且必存在`$l\in G$`，使`$g_ig_l=g_k$`。因此对`$\forall i,k\in [1,n]$`，方程`$g_ix=g_k$`在`$G$`中有解。同理，对`$\forall i,k\in [1,n]$`，方程`$yg_i=g_k$`在`$G$`中有解，由3题的结论可知，`$(G,\circ)$`是群。

***

5、设`$G$`是群，`$a,b\in G$`，如果`$aba^{-1}=b^r$`，证明`$a^iba^{-i}=b^{r^i}$`.

**解答：** 利用数学归纳法，`$n=1$`时有`$a^nba^{-n}=b^{r^n}$`. 假设当`$n=i-1$`时，命题成立，则
`$$a^iba^{-i}=a(a^{i-1}ba^{-(i-1)})a^{-1}=ab^{r^{i-1}}a^{-1}=(aba^{-1})^{r^{i-1}}=(b^r)^{r^{i-1}}=b^{r^i},$$`
因此当`$n=i$`时，命题成立。

***

6、证明不存在恰有两个2阶元素的群。

**解答：** 假设群`$G$`中的两个2阶元素`$a,b$`，则`$ab\ne a$`，否则`$aab=aa\Rightarrow b=e$`，与`$b$`是2阶元素矛盾，同理可得`$ab\ne b$`。现考虑元素`$aba\in G$`，易知`$aba\ne a$`，否则`$abaa=aa\Rightarrow ab=a$`，矛盾，同理可得`$aba\ne b$`。又有`$aba\ne e$`（其中`$e\in G$`为群`$G$`的幺元），否则`$abaa=ea\Rightarrow ab=a$`，矛盾。而`$(aba)^2=(aba)(aba)=e$`，即`$aba$`是群`$G$`中不同于`$a,b$`的另一个2阶元素，因此命题得证。

***

7、设`$G$`是群，如果对于任意的`$a,b\in G$`，都有`$(ab)^2=a^2b^2$`，证明`$G$`是交换群。并由此证明：如果`$exp(G)=2$`，则`$G$`交换。

**解答：** `$(ab)^2=a^2b^2$``$\Rightarrow abab=aabb$``$\Rightarrow a^{-1}ababb^{-1}=a^{-1}aabbb^{-1}$``$\Rightarrow ab=ba$` ，由`$a,b$`的任意性可知`$G$`是交换群。如果`$exp(G)=2$`，则任意`$a,b\in G$`，有`$a^2=e$`，`$b^2=e$`，`$(ab)^2=e$`，因此有`$(ab)^{-1}=ab$``$\Rightarrow b^{-1}a^{-1}$``$=ba=ab$`.

***

8、在`$S_3$`中找出两个元素`$x,y$`，使得`$(xy)^2\ne x^2y^2$`.

**解答：** `$(xy)^2\ne x^2y^2$`当且仅当`$xy\ne yx$`，令`$x=(12), y=(13)$`，则`$xy=(132), yx=(123)$`，因此有`$xy\ne yx$`.

***

9、设`$G$`是群，`$i$`为任一确定的正整数。如果对于任意的`$a,b\in G$`，都有`$(ab)^k=a^kb^k$`，`$k=i,i+1,i+2$`，证明`$G$`是交换群。

**解答：** 由题可知，`$(ab)^i=a^ib^i$`，`$(ab)^{i+1}=a^{i+1}b^{i+1}$`，`$(ab)^{i+2}=a^{i+2}b^{i+2}$`. 而`$(ab)^{i+1}=a(ba)^{i}b$`，`$(ab)^{i+2}=a(ba)^{i+1}b$`，因此`$(ab)^i=(ba)^i$``$，(ab)^{i+1}=(ba)^{i+1}$`，从而`$(ab)^i(ab)=(ba)^i(ba)$``$=(ab)^i(ba)$`. 两边乘以`$((ab)^i)^{-1}$`，得`$ab=ba$`. 由`$a,b$`的任意性，可得`$G$`是交换群。

***

10、证明：群`$G$`为交换群当且仅当`$x\mapsto x^{-1}(x\in G)$`是同构映射。

**解答：** 令`$h:x\mapsto x^{-1}(x\in G)$`为`$G$`到自身的映射。若`$h$`为同构，则`$\forall x,y\in G$`，`$h(xy)=(xy)^{-1}=y^{-1}x^{-1}$``$=h(y)h(x)=h(yx)$`，因此`$xy=h^{-1}h(xy)=h^{-1}h(yx)=yx$`. 反之，若`$G$`是交换群，则`$\forall x,y\in G$`，`$h(xy)=h(yx)=(yx)^{-1}=x^{-1}y^{-1}=h(x)h(y)$`，因此`$h$`是群同态。同时，对`$\forall y\in G$`，`$h(y^{-1})=y$`，因此`$h$`是满同态，而`$h(y)=0\Rightarrow y^{-1}=e\Rightarrow y=e$`，因此`$h$`是单同态，从而`$h$`是同构。
