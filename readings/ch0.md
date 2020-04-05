# Chapter Zero: Introduction

The central question to the theory of computation is:

> What are the fundamental capabilities and limitations of computers?

which brings up three areas of focus:
1. automata
2. computability
3. complexity

## Complexity Theory

> What makes some problems hard and others easy?

For example, why are sorting problems easy, but scheduling problems are exponential? We still don't know the answer so don't expect to find it in this book!

## Computability Theory

> What can be computed?

Certain seemingly fundamental problems cannot be solved by computers, such as deciding if a mathematical statement is true or false. This problem seems so fundamental to math that you would expect it to be not just computable, but easily so. And yet!

- Complexity theory: classify problems into *easy* and *hard*
- Computability theory: classify problems into *solvable* and *unsolvable*

## Automata Theory
Automata theory is our introduction to the theory of computation because it introduces many concepts - such as the definition of a "computer" - used by the other two areas.

Automata theory concerns the **models of computation**, namely their *definitions* and *properties*. Two examples of such models are:
- the **finite automaton** which is used in:
    - text processing and parsing
    - compilers
- the **context-free grammar** used in:
    - programming languages
    - AI

## Terminology
**Alphabet** - Any nonempty finite set of *symbols*.
- Denoted with Greek letters ∑ and Γ

**String** - Finite sequence of symbols from an alphabet.
- If `∑ = {0, 1}`, then a string could be `010010`.
- Length of string `w` is denoted `|w|` and is the number of symbols in the string

**Empty string ε** - String of length zero.

**Short lex order** - Typical dictionary order of strings in ASCII but shorter strings < longer.
- ex: `01` comes before `000` i.e. `01 < 000`

**Language** - Finite set of strings.

## Proofs
**Proof** - Convincing logical argument that a statement is true beyond any doubt.

**Theorem** - Mathematical statement proven true.
- **Lemma** - Statement proven only to assist in the proof of another, more interesting statement
- **Corollaries** - Related statements proven by a theorem

There is no algorithm for finding proofs. Proofs derive from creativity and a complete understanding of the statement. That said, here are some tips:
- Experiment with examples. If a proof says all objects of a certain type have a certain property, pick a few objects of that type and see if they do have said property.
- Experiment with counterexamples. Try to find an object that does not have that property. If you are unable to do so, notice where you ran into difficulty and that may lead you to an understanding of the statement.
- Try to prove a special case e.g. if the statement is for all k > 0, try k = 1.

### Types of Proofs
#### Construction
Proof that a certain object exists by demonstrating its construction.
- ex: prove there *exists* a 3-regular graph with `n` nodes where `n` is an even number > 2

#### Contradiction
Proof whereby you assume the statement is *false*, then show this assumption leads to a logical contradiction (based on previously stipulated facts).
- ex: The uncovered ground is dry. Prove that it is not raining. By proof by contradiction, we assume that it *is* raining. If it is raining, then uncovered ground is wet. But this is a contradiction, since we know previously that the ground is dry. Therefore, it must not be raining and our assumption that it is raining is false.

#### Induction
Proof that all elements of an infinite set have a certain property. We always have a *base case* and an *inductive step*, both of which we must prove to be true.
- base case = proves that `k = 1` is true
- inductive step = proves that if `k = i` is true, then so is `k = i + 1`
    - Note that we asssume that `k = i` is true and do not have to prove it.

