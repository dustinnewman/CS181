# Week Eight, Discussion: Turing Machines

## How do we mathematically model computers?



```
    |--------------|
    | ROBOT BRAIN  |
    |--------------|
    O     (o)<-eye O <-wheels
 [ 0 | 1 | 1 | 0 | ␢ | ␢ | ... 
```

This little robot can view one cell at a time with its eye and then move either left or right with its wheels.

Its brain is a finite state machine and depending on the state and what it sees on the tap, it decides:

- its next state

- what to write on the tape

- whether to move left or right

Therefore, we say delta for TMs is:

<div align='center'>
δ: Q × Γ → Q × Γ × {Left, Right}
</div>

Note that this is the deterministic, regular version. There is a non-deterministic version but it's equivalent in power.

## Deciders vs Recognizers

**Recursively-enumerable = Recognizable**

**Recursive = Decidable**

q<sub>accept</sub> and q<sub>reject</sub> states are special states. If you ever reach these states, you accept or reject *immediately*.

A TM **halts** if it accepts or rejects. Otherwise, it never terminates.

A TM *M* **recognizes** a language *L* if x ∈ L ↔︎ M(x) accepts.

- *L* is a *recognizable* language because there exists some TM that recognizes it

A TM *M* **decides** a language *L* if it recognizes *L* <u>and</u> it always halts (i.e. x ∈ L ↔︎ M(x) accepts ∧ x ∉ L ↔︎ M(x) rejects).

- *L* is a *decidable* language because there exists some TM that decides it.

TMs are closely tied with the idea of NP-Completeness i.e. an undecidable language is a problem where we can verify correct solutions but cannot reject incorrect solutions; an unrecognizable language is even worse, we cannot even verify correct solutions to a problem.

## A Simple Turing Machine

<div align='center'>
L = { 0n1n2n | n >= 0}
</div>

1. The TM will take the leftmost 0 and turn it into an "X"

2. While it doesn't see a 1, move right

3. When it sees a 1, turn it into an "X"

4. While it doesn't see a 2, move right

5. When it sees a 2, turn it into an "X"

6. Rewind all the way back to the start of the tape

7. Accept if entire string is all X's

8. Reject if there isn't a corresponding 0/1/2 pair

## Variants

- Consider a TM that has the ability to stay at the same cell. Is this TM more powerful than the regular TM?

No, because you can convert any TM that can stay to an equivalent, but less elegant, regular TM by just moving left, then right, and not changing the input tape:

```
[0]-- x→x,S --> [1] ==> [0]-- x→x,L --> [0.5]-- x→x,R --> [1]
```

- What about a TM that can move forward/backward any finite number of steps?

```
[0]-- x→x,L2 --> [1] ==> [0]-- x→x,L --> [0.5]-- x→x,L --> [1]
```

### Two-Tape TM

A machine like a TM but it has **two** read-write heads and each head has its own tape.

<div align='center'>
δ: Q × Γ<sup>2</sup> → Q × Γ<sup>2</sup> × {L,R,S}<sup>2</sup>
</div>

Given the current state and the content of T1's tape and T2's tape, transition into new state, move T1 head left or right, and move T2 head left or right.

### Universal TM: Running a Virtual Machine in a TM

TM are equivalent to RAM machines (kinda). Real world machines are finite, but have so much resources that they become effectively infinite.

## Infinity 💫

### The First Infinity

<div align='center'>
ℕ = {0, 1, 2, ... } <br>
ℤ = {..., -2, -1, 0, 1, 2, ... }
</div>

Our intuition is that ℕ > ℤ, however since our definition of "equivalent in size" is that there exists some bijection between the two sets, they are actually the **same size** if we have a bijection from even numbers in ℕ to negative numbers in ℤ and from odd numbers in ℕ to positive numbers in ℤ.

```
Z = 0 +1 -1 +2 -2 +3 -3 ...
    |  |  |  |  |  |  |
N = 0  1  2  3  4  5  6 ...
```

Similar logic works for:

<div align='center'>
ℕ = {0, 1, 2, ... } <br>
2ℕ = {0, 2, 4, ... }
</div>

Impossibly so, these are the **same size**.

If we take the integer pair ℤ<sup>2</sup> = {(a, b) | a, b ∈ ℤ}, we can create a bijection from ℤ<sup>2</sup> to ℤ i.e. the number of integers is equal to the number of pairs of integers! Seems very wrong! 

What about the real numbers, ℝ?
