# Week Four, Discussion

## Pumping Lemma 🚲💨

### 1

<div align="center">
ℒ := {a<sup>i</sup>b<sup>j</sup>c<sup>k</sup> | i < j < k}
</div>

So, there must be some string w in L. Since this is a PL proof, we prove by contradiction, so we assume that L *is* a regular language. Therefore, w must be divisible into some w := xy<sup>i</sup>z partition such that:

- len(y) > 0

- len(xy) <= p

- len(w) >= p

- For **all** i, w ∈ L

If we partition w such that:

<div align="center">
w := a<sup>p</sup>b<sup>p+1</sup>c<sup>p+2</sup>
</div>

Since len(xy) <= p, our only case is:

<div align="center">
x = a<sup>m</sup>
<br>
y = a<sup>n</sup>
<br>
z = a<sup>q</sup>b<sup>p+1</sup>c<sup>p+1</sup>
</div>

The intuition is that by increasing i (i.e. y<sup>i</sup>), then we can violate the language condition that i < j < k (i.e. i as in a<sup>i</sup>).

If we pump with i = 2, then we get:

<div align="center">
xy<sup>2</sup>z = a<sup>m+n</sup> something
</div>

## 2

<div align="center">
ℒ := {a<sup>k</sup>b<sup>j</sup>c<sup>i</sup> | i < j < k}
</div>

The skeleton here is:

1. Come up with some w

2. Decide how to pump

3. How do you show a contradiction?

We're gonna say that w is

<div align="center">
w := a<sup>p+2</sup>b<sup>p+1</sup>c<sup>p</sup>
</div>

And we're actually gonna pump **down**. If we were to pump up, then our string would always be in the language since y is just going to be a bunch of a's and since we are *supposed* to have a lot of a's, then this is always gonna be in the language. When we pump down, we set i := 0.

Since len(xy) <= p, we **decrease** the number of a's so that the number of a's is less than the number of b's. This string will not be in the language, but the PL says it must be. Therefore, contradiction.

### Take Home

<div align="center">
ℒ := {w ∈ Σ<sup>*</sup> | #(0,w) = #(1,w)}
</div>



<div align="center">
ℒ := {1<sup>p</sup> | p is prime}
</div>



## Context-Free Grammars

The basics, yeah... we have a set of **rules** composed of **non-terminals** (things on the left side of the rules) and **terminals** (symbols/elements of the alphabet or empty string). We also have to have a **starting symbol** so we know where to start. By convention, it's *S*.

The reason we call these "context free" is that the expansion of each symbol is completely independent of the expansion of other symbols. e.g. if we have S → AB, then A and B expand completely separate from each other.

The result of expanding non-terminals is a **parse tree** 🌳⽊. Once all of them are expanded, we view all the leaves and get the resulting string. 

### Palindrome Example

<div align="center">
ℒ := {xx<sup>R</sup> | x ∈ Σ<sup>*</sup>} <br>
Σ := {0, 1} <br>
</div>

<div align="center">
S → 0S0 | 1S1 | ε
</div>

### Derivations

There are two main types: **left-most** and **right-most**. It's pretty straightforward really. If you expand the leftmost nonterminal symbol in every step, then it's... a leftmost derivation. Vice versa for right.

It's easier to see the consequences of a left-most vs. right-most derivation in derivation form instead of a parse tree.

## Closure Properties

A **closure property** is an operation on some set X such that the the application of such operation on some element of the set returns an element of the set.

If you have x ∈ X, then operation(x) ∈ X.

Example: [0, 1] is closed under multiplication because zero times 0 or 1 is zero and thus in the set. 1 times 0 is 0 and in the set. 1 times 1 is 1 and in the set.

### Reversal

If L is a regular language, then L<sup>R</sup> := {x<sup>R</sup> | x ∈ L}  is regular.

Take the example NFA below:

```
--> [[ ]]--0--> [[ ]]--0--> (( ))
    1 |           /
      v          /
    (( )) <--1--/
```

The intuition is to flip all the arrows, then make the previous accepting states into starting states (but you have to fake it with epsilon transitions), and then make the previous starting state the accepting state.

```
    (( )) <--0--[[ ]] <--0--[[ ]]
      ^           ^           ^
    1 |          /           /
    [[ ]]---1---/           / ε
      ^                    /
       \                  /
        \-------ε------[[ ]]
```


