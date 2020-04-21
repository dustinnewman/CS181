# 2.2: Pushdown Automata 👨‍❤️‍💋‍👨

<div align="center">
M := (Q,Σ,Γ,δ,q<sub>0</sub>, F)
</div>

A **pushdown automata** (PDA) is a nondeterministic machine having a **stack** which can recognize **non-regular languages**.

- There are deterministic PDAs but we won't be discussing them

- Unlike FSMs, DPDAs and NPDAs are NOT equivalent

- Only NPDAs are equivalent to CFGs:

<div align="center">
PDA = CFG
</div>

What gives us so much power with PDAs is that their stacks are actually *infinite*!🌌 This gives us essentially unlimited memory and the ability to represent non-regular languages like {0<sup>n</sup>1<sup>n</sup>} (which we showed DFAs, NFAs, and regular expressions cannot represent).

Formally, **a PDA is a sextuple** of the form:

<div align="center">
M := (Q,Σ,Γ,δ,q<sub>0</sub>, F)
</div>

- Q = set of states

- Σ = input alphabet

- Γ = **stack alphabet**

- δ : Q × Σ<sub>ε</sub> × Γ<sub>ε</sub> → 𝒫(Q × Γ<sub>ε</sub>) = transition function

- q<sub>0</sub> ∈ Q = start state

- F ⊆ Q = set of accepting states

The action of a PDA is determined by (1) its current state, (2) the input symbol, (3) the top of the stack.

- Both the input symbol and stack symbol can be empty

- If the input symbol is empty, as we have already seen, we automatically "fork" and pursue all epsilon-transitions

- If the stack symbol is empty, we move only according to the input symbol, without reading the top of the stack

The labels of a PDA are in the format (w,s → p) where w is the input symbol, s is the top of the stack, and p is the symbol to push.
- e.g. "ε, ε → $" means go the next state immediately and push a "$" symbol to the stack. This can be used outgoing from the start state q<sub>0</sub> to initialize the stack to "$."
- e.g. "ε, $ → ε" means go to the next state if the top of the stack is "$" (note that viewing the top of the stack pops it!) and push nothing.

It's common to use "$" to mean "bottom of the stack" since we have nothing like `stack.empty`.

**Regular languages are a subset of context-free languages.**
- So, anything that can be represented by an FSM can be represented by a PDA
- But not everything that can be represented by a PDA can be represented by an FSM

