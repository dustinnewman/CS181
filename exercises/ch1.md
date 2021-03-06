# 1.1

## a

$M_1 = q_1$

$M_2 = q_1$

## b

$M_1 = \{q_2\}$

$M_2 = \{q_1, q_4\}$

## c

$M_1 = (q_1, q_2, q_3, q_1, q_1)$

$M_2 = (q_1, q_1, q_1, q_2, q_4)$

## d

$M_1$ - No.

$M_2$ - Yes.

## e

$M_1$ - No.

$M_2$ - Yes.

# 1.2

$$
M_1 = (Q, \Sigma, \delta, q_0, F)\\
Q = \{q_1,q_2,q_3\}\\
\Sigma = \{a,b\}\\
q_0 = q_1\\
F = \{q_2\}
$$

|       | a     | b     |
| ----- |:-----:|:-----:|
| $q_1$ | $q_2$ | $q_1$ |
| $q_2$ | $q_3$ | $q_3$ |
| $q_3$ | $q_2$ | $q_1$ |

$$
M_2 = (Q, \Sigma, \delta, q_0, F)\\
Q = \{q_1, q_2, q_3, q_4\}\\
\Sigma = \{a,b\}\\
q_0 = q_1\\
F = \{q_1, q_4\}
$$

|       | a     | b     |
| ----- |:-----:|:-----:|
| $q_1$ | $q_1$ | $q_2$ |
| $q_2$ | $q_3$ | $q_4$ |
| $q_3$ | $q_2$ | $q_1$ |
| $q_4$ | $q_3$ | $q_4$ |

# 1.3

```mermaid
graph LR
    q3((q3))--u-->q2
    q3--d-->q4
    q2--u-->q1
    q2--d-->q3
    q1--u-->q1
    q1--d-->q2
    q4--u-->q3
    q4--d-->q5
    q5--u-->q4
    q5--d-->q5
```

# 1.4

# 1.5

## a

$$
(Q, \Sigma, \delta, q_0, \{\})\\
Q = \{q_0\}\\
\Sigma = \{a,b\}\\
q_0 = q_0\\
F = \{\}\\
$$

|       | a     | b     |
| ----- |:-----:|:-----:|
| $q_0$ | $q_1$ | $q_0$ |
| $q_1$ | $q_1$ | $q_2$ |
| $q_2$ | $q_2$ | $q_2$ |

```
--> [q0]-- a --> [q1]-- b --> (q2)
    /-b-\        /-a-\         /\
                              a, b
                               \/
```

# 1.24

## a

1. q<sub>1</sub>

2. q<sub>1</sub>

3. q<sub>1</sub>

4. q<sub>1</sub>

"000"

## b

1. q<sub>1</sub>

2. q<sub>2</sub> = 1

3. q<sub>2</sub> = 1

4. q<sub>2</sub> = 1

"111"

## c

1. q<sub>1</sub>

2. q<sub>1</sub> = 0

3. q<sub>2</sub> = 1

4. q<sub>2</sub> = 1

"011"

## d

q<sub>1</sub>, q<sub>1</sub>, q<sub>2</sub>, q<sub>1</sub>, q<sub>2</sub>

"0101"

## e

q<sub>1</sub>, q<sub>3</sub>

"1"

## f

q<sub>1</sub>, q<sub>3</sub>, q<sub>2</sub>, q<sub>3</sub>, q<sub>2</sub>

"1111"

## g

q<sub>1</sub>, q<sub>3</sub>, q<sub>2</sub>, q<sub>1</sub>, q<sub>3</sub>, q<sub>2</sub>, q<sub>1</sub>

"110110"

## h

q<sub>1</sub>

""
