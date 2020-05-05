Dustin Newman

CS 181, Discussion 1C

Campbell, Mathur

# <font style="font-variant: small-caps;">Assignment Five</font>

We prove that $L_1$ is not regular by contradiction.

Assume that $L_1$ is regular. Therefore, the pumping lemma applies to $L_1$. Therefore, there exists some constant $p \gt 0$ such that for all strings $w \in L_1$, $|w| \geq p$. For every $w$, $w$ can be partitioned into substrings $x,y,z$ such that $w := xy^iz$ for all $i \geq 0$. Per the pumping lemma, $|xy| \leq p$ and $|y| \gt 0$.

Consider the case when $w := \text{b}^{\text{p}}\text{cc}^{\text{p}}$. Clearly, $|w| \geq p$, in fact $|w| = 2p + 1$. $w \in L_1$ since more than half of the symbols in $w$ are c's i.e. $\#(\text{c}, w) = \frac{1}{2}|w|+1 \gt \frac{1}{2}|w|$.

Since $|xy| \leq p$, $x,y$ must consist of all b's, since it is not possible for the length of $y$ to exceed $p$. Therefore, it is more accurate to rewrite $w$ as $w := \text{b}^{m}\text{b}^{n}\text{b}^{p-m-n}\text{cc}^{p}$ where $m := |x|$ and $n := |y|$.

No matter the specific assignment of $x,y,z$, we know that $x,y$ must consist of all b's. We also know that the pumping lemma holds for *all* values of $i$.

Consider the case where $i := 3$. We then rewrite $w$ as $w := \text{b}^m\text{b}^{3n}\text{b}^{p-m-n}\text{cc}^{p}$. The pumping lemma states that $w \in L_1$. However, $w \not\in L_2$ because more than half of its symbols are not c's:

$$
m+3n+p-m-n \gt p+1 \\
2n + p \gt p + 1 \\
$$

The above is impossible since $n \geq 1$. We therefore arrive at a contradiction since $\forall{i}(w := \text{b}^p\text{cc}^p = xy^iz \in L_1)$ does not hold when $i := 3$.

$\therefore$ $L_1$ is not regular.


