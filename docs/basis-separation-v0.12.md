# Basis-Separating Counterexamples v0.12 — Is `(B,C,A,P)` Really Four-Dimensional?

> **Status:** diagnostic toy study. The counterexample scores are illustrative normalized values, not measured or derived physical constants. No temporal residual is fitted in this stage.

Executable notebook:

[`notebooks/basis_separation_v0.12.ipynb`](../notebooks/basis_separation_v0.12.ipynb)

## 1. Why temporal modeling is paused

v0.11 exposed a serious problem: if

[
B(t),C(t),A(t),P(t)
]

all track the same merger profile, a temporal model may fit well while the coefficients have no unique physical interpretation.

Therefore v0.12 temporarily removes the temporal ansatz and asks a more basic question:

[
\boxed{
\text{Does the proposed systemhood basis actually contain four separable directions?}
}
]

If not, later temporal equations built from it would inherit artificial redundancy.

## 2. Counterexample strategy

A useful basis should survive systems designed to separate its components.

The notebook therefore uses a deliberately heterogeneous suite:

| regime | intended diagnostic role |
|---|---|
| free control | low (B,C,A,P) |
| entangled, unbound | high (C), low (B) |
| bound, weakly correlated | high (B), moderate/controlled (C) |
| open persistent | high (P) despite constituent/environment exchange |
| autonomous, unbound | high (A) without strong (B) |
| correlated, leaky | high (C), low (A) |
| fragile bound | high (B), low (P) |
| persistent, low binding | high (P), low (B) |

These are basis-separation thought experiments, not claims that the assigned normalized scores are unique.

## 3. Feature matrix

Construct

[
Z=
\begin{pmatrix}
B_1&C_1&A_1&P_1\\
B_2&C_2&A_2&P_2\\
\vdots&\vdots&\vdots&\vdots
\end{pmatrix}.
]

The first structural test is

[
\operatorname{rank}(Z).
]

For the deliberately diversified v0.12 suite, the matrix has full column rank:

[
\boxed{
\operatorname{rank}(Z)=4.
}
]

Therefore the four coordinates are **not mathematically forced** to collapse to fewer than four dimensions.

This is a possibility result, not a physical validation.

## 4. Centered singular-value test

Because a constant offset in every feature does not establish useful variation, also inspect

[
Z_c=Z-\langle Z\rangle.
]

Perform

[
Z_c=U\Sigma V^T.
]

The singular values reveal whether one direction is nearly absent.

A very small

[
\sigma_{min}
]

would indicate a practically degenerate basis even when formal matrix rank remains four.

The condition number

[
\kappa=
\frac{\sigma_{max}}{\sigma_{min}}
]

is therefore more informative than rank alone.

## 5. Full rank is not enough

A matrix can have rank four but still be badly conditioned.

Thus the relevant hierarchy is:

[
\boxed{
\text{formal independence}
\rightarrow
\text{numerical separability}
\rightarrow
\text{physical operational independence}.
}
]

v0.12 addresses the first two only at the toy-score level.

The third remains open.

## 6. Leave-one-feature-out reconstruction

For each coordinate (X_j\in\{B,C,A,P\}), regress it against the other three:

[
X_j
\approx
a_0+\sum_{k\neq j}a_kX_k.
]

If

[
R_j^2\approx1,
]

then that coordinate carries little independent information over the tested regime suite.

This test complements pairwise correlation because a feature may be reconstructible from a combination of several others even when no single correlation is extreme.

## 7. Counterexample ablation

A dangerous situation would be:

> the basis is full rank only because of one specially chosen row.

The notebook therefore removes each counterexample in turn and recomputes rank and the smallest centered singular value.

This tests whether separability is distributed across the suite rather than resting entirely on one hand-crafted case.

## 8. Perturbation robustness

The normalized scores in v0.12 are approximate toy diagnostics.

Therefore the notebook adds random perturbations,

[
Z\rightarrow Z+\delta Z,
]

clips values to the declared normalized range, and repeatedly recomputes the singular spectrum.

This tests whether the inferred basis geometry is structurally stable under modest scoring uncertainty.

A physically useful basis should not alternate between well-conditioned and nearly singular under tiny perturbations.

## 9. PCA-style variance accounting

Even if all four directions exist, some may explain very little variation.

Define

[
f_k=
\frac{\sigma_k^2}
{\sum_j\sigma_j^2}.
]

If the first two or three singular directions explain nearly all variance, a lower-dimensional effective description may be preferable for a particular experimental domain.

This does not mean the discarded coordinate is universally meaningless; it means it is weakly excited by that domain.

## 10. What v0.12 actually establishes

The deliberately heterogeneous suite demonstrates:

[
\boxed{
(B,C,A,P)
\text{ can be mathematically separable.}
}
]

This answers the narrow question raised in v0.11:

> Are the four coordinates necessarily redundant simply because they were correlated in merger simulations?

No.

Their previous collinearity was at least partly a property of the chosen transition family rather than an unavoidable identity.

## 11. What v0.12 does **not** establish

The current scores are still assigned as normalized diagnostic examples.

Therefore v0.12 does not establish that:

- (B,C,A,P) are fundamental observables;
- the numerical values used are physically correct;
- every component has a universal definition;
- four dimensions are necessary in nature;
- any component causes a temporal effect.

The most important limitation is:

[
\boxed{
\text{hand-assigned feature diversity is not physical feature independence}.
}
]

## 12. Operational definitions now become mandatory

The next stage must replace illustrative entries of (Z) with quantities computed from explicit physical models.

Candidate definitions remain:

### Binding

[
B=
\frac{E_{sep}}
{E_{sep}+E_*}.
]

### Correlation

For a two-part quantum system,

[
C=
\frac{I(A:B)}{I_{max}}.
]

### Autonomy

Use an interaction-graph or dynamical-flow diagnostic, such as normalized boundary conductance or an internal/external generator ratio.

### Persistence

Use predictive retention,

[
P=
F(
\rho_{actual}(t+\Delta),
\rho_{predicted}(t+\Delta)
),
]

or an explicitly declared effective-observable prediction score.

Only when all four values are generated by model dynamics should rank analysis be interpreted physically.

## 13. A deeper issue: domain dependence

The effective rank of (Z) may depend on the family of systems being studied.

For example:

- atomic bound-state experiments may excite mainly (B,C);
- decoherence experiments may excite mainly (C,A);
- biological/open-system examples may emphasize (P,A).

Therefore there may be no universal statement that all four axes are equally informative at every scale.

A more defensible structure may be:

[
\mathbf I(S|E;\ell,\Delta\tau,\mathcal O).
]

This preserves the scale/context dependence already identified in v0.2.

## 14. Systemhood is a profile, not a scalar

v0.12 strengthens the earlier decision not to collapse everything prematurely into

[
I(S)\in[0,1].
]

A scalar can hide whether a system is:

- strongly bound but fragile;
- unbound but autonomous;
- highly correlated but environmentally leaky;
- persistent despite material turnover.

Thus the working representation remains

[
\boxed{
\mathbf I=(B,C,A,P).
}
]

Any future scalar systemhood score must be task-specific and justified rather than assumed fundamental.

## 15. Consequence for the temporal hypothesis

The temporal law should remain suspended until the basis is operationalized.

The project should not yet fit

[
\Delta R
=
\sum_k\theta_kX_k
]

to additional synthetic temporal data.

Doing so would create false precision because the (X_k) themselves are not yet uniformly derived from physical dynamics.

This is a deliberate research stop.

## 16. v0.13 target — model-derived systemhood benchmark suite

The next stage should replace hand-assigned rows with explicit finite-dimensional models.

A practical first benchmark suite is:

1. **product qubits:** (C=0), no binding;
2. **Bell pair after interaction is off:** high (C), low continuing autonomy/binding proxy;
3. **interacting dimer:** nonzero internal coupling and controllable environment coupling;
4. **dephasing open dimer:** varying (C) and (P);
5. **metastable effective state:** high predictive (P) despite microscopic evolution.

For every model, compute as many entries of

[
(B,C,A,P)
]

as the operational definitions genuinely support.

Missing or ill-defined entries should be recorded as **undefined**, not filled by intuition.

Then construct the physically derived feature matrix

[
Z_{phys}
]

and repeat:

- rank;
- singular spectrum;
- condition number;
- feature reconstruction;
- perturbation/error propagation.

The v0.13 question is therefore:

[
\boxed{
\text{Does }(B,C,A,P)\text{ remain separable when the numbers come from dynamics rather than our choices?}
}
]

That is the required gate before temporal phenomenology resumes.
