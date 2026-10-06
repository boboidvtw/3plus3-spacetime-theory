# Functional-Law Compression v0.11 — Reducing Temporal Freedom

> **Status:** synthetic model-selection study. No fundamental temporal law is derived and no real experimental data are used.

Executable notebook:

[`notebooks/functional_law_compression_v0.11.ipynb`](../notebooks/functional_law_compression_v0.11.ipynb)

## 1. Problem

v0.8–v0.10 showed how a hypothetical temporal residual could be detected statistically.

The largest remaining weakness was functional freedom:

[
F_i(t)
]

could be chosen too flexibly.

v0.11 reverses direction. Instead of adding mechanisms, it asks:

[
\boxed{
\text{How little functional freedom can the hypothesis survive with?}
}
]

## 2. Restricted basis

Reconnect the temporal ansatz to the systemhood profile

[
\mathbf I=(B,C,A,P).
]

Consider a shared linear basis

[
F_i
=
\alpha_B\tilde B_i
+
\alpha_C\tilde C_i
+
\alpha_A\tilde A_i
+
\alpha_P\tilde P_i
+
\alpha_{\dot A}\dot A_i
+
\alpha_{\dot P}\dot P_i,
]

where tildes denote centered dimensionless features.

The measurable coefficients in a linear residual model are

[
\theta_k=\epsilon\alpha_k.
]

Without an independent normalization convention for (F), (\epsilon) and all (\alpha_k) possess a scale degeneracy.

Therefore v0.11 fits (\theta_k) directly.

This is an important correction:

[
\boxed{
\epsilon\text{ is not separately identifiable from the normalization of }F.
}
]

A later theory must fix the normalization of (F) before assigning physical meaning to (\epsilon).

## 3. Candidate nested models

The notebook compares increasingly flexible models:

[
M_1: A,
]

[
M_2: A+\dot A,
]

[
M_3: A+P+\dot A,
]

[
M_4: B+C+A+P,
]

[
M_5: B+C+A+P+\dot A+\dot P.
]

Every temporal coefficient is shared across all synthetic experiments.

Every experiment retains its own nuisance coefficients.

## 4. Sparse injection

For validation, synthetic data are generated from a deliberately sparse hidden law:

[
\boxed{
F_{true}
=
0.55(A-0.5)
+
0.32\dot A.
}
]

The purpose is not to privilege this law physically.

It asks whether the model-selection pipeline can recover a compact generating structure rather than automatically favoring the largest model.

## 5. BIC compression

For each model,

[
\mathrm{BIC}
=
N\ln(\mathrm{RSS}/N)
+
k\ln N.
]

Adding a basis term is justified only if its reduction in residual error outweighs the parameter penalty.

This implements a simple principle:

[
\boxed{
\text{extra temporal freedom must earn its existence predictively}.
}
]

A larger model is not automatically considered more successful.

## 6. Leave-one-experiment-out validation

Each candidate functional law is also tested by:

1. fitting its shared temporal coefficients on all but one synthetic experiment;
2. holding those coefficients fixed;
3. fitting only nuisance coefficients on the held-out experiment;
4. measuring predictive RMSE.

This protects against selecting a compact model that happens to fit globally but fails to generalize across identity-event shapes.

## 7. Collinearity problem

A major v0.11 result is conceptual rather than numerical.

In simple merger simulations,

[
B(t),C(t),A(t)
]

can all be generated from the same underlying transition window.

Then

[
|\operatorname{Corr}(B,C)|\approx1,
\quad
|\operatorname{Corr}(B,A)|\approx1,
\quad
|\operatorname{Corr}(C,A)|\approx1.
]

Under such conditions, even excellent data cannot reliably determine which physical component carries the temporal effect.

The model may predict well while its coefficients remain physically uninterpretable.

Therefore:

[
\boxed{
\text{predictive identifiability}
\neq
\text{mechanistic identifiability}.
}
]

## 8. Consequence for experimental design

Future experiments must not merely produce a large systemhood change.

They should produce **feature diversity**.

For example, useful complementary regimes would independently vary:

- binding with little change in correlation;
- correlation with negligible binding;
- autonomy while persistence remains high;
- persistence under material turnover;
- fast versus slow boundary changes.

This connects directly to the earlier counterexamples:

- bound hydrogen;
- separated entangled qubits;
- open persistent systems;
- weakly interacting free particles.

Those examples are no longer merely philosophical stress tests. They become experimental basis-separation tools.

## 9. Scale degeneracy of the temporal ansatz

The original form

[
\frac{d\tau_i}{dt}
=
N_i^{std}
[1+\epsilon F_i]
]

is invariant under

[
F_i\rightarrow cF_i,
\qquad
\epsilon\rightarrow\epsilon/c.
]

Therefore (\epsilon) alone has no invariant meaning until a normalization convention or fundamental derivation fixes the scale of (F).

Possible future conventions include

[
\|F\|_{reference}=1
]

on a declared reference process, or deriving (F) from normalized systemhood observables.

Until then, reported constraints should be placed on the product coefficients (\theta_k), not on a supposedly fundamental (\epsilon).

## 10. Derivative terms require care

Terms such as

[
\dot A
]

depend on the parameter with respect to which the derivative is taken.

If (t) is merely a coordinate or bookkeeping parameter, a raw derivative may not be invariant.

A covariant future formulation must replace it with an operationally defined rate, for example relative to a standard reference clock:

[
\frac{dA}{d\tau_{ref}}.
]

Thus v0.11 treats derivative terms as toy-model features only.

## 11. Minimality hierarchy

A candidate temporal law should be evaluated in this order:

1. **null:** no temporal correction;
2. one systemhood component;
3. one component + one transition term;
4. small multicomponent model;
5. only then higher-order or nonlinear terms.

The theory should stop expanding when additional complexity is not supported out of sample.

This prevents the framework from becoming an arbitrary universal function approximator.

## 12. Failure conditions

The functional-law program should be considered unsuccessful if:

1. different experiments require unrelated basis terms;
2. coefficients change substantially under small changes in coarse graining;
3. strong collinearity prevents physical interpretation;
4. higher complexity is always required as new systems are added;
5. the null model performs equally well out of sample;
6. selected terms are degenerate with standard clock-systematic templates;
7. no normalization gives (F) operational meaning.

## 13. Current strongest compact hypothesis

v0.11 does **not** establish a preferred law of nature.

However, it identifies the scientifically useful form of the next hypothesis:

[
\boxed{
\Delta R_{ij}
=
\sum_k
\theta_k
\left[
X_{k,i}-X_{k,j}
\right]
+
\text{standard corrections},
}
]

where the (X_k) are a small number of objective, normalized systemhood/transition observables.

This form is directly relational and avoids pretending that an arbitrary absolute local-time correction is observable.

## 14. Theory status after v0.11

The Version 2 chain is now:

[
\text{dynamical individuation}
\rightarrow
\mathbf I=(B,C,A,P)
\rightarrow
\text{operational clocks}
\rightarrow
\Delta R
\rightarrow
\text{identifiability}
\rightarrow
\boxed{\text{functional compression}}.
]

The project has therefore reached the point where more toy fitting alone has diminishing value.

The next useful stage should attack the physical meaning and independence of (B,C,A,P).

## 15. v0.12 target — basis-separating counterexamples

Construct a suite of deliberately different finite-dimensional systems designed to separate the systemhood components:

1. high (C), low (B): separated entangled qubits;
2. high (B), controlled (C): bound/interacting pair;
3. high (P), changing constituents: open persistent effective system;
4. changing (A), approximately fixed internal state;
5. null free-particle/control case.

Then compute the feature matrix

[
Z=
[B,C,A,P,\ldots]
]

and test its rank and condition number.

The target is not another temporal detection.

It is:

[
\boxed{
\text{Can the proposed physical ingredients actually be varied independently enough to define a law?}
}
]

If not, the (B,C,A,P) decomposition itself must be revised before proceeding toward real experiments.
