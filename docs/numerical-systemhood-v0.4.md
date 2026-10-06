# Numerical Systemhood v0.4 — Results and Interpretation

> **Status:** reproducible toy-model results, not evidence for additional physical time.

The executable notebook is [`notebooks/systemhood_simulation_v0.4.ipynb`](../notebooks/systemhood_simulation_v0.4.ipynb).

## 1. Models simulated

The notebook implements:

[
H=J\sigma_x\otimes\sigma_x
]

for coherent two-qubit interaction, a local phase-flip channel acting on a Bell state, normalized mutual information

[
C=\frac{I(A:B)}2,
]

and the v0.3 toy autonomy proxy

[
A_J=\frac{|J|}{|J|+|g|+J_0}.
]

## 2. Verified analytic/numerical benchmark

Starting from

[
|00\rangle,
]

the XX interaction gives

[
|\psi(t)\rangle
=
\cos(Jt)|00\rangle
-i\sin(Jt)|11\rangle.
]

For (J=1), the numerical scan finds the maximum normalized mutual information

[
\boxed{C_{\max}=1}
]

at

[
\boxed{t=\pi/4\approx0.785398}.
]

At (t=0), (C=0). At (t=\pi), numerical roundoff returns a value effectively equal to zero.

This verifies that correlation is generated dynamically by interaction and can later disappear even though the pair remains the same chosen physical degrees of freedom.

## 3. Bell-state dephasing benchmark

For

[
|\Phi^+\rangle
=
\frac{|00\rangle+|11\rangle}{\sqrt2},
]

the notebook applies

[
\rho(p)
=
(1-p)\rho_{\Phi^+}
+
p(Z\otimes I)\rho_{\Phi^+}(Z\otimes I).
]

Numerically:

| (p) | (C) | fidelity to initial Bell state |
|---:|---:|---:|
| 0 | 1.000000 | 1.000000 |
| 0.10 | 0.765502 | 0.900000 |
| 0.25 | 0.594361 | 0.750000 |
| 0.50 | 0.500000 | 0.500000 |

The two diagnostics do not encode the same property.

In particular, at (p=0.5), Bell-state fidelity is (0.5) while normalized total correlation remains (0.5).

## 4. Important correction concerning persistence

Fidelity to the **initial state** is not a valid general definition of system persistence.

A coherently evolving system can move far from its initial microscopic state while remaining a perfectly persistent dynamical system.

Therefore v0.4 sharpens the v0.3 definition:

[
P_F
=
F(
\rho_S^{\rm actual}(t+\Delta),
\rho_S^{\rm predicted}(t+\Delta)
).
]

The reference must be a prediction from an effective model, not simply (\rho_S(t)).

This distinction will matter strongly for biological/material-turnover examples.

## 5. Autonomy scan

With (J_0=0.1), the notebook reproduces:

| (J) | (g) | (A_J) |
|---:|---:|---:|
| 0 | 0 | 0 |
| 1 | 0 | 0.909091 |
| 1 | 1 | 0.476190 |
| 0.1 | 1 | 0.083333 |

The proxy has the intended qualitative behavior: increasing internal interaction raises (A_J), while increasing environmental coupling lowers it.

It remains a toy diagnostic and is not claimed to be invariant or fundamental.

## 6. v0.4 scientific result

The numerical lab supports the separation

[
\boxed{
C\neq A\neq P.
}
]

A Bell pair can have maximal (C) while the continuing internal-interaction proxy is zero. An interacting pair can dynamically move between low and high (C). A system can also have low fidelity to its initial state while following its predicted dynamics perfectly.

Therefore no one of these quantities can be equated with temporal identity.

## 7. What this does not show

The simulations do not show:

- a new physical time;
- a deviation from GR proper time;
- temporal creation during entanglement;
- a systemhood threshold;
- a temporal correction (\Phi_i).

The temporal hypothesis remains untested until the framework produces an observable relation such as

[
\Delta R_{ij}
=
R_{ij}-R_{ij}^{\rm GR+standard}
\neq0.
]

## 8. v0.5 target — partition robustness

The next numerical model should contain 3–4 qubits with a nonuniform interaction graph,

[
H=
\sum_{i<j}J_{ij}\sigma_x^{(i)}\sigma_x^{(j)}.
]

For every bipartition (S|\bar S), compute a profile based on internal coupling, boundary coupling, correlation, and predictive persistence.

The central question becomes:

[
\boxed{
\text{Does a physically strong cluster appear as a robust optimum across nearby partitions?}
}
]

This directly attacks the arbitrary-subset problem: the theory must identify dynamical boundaries from physics, not from labels chosen by the observer.


---

## 9. v0.5 continuation

Partition robustness is now tested in:

- [`notebooks/partition_robustness_v0.5.ipynb`](../notebooks/partition_robustness_v0.5.ipynb)
- [`docs/partition-robustness-v0.5.md`](partition-robustness-v0.5.md)

A four-node graph with two strong internal pairs and weak cross-couplings recovers the intended dynamical cut from coupling structure alone. For the canonical cluster ({0,1}), the toy partition-autonomy score is approximately (0.806), compared with approximately (0.024) and (0.009) for the cross-pairs ({0,2}) and ({0,3}).

This is a controlled proof-of-concept for a dynamical boundary, not evidence for temporal emergence.
