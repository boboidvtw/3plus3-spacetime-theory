# Computable Systemhood v0.3 — Finite-Dimensional Toy Definitions

> **Status:** exploratory toy mathematics. The quantities below are diagnostic candidates, not established physical laws and not evidence for additional time dimensions.

## 1. Objective

v0.2 proposed the systemhood profile

[
\mathbf I(S|E)=(B,C,A,P).
]

v0.3 makes three components computable in finite-dimensional toy models:

- (C): normalized quantum mutual information;
- (A): autonomy from relative internal/external dynamical influence;
- (P): persistence from predictive retention of an effective state.

The goal is not to prove temporal emergence. It is to determine whether the proposed diagnostics can distinguish physically different situations without confusing correlation with system formation.

---

## 2. Computable correlation (C)

For a bipartite candidate system (S=AB) with density operator (\rho_{AB}),

[
I(A:B)
=
S(\rho_A)+S(\rho_B)-S(\rho_{AB}),
]

where

[
S(\rho)=-\operatorname{Tr}(\rho\log_2\rho).
]

For two qubits,

[
0\le I(A:B)\le2\ \text{bits}.
]

Define

[
\boxed{
C_{AB}=\frac{I(A:B)}{2}
}
]

so that

[
0\le C_{AB}\le1.
]

### Benchmark C1 — product state

For

[
|00\rangle,
]

[
S(\rho_A)=S(\rho_B)=S(\rho_{AB})=0,
]

therefore

[
I(A:B)=0,
\qquad
C=0.
]

### Benchmark C2 — Bell state

For

[
|\Phi^+\rangle
=
\frac{|00\rangle+|11\rangle}{\sqrt2},
]

the global state is pure while each reduced qubit is maximally mixed:

[
S(\rho_{AB})=0,
\qquad
S(\rho_A)=S(\rho_B)=1.
]

Hence

[
I(A:B)=2\ \text{bits},
\qquad
\boxed{C=1}.
]

This gives an exact counterexample to the claim that high (C) alone implies a new composite temporal identity: after preparation, the two qubits can be spatially separated and noninteracting while (C) remains high.

---

## 3. Computable autonomy (A)

A system is more autonomous when its internal generator dominates the coupling that allows the environment to determine its short-time evolution.

For a finite-dimensional model,

[
H
=
H_S\otimes I_E
+
I_S\otimes H_E
+
H_{SE}.
]

Define Frobenius/Hilbert--Schmidt norms

[
K_{\rm int}=\|H_S-H_S^{\rm trivial}\|_F,
\qquad
K_{\rm ext}=\|H_{SE}\|_F.
]

The subtraction (H_S^{\rm trivial}) removes an irrelevant identity component; one convenient choice is

[
H_S^{\rm trivial}
=
\frac{\operatorname{Tr}H_S}{d_S}I_S.
]

A first dimensionless diagnostic is

[
\boxed{
A_H
=
\frac{K_{\rm int}}
{K_{\rm int}+K_{\rm ext}+K_0}
}
]

with a declared reference (K_0>0).

### Why (K_0) is retained

If

[
K_{\rm int}=K_{\rm ext}=0,
]

an arbitrary frozen collection should not receive (A=1). (K_0) prevents this degeneracy.

### Limitation

(A_H) depends on Hamiltonian representation, chosen subsystem boundary, and reference scale. It is therefore a **toy diagnostic**, not yet an invariant systemhood observable.

---

## 4. Information-flow autonomy (A_I)

A more physical future definition should ask how strongly the environment improves prediction of the system's future once the present system state is known.

For classical random variables, define

[
\boxed{
A_I
=
1-
\frac{
I(X_S^{t+\Delta}:X_E^t\mid X_S^t)
}{
H(X_S^{t+\Delta}\mid X_S^t)+\varepsilon
}
}
]

clipped to ([0,1]).

Interpretation:

- numerator: extra predictive information supplied by the environment;
- denominator: total unresolved future uncertainty after knowing the present system state;
- (A_I\approx1): environment adds little predictive power;
- (A_I\approx0): future state strongly depends on external information.

For quantum systems the corresponding construction requires quantum conditional mutual information and careful treatment of temporal channels; that is postponed.

v0.3 therefore keeps (A_H) as the directly computable finite-Hamiltonian proxy and (A_I) as the target conceptual definition.

---

## 5. Computable persistence (P)

System identity should persist under its actual dynamics over a declared interval (\Delta\lambda).

Let (X_S(\lambda)) be a chosen effective state representation and let a reduced model predict

[
\widehat X_S(\lambda+\Delta\lambda)
=
\mathcal M_{\Delta\lambda}[X_S(\lambda)].
]

For quantum density matrices use fidelity

[
F(\rho,\sigma)
=
\left(
\operatorname{Tr}
\sqrt{\sqrt\rho\sigma\sqrt\rho}
\right)^2.
]

Define

[
\boxed{
P_F(\Delta\lambda)
=
F(
\rho_S(\lambda+\Delta\lambda),
\widehat\rho_S(\lambda+\Delta\lambda)
)
}.
]

Thus

[
0\le P_F\le1.
]

Important: (P_F) measures persistence of a **chosen effective model**, not whether microscopic constituents remain identical.

This is exactly the property needed for material-turnover examples: the microscopic realization may change while the coarse-grained dynamical state remains predictively continuous.

---

## 6. A simpler retention diagnostic

For a chosen observable vector

[
\mathbf O_S=(O_1,\ldots,O_n),
]

define normalized prediction error

[
D_P
=
\frac{
\|\mathbf O_S^{\rm actual}(t+\Delta)
-
\mathbf O_S^{\rm pred}(t+\Delta)\|
}{
D_0
}.
]

Then

[
\boxed{
P_O=\max(0,1-D_P)
}.
]

This is less fundamental than state fidelity but useful for coarse-grained classical/open systems.

---

## 7. Binding/cohesion (B)

For a genuine bound-state benchmark with threshold energy (E_{\rm threshold}) and composite energy (E_S), define

[
E_{\rm sep}
=
E_{\rm threshold}-E_S
\ge0.
]

A normalized diagnostic is

[
\boxed{
B_E
=
\frac{E_{\rm sep}}
{E_{\rm sep}+E_*}
}.
]

For hydrogen ground state,

[
E_{\rm sep}\approx13.6\ \mathrm{eV}.
]

Choosing (E_*=13.6\ \mathrm{eV}) merely as a transparent benchmark gives

[
B_E(H)=\frac12.
]

This numerical value has **no universal meaning**; it demonstrates normalization only. A future definition must choose scales non-arbitrarily.

---

## 8. Explicit two-qubit interaction model

Consider

[
H_S
=
\frac{\omega}{2}
(\sigma_z\otimes I+I\otimes\sigma_z)
+
J\,\sigma_x\otimes\sigma_x.
]

Let the environment couple through

[
H_{SE}
=
g\,(\sigma_z\otimes I)\otimes\sigma_z^{(E)}.
]

Then (J) controls internal interaction and (g) external coupling.

A simplified interaction-only autonomy diagnostic is

[
\boxed{
A_J
=
\frac{|J|}
{|J|+|g|+J_0}
}.
]

This is deliberately simpler than (A_H) and makes the behavior transparent.

Example with (J_0=0.1):

| (J) | (g) | (A_J) |
|---:|---:|---:|
| 0 | 0 | 0 |
| 1 | 0 | (1/1.1\approx0.909) |
| 1 | 1 | (1/2.1\approx0.476) |
| 0.1 | 1 | (0.1/1.2\approx0.083) |

The absolute values depend on units and (J_0); only the qualitative behavior is intended.

---

## 9. Three concrete two-qubit cases

### Case Q1 — independent product qubits

State:

[
\rho=|00\rangle\langle00|.
]

Take

[
J=0.
]

Then

[
C=0,
\qquad
A_J=0
]

for the pair considered as a proposed composite.

There is no evidence here for a composite temporal identity.

### Case Q2 — Bell-correlated but no continuing interaction

State:

[
\rho=|\Phi^+\rangle\langle\Phi^+|,
\qquad J=0.
]

Exactly,

[
C=1,
\qquad
A_J=0.
]

Therefore

[
\boxed{
C=1\not\Rightarrow\text{autonomous composite system}.
}
]

This is a useful hard constraint on any future (\mathcal I).

### Case Q3 — interacting pair

Let

[
J=1,\qquad g=0,\qquad J_0=0.1.
]

Then

[
A_J\approx0.909.
]

Correlation (C(t)) depends on the state and interaction history rather than on (J) alone. Thus even strong internal coupling does not guarantee high instantaneous correlation.

This gives another constraint:

[
\boxed{
A\text{ and }C\text{ measure different physical properties}.
}
]

---

## 10. Why a scalar (mathcal I) is still postponed

Suppose Bell qubits have

[
(B,C,A,P)=(0,1,0,P_B)
]

while a stable bound composite has approximately

[
(B,C,A,P)=(+, +, +, +).
]

A weighted arithmetic average could give the Bell pair a misleadingly high score. A geometric mean could incorrectly force all legitimate unbound dissipative systems to zero when (B=0).

Therefore v0.3 keeps

[
\boxed{
\mathbf I=(B,C,A,P)
}
]

as a **profile**.

Temporal emergence, if it exists, may depend on a region of this four-dimensional space rather than a one-dimensional threshold.

---

## 11. Candidate individuation region

Instead of

[
\mathcal I>I_c,
]

define a tentative admissible region

[
\Omega_{\rm sys}
\subset
[0,1]^4.
]

Then

[
\mathbf I(S|E)\in\Omega_{\rm sys}
]

means only that (S) qualifies as a dynamically individuated effective system under the current diagnostic.

For example, a future model could require

[
P>P_c,
\qquad
A>A_c,
\qquad
(B>B_c\ \text{or}\ C>C_c),
]

but **no thresholds are chosen in v0.3** because doing so without data would be arbitrary.

This logical form is more flexible than a scalar score and naturally permits multiple routes to effective systemhood.

---

## 12. Partition sensitivity test

For a microscopic universe with degrees of freedom

[
\{1,2,\ldots,N\},
]

evaluate candidate partitions

[
S_k|\bar S_k.
]

A useful systemhood measure should not assign high individuation to exponentially many arbitrary subsets merely because they are weakly coupled to the remainder.

Define a future partition contrast

[
\Delta_{\rm part}(S)
=
D[
\mathbf I(S|E),
\mathbf I(S'|E')
],
]

where (S') are nearby alternative partitions and (D) is a distance in profile space.

A physically meaningful boundary should correspond to a robust local optimum or plateau under small changes of partition/coarse graining.

This is a new requirement introduced in v0.3.

---

## 13. Scale and timescale remain explicit

The full diagnostic is now written

[
\boxed{
\mathbf I
=
\mathbf I(
S|E;
\ell,
\Delta\lambda,
\mathcal O,
\mathcal M
)
}
]

where (\mathcal M) specifies the effective predictive model.

This prevents claims such as “the human body has one absolute systemhood number.” Different scales can reveal different valid effective systems.

Nested systems are therefore allowed:

[
S_{\rm atom}
\subset
S_{\rm molecule}
\subset
S_{\rm cell}
\subset
S_{\rm organism},
]

with each evaluated at an appropriate scale.

This mathematical structure is compatible with the motivating intuition of nested temporal histories, but does not prove them.

---

## 14. Connection to temporal dynamics

Only after systemhood is identified do we consider

[
\frac{d\tau_i}{d\lambda}
=
N_i^{\rm std}
+
\epsilon\Phi_i(\mathbf I_i,\rho,H,\ldots).
]

v0.3 imposes two constraints on any future (\Phi_i):

### Constraint T1 — standard limit

[
\epsilon\rightarrow0
\quad\Rightarrow\quad
\text{GR + standard QM/QFT clock dynamics}.
]

### Constraint T2 — no label dependence

If two mathematical descriptions differ only by relabeling physically identical degrees of freedom, all measurable temporal relations must be invariant.

These constraints will be essential when identical particles and QFT are introduced.

---

## 15. What has actually become computable

v0.3 now provides:

[
C=\frac{I(A:B)}2
]

exactly for two qubits;

[
A_J=\frac{|J|}{|J|+|g|+J_0}
]

as a transparent toy autonomy proxy;

[
P_F
=
F(
\rho_S^{\rm actual},
\rho_S^{\rm predicted}
)
]

as a computable persistence measure once a predictive model is specified;

and

[
B_E
=
\frac{E_{\rm sep}}{E_{\rm sep}+E_*}
]

as a computable bound-state cohesion proxy.

These definitions are intentionally modular so that weak pieces can be replaced without rewriting the entire framework.

---

## 16. v0.3 conclusions

The first quantitative lesson is already clear:

[
\boxed{
\text{correlation}\neq
\text{autonomy}\neq
\text{binding}\neq
\text{persistence}.
}
]

For the Bell state,

[
C=1
]

while the continuing interaction/autonomy proxy can be

[
A_J=0.
]

Therefore a theory that says “strong quantum correlation creates a new time” is too weakly constrained.

The second lesson is that **systemhood is likely a region/profile problem**, not a single scalar threshold.

The third lesson is that the user's motivating examples of nested, changing matter are most naturally represented through (P), scale dependence, and nested effective partitions—not by assigning a new geometric timelike coordinate merely because two processes have different rates.

---

## 17. v0.4 targets

The next stage should build an executable numerical notebook and stop relying only on analytic examples.

Recommended simulations:

1. two-qubit unitary evolution under (J\sigma_x\otimes\sigma_x);
2. Bell-state dephasing under a simple channel;
3. calculate (C(t)) during both evolutions;
4. calculate state fidelity (P_F(t));
5. scan (J/g) and plot (A_J);
6. compare product, correlated, interacting, and decohering cases in profile space;
7. test whether proposed system boundaries remain robust under partition changes in a 3- or 4-qubit toy network.

Only after this numerical stage should the project attempt a temporal correction (\Phi_i).


---

## 18. v0.4 numerical continuation

The numerical stage is now available in:

- [`notebooks/systemhood_simulation_v0.4.ipynb`](../notebooks/systemhood_simulation_v0.4.ipynb)
- [`docs/numerical-systemhood-v0.4.md`](numerical-systemhood-v0.4.md)

The XX-interaction benchmark reproduces (C_{\max}=1) at (Jt=\pi/4), and the Bell dephasing model shows explicitly that correlation and state retention evolve differently.

v0.4 also sharpens the persistence definition: fidelity to an initial state is not persistence. The appropriate candidate compares the actual future state with the future state predicted by an effective model.
