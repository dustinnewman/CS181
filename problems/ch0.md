# 0.10
If `a = b`, you cannot divide by `(a - b)` because that would be dividing by zero. We reach a contradiction where either `a ≠ b`, thereby contradicting our initial assumption, or `a = b`, thereby violating the division-by-zero rule.

# 0.11
a. `S(n) = (1/2)(n)(n+1)`

**Base case**:

$S(1) = \frac{1}{2}(1)(1+1) = 1$

**Inductive step**:
Assume `S(k) = (1/2)(k)(k+1)`.

Prove `S(k+1) = (1/2)(k+1)(k+2)`
$$
S(k+1) = S(k) + k + 1\\
S(k+1) = \frac{1}{2}k(k+1)+k+1\\
S(k+1) = \frac{1}{2}(k^{2}+k)+k+1\\
S(k+1) = \frac{k^{2}}{2}+\frac{k}{2}+k+1\\
S(k+1) = \frac{k^{2}}{2}+\frac{3k}{2}+1\\
S(k+1) = \frac{1}{2}(k^{2}+3k+2)\\
S(k+1) = \frac{1}{2}(k+1)(k+2)\\
$$
b.
$$
C(n) = \frac{1}{4}(n^{4}+2n^{3}+n^{2})=\frac{1}{4}n^{2}(n+1)^{2}
$$
**Base case**:
$$
C(1)=\frac{1}{4}(1+2+1)=1
$$
**Inductive step**:

Assume $C(k) = \frac{1}{4}(k^{4}+2k^{3}+k^{2}) = \frac{1}{4}k^2(k+1)^2$

Prove $C(k+1) = \frac{1}{4}((k+1)^{4}+2(k+1)^{3}+(k+1)^{2}) = \frac{1}{4}(k+1)^2(k+2)^2$
$$
C(k+1) = C(k) + (k+1)^3\\
C(k+1) = \frac{1}{4}(k^{4}+2k^{3}+k^{2}) + k^3 + 3k^2 + 3k + 1\\
C(k+1) = \frac{k^4}{4}+\frac{k^3}{2}+\frac{k^2}{4} + k^3 + 3k^2 + 3k + 1\\
C(k+1) = \frac{k^4}{4}+\frac{3k^3}{2}+\frac{13k^2}{4}+3k + 1\\
C(k+1) = \frac{1}{4}(k^4 + 6k^3+ 13k^2 + 12k + 4)\\
C(k+1) = \frac{1}{4}(k+1)^2 (k+2)^2
$$
