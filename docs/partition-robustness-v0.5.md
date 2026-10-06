# Partition Robustness v0.5 — Dynamical Boundaries from Interaction Structure

> **Status:** toy-model result. It tests system-boundary identification, not the existence of additional physical time.

## 1. Question

Earlier versions introduced

[
\mathbf I(S|E)=(B,C,A,P)
]

but left an important problem:

> Why should one partition (S|E) be physically preferred over an arbitrary subset chosen by an observer?

v0.5 tests whether a nonuniform interaction graph can produce a preferred dynamical cluster without inserting the cluster label into the score.

The executable notebook is:

[`notebooks/partition_robustness_v0.5.ipynb`](../notebooks/partition_robustness_v0.5.ipynb)

## 2. Four-qubit interaction graph

Use four nodes with coupling matrix

[
J=
\begin{pmatrix}
0&1&0.05&0.02\\
1&0&0.03&0.04\\
0.05&0.03&0&0.9\\
0.02&0.04&0.9&0
\end{pmatrix}.
]

The graph contains two strong interaction pairs,

[
\{0,1\},\qquad\{2,3\},
]

connected only by weak bridges.

The partition scoring code is not told that these are the intended clusters.

## 3. Internal and boundary coupling

For candidate subset (S), define

[
W_{\rm in}(S)
=
\sum_{i<j\in S}|J_{ij}|
]

and

[
W_{\rm out}(S)
=
\sum_{i\in S,j\notin S}|J_{ij}|.
]

The v0.5 structural autonomy diagnostic is

[
\boxed{
A_{\rm part}(S)
=
\frac{W_{\rm in}}
{W_{\rm in}+W_{\rm out}+K_0}
}
]

with (K_0=0.1).

A signed boundary contrast is also recorded:

[
Q_{\rm part}(S)
=
\frac{W_{\rm in}-W_{\rm out}}
{W_{\rm in}+W_{\rm out}+K_0}.
]

Neither quantity is proposed as fundamental.

## 4. Enumerated partitions

Canonical bipartitions are enumerated by requiring node 0 to lie in (S), avoiding duplicate complements.

The main structural results are:

| (S) | (W_{in}) | (W_{out}) | (A_{part}) |
|---|---:|---:|---:|
| ({0}) | 0 | 1.07 | 0 |
| ({0,1}) | 1.00 | 0.14 | **0.80645** |
| ({0,2}) | 0.05 | 1.95 | 0.02381 |
| ({0,3}) | 0.02 | 1.99 | 0.00948 |
| ({0,1,2}) | 1.08 | 0.96 | 0.50467 |
| ({0,1,3}) | 1.06 | 0.98 | 0.49533 |
| ({0,2,3}) | 0.97 | 1.07 | 0.45327 |

The strong pair ({0,1}) is recovered as a much stronger candidate than the arbitrary cross-pairs ({0,2}) and ({0,3}).

Because complementary partitions describe the same cut, the same boundary also identifies the ({2,3}) cluster.

## 5. What has been achieved

For this toy graph,

[
\boxed{
\text{interaction structure}
\longrightarrow
\text{preferred candidate boundary}
}
]

without using spatial proximity, semantic labels, or a manually assigned object name.

This is the first concrete answer in Version 2 to the arbitrary-subset problem.

It is only a partial answer because the result is currently driven by static coupling strengths.

## 6. Boundary perturbation

Nearby partitions obtained by adding or swapping a node have substantially lower (A_{part}).

For example,

[
A(\{0,1\})\approx0.806,
]

whereas

[
A(\{0,1,2\})\approx0.505,
\qquad
A(\{0,1,3\})\approx0.495.
]

Cross-pairs are much lower still.

Thus the preferred boundary is not destroyed by the smallest combinatorial perturbations in this example.

## 7. Bridge-strength scan

Let all cross-cluster couplings be scaled by

[
J_{cross}\rightarrow\alpha J_{cross}.
]

Then

[
A_{part}(\{0,1\};\alpha)
]

decreases continuously as the external bridge becomes stronger.

This behavior is desirable: systemhood should not be a magical binary property independent of interaction scale.

At sufficiently strong cross-coupling, the distinction between the two clusters should cease to be compelling.

## 8. Important limitation: static graph bias

The graph was deliberately constructed with strong internal and weak external edges. Recovering the intended cluster therefore validates the algorithmic logic, but it is not a surprising physical discovery.

A serious systemhood criterion must survive harder cases:

- time-dependent couplings;
- equal-strength but state-dependent correlations;
- entanglement without binding;
- open-system noise;
- multiple overlapping scales;
- alternative coarse grainings;
- relabeling of nodes.

## 9. Permutation invariance requirement

If the nodes are relabeled by permutation matrix (P),

[
J\rightarrow PJP^T,
]

the preferred physical cut must transform by the same permutation and all scalar scores must remain unchanged.

This becomes a formal requirement:

[
\boxed{
\text{systemhood diagnostics must be invariant under pure relabeling}.
}
]

This is especially important before approaching identical-particle physics.

## 10. From a tree to a multiscale hierarchy

The graph suggests that systemhood can occur at multiple nested scales.

For example, strong microscopic clusters may themselves interact strongly enough to form a larger effective cluster.

Therefore the target structure is not necessarily a single partition but a hierarchy or multiscale graph:

[
\mathcal H_{sys}
=
\{S^{(1)},S^{(2)},\ldots\}.
]

This matches the motivating atom → molecule → cell → organism intuition more naturally than assigning one exclusive object boundary.

It still does not imply one new geometric time dimension per level.

## 11. Connection to Temporal Identity

v0.5 permits the statement

[
S\text{ has a robust dynamical boundary}
]

to be tested independently of

[
S\text{ has a new physical temporal degree of freedom}.
]

This separation is essential.

The current logical chain is only

[
\text{interaction structure}
\rightarrow
\text{robust effective system candidate}
\rightarrow
\text{candidate temporal identity}.
]

The final arrow remains a hypothesis.

## 12. v0.5 conclusion

The arbitrary-subset problem is not solved in general, but the first nontrivial criterion works in a controlled graph:

[
\boxed{
\{0,1\}|\{2,3\}
}
]

is preferred over cross-cuts because internal interactions dominate boundary interactions.

This gives Version 2 a concrete concept of **dynamical boundary**.

## 13. v0.6 target — state-dependent boundary

The next stage should make the boundary depend on both Hamiltonian structure and actual quantum state.

For each time (t) and partition (S|E), compute:

[
A_{part}(S,t),
\qquad
C_{in}(S,t),
\qquad
C_{boundary}(S:E,t),
\qquad
P(S,t).
]

Then ask whether a cluster remains preferred throughout evolution.

The key quantity becomes a time-dependent profile:

[
\boxed{
\mathbf I_S(t)
=
(B_S(t),C_S(t),A_S(t),P_S(t)).
}
]

If preferred partitions appear, disappear, merge, or split as the physical state evolves, Version 2 will finally have a mathematical prototype for a **dynamic system-identity network**.

Only after that should the project attempt to associate such identity transitions with any temporal-emergence law.


---

## 14. v0.6 continuation

Dynamic formation, merger, and separation are now modeled in:

- [`notebooks/dynamic_system_identity_v0.6.ipynb`](../notebooks/dynamic_system_identity_v0.6.ipynb)
- [`docs/dynamic-system-identity-v0.6.md`](dynamic-system-identity-v0.6.md)

The key result is deliberately conservative: a preferred system decomposition can change dynamically under standard quantum mechanics. Therefore **dynamical identity emergence is not by itself evidence for temporal emergence**.

The project now distinguishes dynamical individuation, operational local clocks, and genuinely nonredundant temporal dynamics.
