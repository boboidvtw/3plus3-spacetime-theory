# Intervention Jacobian v0.14 — Can Systemhood Components Be Independently Manipulated?

> **Status:** local finite-dimensional intervention study. No temporal correction is fitted. The purpose is to distinguish genuine physical controllability from independence created by parameterization.

Executable notebook:

[`notebooks/intervention_jacobian_v0.14.ipynb`](../notebooks/intervention_jacobian_v0.14.ipynb)

## 1. From covariance to intervention

Previous stages asked whether (B,C,A,P) vary independently across benchmark systems.

v0.14 asks the stronger question:

[
\boxed{
\text{Can we deliberately change one diagnostic without being forced to change the others?}
}
]

Let the diagnostic vector be

[
\mathbf I=
(B,C,A,P)^T
]

and let the model controls be

[
\mathbf u=
(J,g,p,E_{sep})^T.
]

Define the local intervention Jacobian

[
\boxed{
M_{kj}
=
\frac{\partial I_k}
{\partial u_j}.
}
]

This is a local controllability diagnostic, not a causal theorem.

## 2. Declared model

The benchmark uses:

- (J): internal dimer coupling;
- (g): external/environment coupling;
- (p): phase-flip probability;
- (E_{sep}): a separation-energy control when treated independently.

The diagnostics are

[
B=
\frac{E_{sep}}{E_{sep}+E_*},
]

[
C=
\frac{I(A:B)}{2},
]

[
A=
\frac{|J|}
{|J|+|g|+J_0},
]

and

[
P=
F(\rho_{actual},\rho_{predicted}).
]

All derivatives are evaluated numerically by centered finite differences.

## 3. Local rank

If

[
\operatorname{rank}(M)=4,
]

then the four diagnostic directions are locally reachable from four independent control directions in the declared parameterization.

But this statement has an essential qualification:

[
\boxed{
\text{rank}(M)=4
\text{ is meaningful only if the four controls are physically independent}.
}
]

A full-rank Jacobian obtained by inventing independent knobs does not establish four independent physical properties.

## 4. Unit dependence

Raw derivatives such as

[
\frac{\partial B}{\partial E_{sep}}
]

and

[
\frac{\partial C}{\partial p}
]

have different control units/scales.

Therefore v0.14 also computes a dimensionless elasticity matrix

[
\boxed{
\mathcal E_{kj}
=
\frac{u_j}{I_k}
\frac{\partial I_k}{\partial u_j}
}
]

where the denominator is defined and nonzero.

This is better suited for comparing relative sensitivities.

Even the elasticity matrix remains local and model-dependent.

## 5. Targeted intervention

Given a desired small diagnostic displacement

[
\delta\mathbf I_{target},
]

solve

[
M\delta\mathbf u
\approx
\delta\mathbf I_{target}.
]

Using the Moore–Penrose pseudoinverse,

[
\delta\mathbf u
=
M^+
\delta\mathbf I_{target}.
]

For each target direction (B,C,A,P), the notebook reports:

- required control displacement;
- achieved diagnostic displacement;
- off-target leakage;
- control-vector norm.

A mathematically reachable direction may still be practically poor if it requires extreme controls.

## 6. The artificial-knob test

The most important v0.14 result comes from comparing two parameterizations.

### Formal independent-energy model

Treat

[
E_{sep}
]

as independent of (J).

Then the controls are

[
(J,g,p,E_{sep}),
]

and the local Jacobian can achieve full rank.

This demonstrates mathematical controllability.

### Dimer-tied model

Return to the earlier toy interpretation

[
E_{sep}=|J|.
]

Now the physically available controls are only

[
(J,g,p).
]

The Jacobian becomes (4\times3), so

[
\boxed{
\operatorname{rank}(M)\le3.
}
]

Four-dimensional independent control is impossible in that model.

This yields a critical methodological rule:

[
\boxed{
\text{Do not infer physical dimensionality from controls introduced only to make diagnostics independent.}
}
]

## 7. Binding/autonomy coupling

In the tied dimer,

[
J
]

changes both

[
B(J)
]

and

[
A(J,g).
]

It can also change the generated quantum state and therefore (C).

Thus the direction corresponding to “binding only” is not naturally available.

This does not prove that binding and autonomy are the same physical property.

It proves that this benchmark cannot identify them independently.

The distinction is important.

## 8. Correlation/persistence coupling

The phase-flip parameter (p) changes the density matrix.

Consequently it can alter both

[
C
]

and

[
P.
]

Again, one physical intervention can move several diagnostic coordinates.

Therefore a useful systemhood basis need not possess one laboratory knob per coordinate.

But if no collection of physical interventions spans the proposed diagnostic space, the decomposition becomes operationally underdetermined.

## 9. Local versus global controllability

The Jacobian describes only a neighborhood of a baseline point:

[
\mathbf I(\mathbf u+\delta\mathbf u)
\approx
\mathbf I(\mathbf u)
+
M\delta\mathbf u.
]

A full-rank local result does not guarantee global independent control.

Conversely, a rank-deficient point may lie at a symmetry or saturation point while other operating regions have higher rank.

The notebook therefore scans several (J,g) baselines and reports rank/conditioning.

## 10. Singular directions

Perform

[
M=U\Sigma V^T.
]

Small singular values identify diagnostic combinations that are difficult to excite with the available controls.

These directions are more informative than a binary rank statement.

A nearly singular direction means that the corresponding combination may be formally identifiable but experimentally fragile.

## 11. New distinction: diagnostic dimension versus control dimension

v0.14 introduces a distinction that should remain permanent.

### Diagnostic dimension

How many coordinates are useful for describing systemhood?

### Control dimension

How many independent directions can the declared physical model manipulate?

They need not be equal.

For example, four diagnostics may describe a system even if one experimental platform supplies only three independent controls.

Therefore:

[
\boxed{
\operatorname{rank}(M)<4
}
]

does not by itself falsify a four-component diagnostic profile.

It does mean that this platform cannot validate all four components independently.

## 12. Stronger validation criterion

To support a universal four-component basis, the project should eventually find a **collection** of physically motivated benchmark families whose combined intervention directions span the four-dimensional diagnostic space.

Let platform (r) have Jacobian

[
M^{(r)}.
]

Construct the combined intervention matrix

[
M_{combined}
=
[
M^{(1)}
\;M^{(2)}
\;\cdots
]
]

with controls arranged consistently.

The desired condition is that the union of physically available intervention directions spans the diagnostic space.

This is more defensible than demanding one toy model contain four artificial independent knobs.

## 13. Consequence for (B,C,A,P)

The current status is:

- (C) has a clean finite-dimensional information-theoretic definition in the two-qubit benchmarks;
- (A) is computable but depends on the chosen autonomy proxy and (J_0);
- (P) is operational once a predictive effective model and horizon are declared;
- (B) remains the least universal component because separation energy is natural for bound systems but not for every candidate system.

Thus (B) should not yet be treated as mandatory for all physical systems.

## 14. Temporal phenomenology remains paused

The project still should not return to fitting

[
\Delta R
=
\sum_k\theta_kX_k.
]

v0.14 shows why: the independent-variable geometry is still platform-dependent and partially convention-dependent.

Resuming temporal fits now would again create precision downstream of unresolved systemhood definitions.

## 15. v0.14 research gate

The formal gate established by this stage is:

[
\boxed{
\text{A systemhood dimension counts as independently validated only through physically justified interventions or observables, not parameterization freedom.}
}
]

This prevents the theory from manufacturing its desired dimensionality.

## 16. v0.15 target — multi-platform intervention atlas

One dimer model is insufficient.

The next stage should construct several distinct model families:

1. interacting/bound dimer;
2. Bell pair with tunable decoherence after interaction switch-off;
3. driven open system with strong predictive persistence;
4. metastable state with weak binding proxy;
5. classical or stochastic effective system as a non-quantum comparison.

For each platform (r):

[
M^{(r)}
=
\frac{\partial\mathbf I}
{\partial\mathbf u^{(r)}}.
]

Then build an intervention atlas recording:

- which diagnostics are defined;
- which controls are physically motivated;
- local rank;
- singular directions;
- normalization dependence;
- overlap with other platforms.

The central v0.15 question is:

[
\boxed{
\text{Does the union of physically motivated models span the proposed systemhood space without artificial controls?}
}
]

If the answer remains no, the project should reduce or redesign the (B,C,A,P) basis before returning to temporal dynamics.
