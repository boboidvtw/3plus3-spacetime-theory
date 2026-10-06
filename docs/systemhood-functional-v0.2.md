# Systemhood Functional v0.2 — Candidate Dynamical Individuation Measure

> **Status:** exploratory mathematical construction. None of the quantities below has been established as a new law of nature.

## 1. Goal

Version 2 needs an observer-independent reason why some collection of degrees of freedom should count as a dynamically individuated system while an arbitrary human-selected collection should not.

We denote the desired quantity by

[
\mathcal I(S),
]

but v0.2 deliberately treats it as a **functional to be constructed**, not as a known observable.

A successful candidate should distinguish at least:

1. two noninteracting particles;
2. a bound hydrogen atom;
3. two entangled but otherwise non-bound qubits;
4. an open system that preserves effective identity while exchanging microscopic constituents.

No temporal degree of freedom is inferred merely from a high score. Systemhood and temporal identity remain separate hypotheses.

---

## 2. Why one scalar ingredient is insufficient

Several tempting definitions fail immediately.

### 2.1 Binding energy alone

A candidate such as

[
\mathcal I_B(S)\propto |E_{\rm bind}|
]

can identify many bound composites, but fails for systems whose effective identity is maintained by driven, dissipative, informational, or collective dynamics rather than static binding.

### 2.2 Correlation alone

A correlation measure

[
\mathcal I_C(S)\propto C(S)
]

can become large for two entangled qubits separated over a large distance. Correlation therefore does not automatically imply that the pair is one autonomous composite object.

### 2.3 Spatial proximity alone

Nearby particles need not form a system; distant degrees of freedom can remain strongly correlated.

### 2.4 Internal/external coupling ratio alone

The heuristic ratio

[
\frac{K_{\rm int}}{K_{\rm ext}}
]

is useful but scale- and partition-dependent. A nearly isolated arbitrary subset could score misleadingly well even without stable collective dynamics.

Therefore v0.2 adopts a **multi-component systemhood profile** before attempting scalar compression.

---

## 3. Systemhood profile

For a candidate partition (S|E), where (E) denotes the rest of the modeled environment, define

[
\mathbf I(S|E)
=
(B,C,A,P).
]

The components are:

- (B): binding / dynamical cohesion;
- (C): internal correlation or integration;
- (A): dynamical autonomy from the environment;
- (P): persistence / predictive closure across evolution.

Each component should ultimately be normalized to

[
0\le B,C,A,P\le1.
]

The notation (S|E) is intentional: systemhood cannot generally be evaluated without specifying what counts as the environment and what observational scale is being used.

---

## 4. Component B — dynamical cohesion

Let the effective Hamiltonian be

[
H=H_S+H_E+H_{SE}.
]

For a composite candidate (S) containing subparts (S_a), define a cohesion indicator from the energetic or dynamical cost of separating those subparts.

A schematic normalized form is

[
B(S)
=
\frac{E_{\rm sep}}
{E_{\rm sep}+E_*},
]

where (E_{\rm sep}\ge0) is an operationally defined separation energy and (E_*>0) is a reference scale chosen by the model.

Properties:

[
E_{\rm sep}=0\Rightarrow B=0,
\qquad
E_{\rm sep}\gg E_*\Rightarrow B\rightarrow1.
]

This is useful for hydrogen-like bound states but is not universal.

---

## 5. Component C — internal correlation / integration

For a bipartition (S=S_1\cup S_2), quantum mutual information provides a standard correlation quantity:

[
I(S_1:S_2)
=
S(\rho_{S_1})
+
S(\rho_{S_2})
-
S(\rho_S),
]

where

[
S(\rho)=-\operatorname{Tr}(\rho\ln\rho).
]

A bounded candidate is

[
C(S_1:S_2)
=
\frac{I(S_1:S_2)}
{I(S_1:S_2)+I_*}.
]

For multipartite systems, a future version must specify a partition-independent or optimization-based integration measure.

Important: (C\approx1) is **not sufficient** for systemhood. Entangled qubits are the deliberate counterexample.

---

## 6. Component A — dynamical autonomy

Systemhood should increase when internal dynamics dominate over disruptive environmental coupling.

Introduce characteristic rates

[
\Gamma_{\rm int},
\qquad
\Gamma_{\rm ext}.
]

A simple bounded autonomy indicator is

[
A(S|E)
=
\frac{\Gamma_{\rm int}}
{\Gamma_{\rm int}+\Gamma_{\rm ext}+\Gamma_*},
]

where (\Gamma_*>0) prevents an isolated but dynamically empty arbitrary collection from automatically receiving maximal autonomy.

This is still schematic. A rigorous version may use Liouvillian generators, response functions, information flow, or effective-field-theory scale separation.

---

## 7. Component P — persistence / predictive closure

The most important addition in v0.2 is persistence.

A system should possess effective variables (X_S) whose future can be predicted substantially from its present effective state without continuously specifying every microscopic environmental variable.

Let

[
\mathcal E_S(\Delta\lambda)
]

denote the prediction error for an effective model of (S) over interval (\Delta\lambda), and let (\mathcal E_{\rm null}) be the error of a baseline model with no persistent system identity.

Define schematically

[
P(S)
=
1-
\frac{\mathcal E_S}
{\mathcal E_{\rm null}},
]

clipped to ([0,1]).

Thus (P\rightarrow1) means the effective state of (S) has strong predictive continuity.

This component is intended to capture cases where microscopic constituents turn over while the macroscopic dynamical organization persists.

---

## 8. First scalar candidate

Only after retaining the full profile do we define a provisional scalar:

[
\boxed{
\mathcal I_{0.2}(S|E)
=
(B^{w_B}
 C^{w_C}
 A^{w_A}
 P^{w_P})^{1/W}
}
]

with

[
w_k\ge0,
\qquad
W=w_B+w_C+w_A+w_P.
]

This weighted geometric mean has a useful property: one component cannot be completely ignored merely because another is very large.

However, it also has an obvious weakness: a legitimate system can have (B=0), making the score vanish. Therefore this formula is **only Candidate G (geometric)**, not the accepted definition.

A second candidate is

[
\boxed{
\mathcal I_{0.2}^{(L)}
=
\sigma(
b_0+b_BB+b_CC+b_AA+b_PP+b_{BC}BC+b_{AP}AP
)
}
]

with logistic function

[
\sigma(x)=\frac{1}{1+e^{-x}}.
]

Candidate L allows different routes to systemhood, but introduces fitted coefficients and risks becoming arbitrary.

The v0.2 conclusion is therefore:

[
\boxed{
\mathbf I=(B,C,A,P)
\text{ is currently more defensible than a single }\mathcal I.
}
]

---

## 9. Stress test 1 — two noninteracting particles

Let

[
H=H_A+H_B,
\qquad
H_{AB}=0.
]

For the proposed composite (S=\{A,B\}):

- separation energy: (B\approx0);
- internal correlation for a product state: (C\approx0);
- collective internal dynamics: weak or absent;
- persistence of the arbitrary pair as a collective effective object: generally low.

Expected profile:

[
\mathbf I(A\cup B)
\sim
(0,0,\text{low},\text{low}).
]

The framework should **not** infer a new composite temporal identity merely because an observer groups the particles.

The individual systems (A) and (B), however, can each retain their own candidate temporal histories.

---

## 10. Stress test 2 — hydrogen

Consider

[
p+e\rightleftarrows H.
]

For the bound atom:

- (B>0): ionization requires finite energy;
- (C>0): proton/electron degrees of freedom are dynamically correlated;
- (A): can be high when the atom is sufficiently isolated;
- (P): high for a stable atomic state over its relevant lifetime.

Expected profile:

[
\mathbf I(H)
=
(B_H,C_H,A_H,P_H)
]

with all four components potentially non-negligible.

This makes hydrogen the first serious candidate for testing whether an emergent composite temporal identity (\tau_H) has any content beyond standard atomic phase evolution and GR proper time.

No extra clock effect is asserted yet.

---

## 11. Stress test 3 — entangled qubits

For a Bell state

[
|\Psi\rangle
=
\frac{|00\rangle+|11\rangle}{\sqrt2},
]

the mutual information is high, so

[
C\gg0.
]

But if the qubits are noninteracting after preparation:

[
B\approx0,
\qquad
\Gamma_{\rm int}\approx0.
]

The pair may therefore have a profile schematically like

[
\mathbf I(Q_1\cup Q_2)
\sim
(0,\text{high},\text{low},\text{context-dependent}).
]

This demonstrates why entanglement alone cannot define a new composite temporal identity.

If future work concludes otherwise, the theory must produce an operational consequence that distinguishes a correlated pair's temporal identity from ordinary entanglement dynamics.

---

## 12. Stress test 4 — open system with turnover

Consider an effective system (S) exchanging microscopic constituents with reservoir (E):

[
S+E\rightleftarrows S'+E'.
]

Static binding may be incomplete or continually reorganized, so (B) need not dominate.

However, a persistent open system can have:

- sustained internal interactions;
- nontrivial internal correlations;
- partial autonomy;
- high predictive continuity in coarse-grained variables.

Thus a plausible profile is

[
\mathbf I(S|E)
\sim
(\text{variable},\text{moderate/high},\text{moderate},\text{high}).
]

This is the mathematical role of the human-body intuition: not evidence for extra time, but motivation for a persistence component that does not require microscopic material identity.

---

## 13. Scale dependence

A major conceptual correction is required:

[
\mathcal I=\mathcal I(S|E;\ell,\Delta\lambda,\mathcal O),
]

where

- (\ell) is observational/coarse-graining scale;
- (\Delta\lambda) is the timescale over which persistence is evaluated;
- (\mathcal O) denotes the chosen observable algebra or effective variables.

This means systemhood may be scale-relative without being purely subjective.

For example, an atom may be a useful autonomous system at one energy scale while its internal nuclear/electronic degrees of freedom become essential at another.

The research goal is therefore not necessarily an absolute universal partition, but an **invariant procedure for identifying stable effective systems at a stated scale**.

---

## 14. Connection to temporal identity — deliberately postponed

v0.2 does **not** assume

[
\mathcal I\uparrow
\Rightarrow
\text{time literally appears}.
]

Instead define a hypothesis family

[
w_\tau(S)
=
G(\mathbf I(S)).
]

Three possibilities remain open:

### H1 — bookkeeping interpretation

(w_\tau) only measures when a separate effective clock description is convenient.

### H2 — emergent relational-time interpretation

High systemhood permits a physically meaningful local clock degree of freedom, but all clock relations remain compatible with standard physics.

### H3 — new-physics interpretation

Systemhood modifies relational clock dynamics:

[
\frac{d\tau_i}{d\lambda}
=
N_i^{\rm std}
+
\epsilon\Phi_i(\mathbf I,\rho,H_{\rm int},\ldots),
]

with an observable

[
\Delta R_{ij}\neq0.
]

Only H3 would establish genuinely new temporal physics.

---

## 15. v0.2 result

The first attempted answer to “what objectively distinguishes a physical system?” is therefore not a single magic number.

The current candidate is the profile

[
\boxed{
\mathbf I(S|E)
=
(B,C,A,P)
}
]

evaluated relative to an explicit environment, scale, timescale, and observable set.

The four stress tests show:

| Candidate | Binding (B) | Correlation (C) | Autonomy (A) | Persistence (P) | New composite time justified? |
|---|---:|---:|---:|---:|---|
| Two free particles | low | low | low as a pair | low | No evidence |
| Hydrogen | nonzero | nonzero | potentially high | high | Candidate only |
| Entangled qubits | low | high | low if noninteracting | context-dependent | Correlation alone insufficient |
| Open persistent system | variable | moderate/high | moderate | high | Candidate only |

No row currently demonstrates a new physical time.

---

## 16. Requirements for v0.3

The next version should replace at least two schematic components with quantities that can actually be computed in explicit models.

Recommended order:

1. make (C) precise using quantum mutual information for finite-dimensional examples;
2. make (A) precise using open-system information flow or generator/coupling norms;
3. define (P) using a concrete predictive-loss or conditional-information measure;
4. use hydrogen as the first binding benchmark for (B);
5. test partition sensitivity;
6. only then attempt (w_\tau=G(\mathbf I)).

The project should reject any candidate systemhood definition that classifies arbitrary observer-selected collections as strongly individuated without an invariant dynamical reason.
