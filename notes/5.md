# Week Five, Discussion

## Ambiguity
A grammar is ambiguous if there's some string generated in multiple ways.

e.g. **Dangling Else Problem** - `if a if b else c` - Which does the `else` complement?

S → 0S | S0 | ε is ambiguous because we have multiple parse trees for the string "0". We **can** have multiple valid *derivations* and still be unambiguous, for example S → AB, A → a, B → b. This grammar is unambiguous, even though we have two different derivations:

<div align="center">
Left-most: S → AB → aB → ab
Right-most: S → AB → Ab → ab
</div>

It is not enough to have two different derivations, we must have **two different parse trees**. One way to simplify this requirement is to get to two different left-most derivations. However, this only works *because* those derivations denote different parse trees i.e. it's a middle man step.

If we use our earlier grammar of S → 0S | S0 | 0, how many ways are there to generate 0<sup>n</sub>? Well, for each derivation, we choose if the next zero goes on the left or right i.e. we have two choices for each n zeroes. Thus, 2<sup>n</sup>.

### Precedence 🍊
The classic example of precedence and ambiguity is: a + a x b. We, as humans, know that multiplication has precedence over addition. However, the straightforward grammar:

<div align="center">
E → E + E | E x E | a | b
</div>

has **no** concept of precedence. For it, (a + a) x b is just as likely as a + (a x b). So, our grammar has to incorporate **precedence** i.e. preferring certain operations lower in the parse tree (operations of higher precedence) than others (operations of lower precedence).
- The operation with the highest precedence will be "closest" to its operands in the parse tree.

The big question is then: how do we *implement* precedence? Roughly, we want higher level operations to be parsed last. From our example earlier:

<div align='center'>
E → E + M | M
M → M x M | a | b
</div>

### Associativity
Say we have a - b - a. Although there are no parentheses, we can imagine *implicit* parentheses around two different interpretations: (a - b) - a or a - (b - a). We want the former, since we say that subtraction is **left-associative**.

<div align='center'>
E → E - F | F
F → F x F | (E) | a | b
</div>

The above grammar is **left-associative**. To make it **right-associative**, the name is actually really descriptive and to make it right-associative we just move the recursive E definition to the *right*:

<div align='center'>
E → F - E | F
F → F x F | (E) | a | b
</div>

Back to ambiguous grammars. Consider S → 0S1 | S1 | ε and the string "011". We can either have (0(1)1) or ((01)1). If the language this grammar describes is {0<sup>i</sup>1<sup>j</sup> | i ≤ j}, how do we describe an unambiguous grammar for it?

<div align='center'>
S → 0S1 | T
T → T1 | ε
</div>

What about L := {a<sup>i</sup>b<sup>j</sup>c<sup>k</sup> | i = j or i = k}.

<div align='center'>
S → J | K
J → Jc | J'
J' → aJ'b | ε
K → aKc | K'
K' → bK' | ε
</div>

However, what happens when i = j = k? Then our language itself seems ambiguous! No matter what your grammar is, the language itself does not distinguish between the two different parse trees of i = j = k. Thus, this language is **inherently ambiguous** i.e. no grammar you create for this language will be unambiguous.

