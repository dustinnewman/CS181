# 2.1
## a
E => T => F => a
```
E
|
T
|
F
|
a
```

## b
E => E+T => T+T => F+T => a+T => a+F => a+a
```
        E
       / \
      T   T
      |   |
      F   F
      |   |
      a   a
```

## c
E => E+T => E+T+T => T+T+T => F+T+T => a+T+T => a+F+T => a+a+T => a+a+F => a+a+a
```
        E
       / \
      E   T
     / \  |
    E  T  F
    |  |  |
    T  F  a
    |  |
    F  a
    |
    a
```

## d
E => T => F => (E) => (T) => (F) => ((E)) => ((T)) => ((F)) => ((a))
```
        E
        |
        T
        |
        F
       /|\
      ( E )
        |
        T
        |
        F
       /|\
      ( E )
        |
        T
        |
        F
        |
        a
```

# 2.3
## a
R,S,T,X

## b
a,b

## c
R

## d
1. ab
2. aaba
3. babaaba

## e
1. aa
2. aaa
3. ""

## f
False

## g
True

## h
False

## i
True

## j
True

## k
False

## l
True

## m
True

## n
False

## o
L(G) is the set of all strings of "a" and "b" that are not palindromes.

# 2.4
## a
S → X1X1X1X
X → 0X | 1X | ε

## b
S → 1X1 | 0X0
X → 0X | 1X | ε

## c
S → 0 | 1 | 0S0 | 0S1 | 1S0 | 1S1

## d
S → 0 | 0S0 | 0S1 | 1S0 | 1S1

## e
S → 0 | 1 | 0S0 | 1S1 | ε

## f
S → S

# 2.6
## a
S → XaX
X → a | aXb | bXa | XX | ε

# 2.8
S → NP VP → CMPLX-N VP → ART N VP → the N VP → the girl VP → the girl CMPLX-V PREP-PHR → the girl VP NP PREP-PHR → the girl touches NP PREP-PHR → the girl touches ART N PREP-PHR → the girl touches the N PREP-PHR → the girl touches the boy PREP-PHR → the girl touches the boy PREP CMPLX-N → the girl touches the boy with CMPLX-N → the girl touches the boy with ART NP → the girl touches the boy with the NP → the girl touches the boy with the flower

S → NP VP → CMPLX-N VP → ART N VP → the N VP → the girl VP → the girl CMPLX-V → the girl V NP → the girl touches CMPLX-N PREP-PHR → the girl touches ART N PREP-PHR → the girl touches the N PREP-PHR → the girl touches the boy PREP-PHR → the girl touches the boy PREP CMPLX-N → the girl touches the boy with CMPLX-N → the girl touches the boy with ART N → the girl touches the boy with the N → the girl touches the boy with the flower

The first sentence is saying that the boy is touched by a flower such that the girl caused the event to take place i.e. the girl was holding the flower and used said flower to touch the boy, who had no flowers. The second sentence is saying that the boy with the flower was touched by the girl i.e. the boy was holding the flower.

In a LISP-y syntax, the difference is:
`(the girl (touched (the boy) (with a flower)))`
versus
`(the girl (touched (the boy with a flower)))`

# 2.9
S → X | Y
X → IT
I → aIb | ε
T → kT | ε
Y → AK
K → bKc | ε
A → aA | ε

# 2.14
## 1
A → BAB | B | ε
B → 00 | ε

## 2
S → A
A → BAB | B | ε
B → 00 | ε

## 3
S → A
A → BAB | AB | BA | A | ε
B → 00

## 4
S → A | ε
A → BAB | AB | BA | BB | B
B → 00

## 5
S → A | ε
A → BAB | AB | BA | BB | 00
B → 00

## 6
S → A | ε
A → BX | AB | BA | BB | 00
B → 00
X → AB

## 7
S → A | ε
A → S00 | 00S

