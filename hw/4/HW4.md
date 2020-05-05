Dustin Newman

CS 181, Discussion 1A

Campbell, Mathur

# <font style="font-variant: small-caps">Assignment Four</font>

## 1

$L_1$ is a finite state (FS) language which can be represented with the regular expression below.

$$
R_1 := (b\,|\,c)^* \cdot [a \cdot (b\,|\,c) \cdot (b\,|\,c)^* \cdot 
a \cdot (b\,|\,c) \cdot (b\,|\,c)^*]^* \cdot (b\,|\,c)^*
$$

<div style="page-break-after: always; break-after: page;"></div>

## 2

$L_2$ is **not** a finite state language, but is a context-free language. Below, I prove by contradiction that $L_2$ is not a regular language and then present a context-free grammar for the language.

Assume that $L_2$ is regular. By the pumping lemma, there exists some pumping length $p \gt 0$ such that for every string $w \in L_2$ of at least length $p$ (i.e. $|w| \geq p$), $w$ can be partitioned in the form $w := xy^iz$. Per the pumping lemma, we know that (1) $|xy| \le p$, that (2) $|y| \gt 0$, and that (3) all these properties hold for all values of $i \ge 0$. Effectively, this allows us to "pump" (up or down) $w$ and still have the string remain in $L_2$.

Let our $w := a^{p+1}b^{p+1}c^{0}$. $w \in L_2$ because our predicate $k = m + n$ holds when $k = p + 1$ and $m = p + 1$ (i.e. $p + 1 = p + 1 + 0$). 

$|w| \ge p$ because it contains one more "a" and one more "b" than each value of $p \ge 0$ and thus has a specific length of $2p + 2 \gt p$.

Since $|xy| \le p$, we know that $xy$ consists of some fraction of the "a"s in $w$. Maximally, there must be at least one "a" not in the $xy$ partition.

More formally, we say that $x := a^{\alpha}$ and $y := a^{\beta}$ and $z := a^{p + 1- \alpha - \beta}b^{p + 1}$ where $(\alpha + \beta) \le p$ and $\beta \gt 0$.

No matter the partition of $xy^iz$, consider the case when $i := 2$. Then we have $w_2 := xyyz := a^{\alpha}a^{\beta}a^{\beta}a^{p + 1- \alpha - \beta}b^{p + 1}$. 

However, $w_2 \not\in L_2$ because the number of occurrences of "a" does not equal the number of occurrences of "b" i.e. $\#(a,w) \neq \# (b, w)$. We can see that illustrated below:

$$
\alpha + \beta + \beta + p + 1 - \alpha - \beta = p + 1 \\
\beta + p + 1 = p + 1
$$

This can only hold when $\beta := 0$. However, since the length of $y$ must be greater than 0, $\beta \gt 0$. Thus, the above does not hold and $w_2 \not\in L_2$.

This is a contradiction since, by the pumping lemma, $w_2 \in L_2$ since it is of the form $xy^iz$.

$\therefore$ $L_2$ is not a regular language.

The context-free grammar is given below:

$$
S \rightarrow XY \,\,\,\,\,\, \\
X \rightarrow aXb \,|\, \varepsilon \\
Y \rightarrow bYc \,|\, \varepsilon
$$

<div style="page-break-after: always; break-after: page;"></div>

## 3

### a

The parse tree:

<img title="" src="/Users/dustinnewman/Documents/CS181/hw/4/3.a.png" alt="The parse tree" data-align="center">

<div style="page-break-after: always; break-after: page;"></div>

### b

The right-most derivation:

$$
\underline{E} \Rightarrow E + T \\
E + \underline{T} \Rightarrow E + F \\
E + \underline{F} \Rightarrow E + v \\
\underline{E} + v \Rightarrow E + T + v \\
E + \underline{T} + v \Rightarrow E + F + v \\
E + \underline {F} + v \Rightarrow E + v + v \\
\underline{E} + v + v \Rightarrow T + v + v \\
\underline{T} + v + v \Rightarrow F + v + v \\
\underline{F} + v + v \Rightarrow v + v + v
$$

<div style="page-break-after: always; break-after: page;"></div>

### c

The left-most derivation:

$$
\underline{E} \Rightarrow E + T \\
\underline{E} + T \Rightarrow E + T + T \\
\underline{E} + T + T \Rightarrow T + T + T \\
\underline{T} + T + T \Rightarrow F + T + T \\
\underline{F} + T + T \Rightarrow v + T + T \\
v + \underline{T} + T \Rightarrow v + F + T \\
v + \underline{F} + T \Rightarrow v + v + T \\
v + v + \underline{T} \Rightarrow v + v + F \\
v + v + \underline{F} \Rightarrow v + v + v
$$
