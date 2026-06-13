# Marr's Three Levels of Analysis — Three Levels for Understanding Any Information-Processing System

> *David Marr (1982) argued that any system performing an information-processing task must be understood at three independent yet complementary levels — the **computational theory**, the **representation and algorithm**, and the **hardware implementation**. This is a founding methodological framework for cognitive science and the bridge between "mind" and "brain."*
>
> **Difficulty**: Intermediate　·　**Reading time**: ~12 min
> **Prerequisites**: [Foundations of Cognitive Science](index.md)
> **Further reading**: [Symbolism vs Connectionism](Symbolism_vs_Connectionism.md), [Computational Models of Cognition](../07_Computational_Models/index.md)

---

Cognitive science tries to explain something that sounds impossible: how does roughly 1.4 kg of moist tissue manage to *see*, *remember*, and *decide*? Faced with such a complex system, the easiest mistake is to look for the answer at **one level only** — either getting lost in the electrical signals of neurons, or staying at the level of behavioral description. Marr's contribution is a map that **cuts the problem into three layers**. By the end of this article you will have a "scalpel" that runs through the whole of cognitive science.

## 1. Intuition: Three Ways to Understand a Cash Register

Start with a non-threatening example. Suppose you want to truly "understand" a cash register. You will find you are really asking three completely different — yet equally valid — questions:

1. **What does it compute, and why?** — It maps a set of item prices to a total: essentially *addition*. Why addition of all things? Because the real world imposes a hard constraint: the total of two groups of items must equal the sum of their separate totals. That constraint is what "forces" the algebraic structure of addition.
2. **What steps does it use?** — Column-wise carrying? A big lookup table? Converting to binary and adding?
3. **What is it made of?** — Mechanical gears, abacus beads, or silicon transistors?

All three point at the same machine, yet **none can substitute for another**: knowing it is gears inside (material) tells you nothing about it computing addition (task); knowing it adds tells you nothing about long addition versus a table (steps).

Marr's central claim: **understanding the brain and mind requires asking in exactly these three layers.** Conflating them is the root of many unresolvable debates.

## 2. Formal Definition

Let us tighten the intuition into a definition. View any system as realizing a **mapping from input to output**, $f: X \to Y$. **Marr's Three Levels of Analysis** answer different questions about this $f$:

- **Computational Theory (CT)**: which function $f$ the system actually computes, and **why** that $f$ is appropriate for its environment (what the goal is, what constraints exist, whether the problem is solvable). Answers *What & Why*.
- **Representation & Algorithm (RA)**: what **representations** $R_X, R_Y$ encode the input $X$ and output $Y$, and what **algorithm** $A$ turns one into the other. Answers *How*. Formally, $A: R_X \to R_Y$ must correctly compute $f$.
- **Implementation (IM)**: the **physical substrate** on which $A$ ultimately runs — neurons, silicon, or gears. Answers *physically realized by what*.

A **complete** explanation requires the three levels to line up:

$$
\underbrace{f: X \to Y}_{\text{CT: what}}
\;\;\xrightarrow{\text{choose repr. & algorithm}}\;\;
\underbrace{A: R_X \to R_Y}_{\text{RA: how}}
\;\;\xrightarrow{\text{physical realization}}\;\;
\underbrace{\text{neurons / silicon}}_{\text{IM: by what}}
$$

Note the direction of the arrows: upper levels **constrain** lower ones (the task fixes the algorithm's goal; the algorithm fixes what the hardware must support), yet one upper level can be satisfied by many lower ones — the key point behind everything that follows.

## 3. History & Motivation

This framework did not appear in a vacuum; it was born from a concrete scientific impasse.

David Marr was a neuroscientist at MIT working on vision. Collaborating with Tomaso Poggio (Marr & Poggio, 1976/1977), he observed that vision research was stuck between two extremes: one camp watched only when single neurons fired (pure implementation), the other only described behavioral phenomena (close to the computational level) but never asked about the mechanism in between. Both felt they were "explaining vision," yet neither could convince the other.

Marr broke the deadlock with a famous analogy: **you cannot understand "flight" from the microstructure of feathers — the "computational theory" of flight is aerodynamics.** Likewise, a wiring diagram of neurons alone cannot explain vision. Every level is indispensable, but each handles its own slice.

In 1980 Marr died of leukemia at just 35. His posthumous book *Vision* (1982) laid out the three-level framework systematically, and it became a methodological cornerstone **shared** by cognitive science and computational neuroscience.

## 4. The Three Levels in Detail

With the definition in hand, let us lay the three levels out clearly, then ask what their relationship really is.

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

Drop it onto two systems you already know, and the division of labor becomes obvious:

| Level | Core question | Vision example | Deep-learning example |
|---|---|---|---|
| Computational theory | what, why | recover 3D structure from 2D images (why possible: the world has regularities) | which loss is minimized, and why that goal is reasonable |
| Representation & algorithm | how | edge detection → 2.5D sketch → 3D model | Transformer architecture, backprop |
| Implementation | by what | retina + V1 + ventral stream | GPUs, floating-point weight matrices |

As you read this table, notice: **swapping one column in a row need not change the other two rows.** That leads to the next key question.

### 4.2 What Is the Relationship Between the Levels? — Semi-Independence

The most misunderstood thing is how the levels relate. First, the independent side, which has its own name: **Multiple Realizability**.

It says: the same computation $f$ can be carried out by many algorithms, and the same algorithm by many hardwares. "Adding" simply does not care whether you use gears or silicon. Carried over to the brain, this yields a profound corollary — **a functional description of mind (computational/algorithmic level) cannot be straightforwardly reduced to neural mechanism (implementation level)**. This is the bedrock on which cognitive science stands as an autonomous discipline: studying "what the mind computes" need not wait for neuroscience to count every neuron first.

But there is a second side. The levels are not **fully** independent: **implementation constrains algorithm.** The brain is massively parallel, its units are slow, and it is severely energy-limited — hardware facts that force algorithms very different from a serial digital computer (population codes, approximate inference, rather than exact serial computation). So mature cognitive science does not insist on "strict top-down derivation"; it treats the three levels as a whole that is **mutually constraining and jointly modeled**. In a sentence: the upper levels give direction, the lower levels give reality.

## 5. Worked Example: Dissecting "Addition" Across the Three Levels

With the abstraction done, let us return to the cash register and walk through Marr's own favorite example — addition — step by step, so you can feel "swap one level without touching another."

- **Computational theory**: the function $f(a, b) = a + b$ over integers, satisfying commutativity $a+b=b+a$, associativity, and an identity element $0$. "Why this $f$" — because it captures the real task of "merge two piles, then count," and its algebraic properties are fixed by real-world constraints, not by how we implement it.
- **Representation & algorithm**: the same addition admits completely different algorithms:
  - Arabic numerals + column-wise carrying;
  - Roman numerals (swap the representation and carrying instantly becomes clumsy);
  - two's-complement binary + full-adder logic.
  Three **different representations/algorithms, all computing the same $f$**.
- **Implementation**: and then many physical substrates: decimal mechanical gears (old cash registers), a silicon adder (CPU), abacus beads, even numerosity representations in the human intraparietal sulcus. **Different implementations, the same algorithm possible.**

String the three steps together and the conclusion is clean: **swap the implementation without changing the algorithm; swap the algorithm without changing the computation.** That is the "feel" of multiple realizability.

## 6. Common Pitfalls

Having seen the positive side, here are the most common traps — they recur throughout cognitive-science debates.

> **Pitfall 1: assuming strict top-down independence.** Marr's early exposition did lean top-down, but the mature view accepts that implementation constrains algorithm (biological hardware's parallelism shapes the brain's algorithms). The levels constrain each other; it is not a one-way waterfall.
>
> **Pitfall 2: conflating the algorithm and implementation levels.** "Uses a Transformer" is an algorithm-level fact; "runs on an A100 with bf16 weights" is implementation. Swap the GPU and the algorithm is unchanged.
>
> **Pitfall 3: treating deep learning as "just implementation."** A serious error: the loss function and task definition are computational-level, architecture and optimizer are algorithm-level, and hardware and numerics are implementation. Conflate them and "what is the model actually learning?" becomes unanswerable.

## 8. Related Concepts

- **Prerequisite**: [Foundations of Cognitive Science](index.md) — the three levels are central to cognitive science's multi-level explanatory stance.
- **Lateral**: [Symbolism vs Connectionism](Symbolism_vs_Connectionism.md) — this classic debate is largely about "what representation to use at the algorithm level."
- **Next**: [Computational Models of Cognition](../07_Computational_Models/index.md) — cognitive modeling is exactly the act of instantiating a computational theory at the algorithm level.
- **Cross-pillar (neuroscience)**: [Computational Neuroscience](/notes/neuroscience/05_Computational_Neuroscience/index) — it uses Marr's framework to connect neural mechanism to computational goal.
- **Cross-pillar (wetware)**: [Introduction to Wetware Computing](/notes/wetware/00_Foundations/Overview) — what living neurons "compute" (computational level) is independent of being carbon- or silicon-based (implementation), an echo of multiple realizability in biological computing.

## References

1. Marr, D. (1982). *Vision: A Computational Investigation into the Human Representation and Processing of Visual Information*. W. H. Freeman. (Chapter 1 introduces the three levels.)
2. Marr, D., & Poggio, T. (1976). *From Understanding Computation to Understanding Neural Circuitry*. MIT AI Memo 357.
3. Poggio, T. (2012). *The Levels of Understanding framework, revised*. Perception, 41(9), 1017–1023.
4. Bechtel, W., & Shagrir, O. (2015). *The non-redundant contributions of Marr's three levels of analysis for explaining information-processing mechanisms*. Topics in Cognitive Science, 7(2), 312–322.
