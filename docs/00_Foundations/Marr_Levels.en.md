# Marr's Three Levels of Analysis — Three Levels for Understanding Any Information-Processing System

> *David Marr (1982) argued that any system performing an information-processing task must be understood at three independent yet complementary levels — the **computational theory**, the **representation and algorithm**, and the **hardware implementation**. This is a founding methodological framework for cognitive science and the bridge between "mind" and "brain."*
>
> **Difficulty**: Intermediate
> **Prerequisites**: [Foundations of Cognitive Science](index.md)
> **Further reading**: [Symbolism vs Connectionism](Symbolism_vs_Connectionism.md), [Computational Models of Cognition](../07_Computational_Models/index.md)

---

## 1. Intuition: Three Ways to Understand a Cash Register

Suppose you want to "understand" a cash register. You can ask three completely different but equally valid questions:

1. **What does it compute, and why?** — It maps a set of item prices to a total: essentially *addition*. Why addition? Because real-world constraints (the total of two groups of items equals the sum of their separate totals) force the algebraic properties of addition.
2. **What steps does it use?** — Column-wise carrying? A lookup table? Two's-complement binary addition?
3. **What is it made of?** — Gears, abacus beads, or silicon transistors?

All three point at the same machine, yet **none substitutes for another**: knowing it uses gears (implementation) does not tell you it computes addition (computational); knowing it adds does not tell you whether it uses long addition or a table (algorithm). Marr held that understanding the brain/mind likewise requires all three.

---

## 2. Formal Definition

View a system as realizing a **mapping from input to output**, $f: X \to Y$. **Marr's Three Levels of Analysis** answer:

- **Computational Theory (CT)**: which function $f$ the system computes, and **why** that $f$ is appropriate for its environment (goal, constraints, solvability). Answers *What & Why*.
- **Representation & Algorithm (RA)**: what **representations** $R_X, R_Y$ encode input $X$ and output $Y$, and what **algorithm** $A$ turns one into the other. Answers *How*. Formally, $A: R_X \to R_Y$ must correctly compute $f$.
- **Implementation (IM)**: the **physical substrate** on which $A$ runs — neurons, silicon, gears. Answers *physically realized by what*.

A complete explanation requires consistency across all three:

$$
\underbrace{f: X \to Y}_{\text{CT: what}}
\;\;\xrightarrow{\text{choose repr. & algorithm}}\;\;
\underbrace{A: R_X \to R_Y}_{\text{RA: how}}
\;\;\xrightarrow{\text{physical realization}}\;\;
\underbrace{\text{neurons / silicon}}_{\text{IM: by what}}
$$

---

## 3. History & Motivation

David Marr was a neuroscientist at MIT studying the visual system. With Tomaso Poggio (Marr & Poggio, 1976/1977) he argued that vision research was caught between two impoverished extremes: staring only at single-neuron firing (implementation), or only describing behavioral phenomena (close to the computational level) without asking about mechanism. Marr held that **explaining at a single level loses essential understanding** — you cannot understand vision from a wiring diagram alone, just as you cannot understand flight from the microstructure of feathers (the "computational theory" of flight is aerodynamics).

Marr died of leukemia in 1980 at only 35. His posthumous book *Vision* (1982) laid out the three-level framework systematically, becoming a shared methodological cornerstone of cognitive science and computational neuroscience.

---

## 4. The Three Levels in Detail

### 4.1 Content and Typical Questions

<div class="diagram">
<svg viewBox="0 0 720 300" xmlns="http://www.w3.org/2000/svg" font-family="Georgia, serif">
  <rect x="100" y="20" width="520" height="64" rx="6" fill="var(--dia-accent-soft, rgba(196,103,58,.10))" stroke="var(--dia-accent, #c4673a)" stroke-width="1.5"/>
  <text x="360" y="46" text-anchor="middle" font-size="17" fill="var(--dia-accent, #c4673a)" font-weight="bold">Computational Theory</text>
  <text x="360" y="68" text-anchor="middle" font-size="13" fill="var(--dia-stroke-soft, #6b5f4e)">what / why — goal, constraints, solvability</text>
  <rect x="100" y="118" width="520" height="64" rx="6" fill="none" stroke="var(--dia-blue, #2c4d6e)" stroke-width="1.5"/>
  <text x="360" y="144" text-anchor="middle" font-size="17" fill="var(--dia-blue, #2c4d6e)" font-weight="bold">Representation &amp; Algorithm</text>
  <text x="360" y="166" text-anchor="middle" font-size="13" fill="var(--dia-stroke-soft, #6b5f4e)">how — input/output representation + algorithm</text>
  <rect x="100" y="216" width="520" height="64" rx="6" fill="none" stroke="var(--dia-green, #4a6741)" stroke-width="1.5"/>
  <text x="360" y="242" text-anchor="middle" font-size="17" fill="var(--dia-green, #4a6741)" font-weight="bold">Implementation</text>
  <text x="360" y="264" text-anchor="middle" font-size="13" fill="var(--dia-stroke-soft, #6b5f4e)">by what — neurons / silicon / gears</text>
  <line x1="360" y1="84" x2="360" y2="116" stroke="var(--dia-stroke-soft, #6b5f4e)" stroke-width="1.2" marker-end="url(#a)"/>
  <line x1="360" y1="182" x2="360" y2="214" stroke="var(--dia-stroke-soft, #6b5f4e)" stroke-width="1.2" marker-end="url(#a)"/>
  <defs><marker id="a" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="var(--dia-stroke-soft, #6b5f4e)"/></marker></defs>
</svg>
</div>
<p class="figure-caption">Figure 1 — Marr's three levels: the top fixes "what," the middle fixes "how," the bottom fixes "by what"; one top level can be realized by many bottom levels.</p>

| Level | Core question | Vision example | Deep-learning example |
|---|---|---|---|
| Computational theory | what, why | recover 3D structure from 2D images | which loss is minimized, and why |
| Representation & algorithm | how | edge detection → 2.5D sketch → 3D model | Transformer architecture, backprop |
| Implementation | by what | retina + V1 + ventral stream | GPUs, floating-point weight matrices |

### 4.2 (Semi-)Independence Between Levels

The key insight is **Multiple Realizability**: the same computation $f$ can be carried out by many algorithms, and the same algorithm by many hardwares. "Adding" does not depend on gears versus silicon. This is exactly why a **functional description of mind (computational/algorithmic level) cannot be reduced to neural mechanism (implementation level)** — and why cognitive science is legitimate as an autonomous discipline.

But the levels are not **fully** independent: implementation constrains algorithm. The brain is massively parallel, slow, and energy-limited, which forces algorithms very different from serial digital computers (population codes, approximate inference). Modern cognitive science therefore does not insist on strict top-down derivation, but treats the three levels as **mutually constraining and jointly modeled**.

---

## 5. Worked Example: Dissecting Addition Across the Three Levels

Marr himself used addition. Let us walk through it:

- **Computational theory**: the function $f(a, b) = a + b$ over integers, satisfying commutativity $a+b=b+a$, associativity, and an identity element $0$. "Why this $f$" — because it captures the real task of "merging two piles and counting," whose algebraic properties are fixed by real-world constraints.
- **Representation & algorithm**:
  - Arabic numerals + column-wise carrying; or
  - Roman numerals (different representation, clumsy carrying); or
  - two's-complement binary + full-adder logic.
  Three **different representations/algorithms, all computing the same $f$**.
- **Implementation**: decimal mechanical gears (old cash registers), a silicon adder (CPU), abacus beads, or numerosity representations in the human intraparietal sulcus. **Different implementations, same algorithm possible**.

This cleanly shows: swap the implementation without changing the algorithm; swap the algorithm without changing the computation.

---

## 6. Common Pitfalls

> **Pitfall 1: assuming strict top-down independence.** Marr's early exposition leaned top-down, but the mature view accepts that implementation constrains algorithm (biological hardware's parallelism shapes brain algorithms). The levels constrain each other.
>
> **Pitfall 2: conflating the algorithm and implementation levels.** "Uses a Transformer" is the algorithm level; "runs on an A100 with bf16 weights" is implementation. Swapping GPUs does not change the algorithm.
>
> **Pitfall 3: treating deep learning as "just implementation."** No: the loss function and task definition are computational-level; architecture and optimizer are algorithm-level; hardware and numerics are implementation. Conflating the three makes "what is the model learning?" unanswerable.

---

## 8. Related Concepts

- **Prerequisite**: [Foundations of Cognitive Science](index.md) — the three levels are central to cognitive science's multi-level explanatory stance.
- **Lateral**: [Symbolism vs Connectionism](Symbolism_vs_Connectionism.md) — this debate is largely about "what representation to use at the algorithm level."
- **Next**: [Computational Models of Cognition](../07_Computational_Models/index.md) — cognitive modeling explicitly instantiates a computational theory at the algorithm level.
- **Cross-pillar (neuroscience)**: [Computational Neuroscience](/notes/neuroscience/05_Computational_Neuroscience/index) — it uses Marr's framework to connect neural mechanism to computational goal.
- **Cross-pillar (wetware)**: [Introduction to Wetware Computing](/notes/wetware/00_Foundations/Overview) — what living neurons "compute" (computational level) is independent of being carbon- or silicon-based (implementation), echoing multiple realizability.

---

## References

1. Marr, D. (1982). *Vision: A Computational Investigation into the Human Representation and Processing of Visual Information*. W. H. Freeman. (Chapter 1 introduces the three levels.)
2. Marr, D., & Poggio, T. (1976). *From Understanding Computation to Understanding Neural Circuitry*. MIT AI Memo 357.
3. Poggio, T. (2012). *The Levels of Understanding framework, revised*. Perception, 41(9), 1017–1023.
4. Bechtel, W., & Shagrir, O. (2015). *The non-redundant contributions of Marr's three levels of analysis for explaining information-processing mechanisms*. Topics in Cognitive Science, 7(2), 312–322.
