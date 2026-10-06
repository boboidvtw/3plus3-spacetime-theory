# Mock Experiment v0.9 — Identifiability Before Experiment Design

> **Status:** synthetic-data inference study. No real clock data are analyzed and no temporal anomaly is claimed.

Executable notebook:

[`notebooks/mock_experiment_v0.9.ipynb`](../notebooks/mock_experiment_v0.9.ipynb)

## 1. Central question

v0.8 produced a falsifiable residual template,

[
\Delta R(t)
\approx
\epsilon F(t).
]

But an observable clock residual generally contains ordinary effects:

[
y(t)
=
\epsilon F(t)
+
\sum_k\beta_k G_k(t)
+
n(t).
]

Here (G_k) are conventional nuisance templates and (n(t)) is measurement noise.

v0.9 asks the necessary inference question:

[
\boxed{
\text{Can }\epsilon\text{ actually be identified separately from }\beta_k?
}
]

## 2. Synthetic experiment

The notebook injects a known temporal coefficient

[
\epsilon_{true}=2\times10^{-4}
]

into synthetic data.

The data also contain:

- a plateau-like interaction shift;
- a slow drift/thermal-like component;
- a calibration offset;
- Gaussian measurement noise.

The numerical values are illustrative only.

## 3. Linear inference model

Write

[
\mathbf y
=
X\boldsymbol\theta
+
\mathbf n,
]

where

[
\boldsymbol\theta
=
(\epsilon,\beta_{int},\beta_{drift},c).
]

For independent equal-variance Gaussian noise,

[
\hat{\boldsymbol\theta}
=
(X^TX)^{-1}X^T\mathbf y
]

and

[
\operatorname{Cov}(\hat{\boldsymbol\theta})
=
\sigma^2(X^TX)^{-1}.
]

This makes identifiability explicit through the geometry of the design matrix.

## 4. Deliberately wrong model

The notebook first fits (\epsilon) while omitting the conventional interaction template.

This can bias the recovered (\epsilon), because the temporal template and interaction shift partially overlap.

The lesson is fundamental:

[
\boxed{
\text{an incomplete null model can manufacture an apparent temporal signal}.
}
]

Therefore improving standard-systematic modeling is not an optional cleanup step; it is part of the test itself.

## 5. Full nuisance model

The complete toy fit includes

[
F(t),\quad
G_{int}(t),\quad
G_{drift}(t),\quad
1.
]

The parameter covariance matrix reveals correlations between (\epsilon) and nuisance coefficients.

Even when (\epsilon) is recoverable in synthetic data, strong covariance enlarges its uncertainty.

Thus a quoted “clock anomaly” without a nuisance-correlation analysis would be scientifically insufficient.

## 6. Exact degeneracy

The strongest v0.9 result is algebraic.

If

[
F(t)=G_{int}(t),
]

then the model becomes

[
y(t)
=
(\epsilon+\beta_{int})F(t)
+\cdots.
]

Only the sum is observable.

The design matrix loses rank:

[
\operatorname{rank}(X)<N_{parameters}.
]

Therefore

[
\boxed{
\epsilon\text{ is non-identifiable}.
}
]

Reducing random noise cannot solve exact structural degeneracy.

External calibration, a different experiment, or a more distinctive theoretical prediction is required.

## 7. Why transition-localized signals help

The v0.8 functional included both state-like and transition-like pieces.

Define a transition template schematically as

[
T(t)
\sim
\tanh(k\dot I).
]

It is concentrated near formation and separation events rather than throughout the interaction plateau.

The notebook compares template overlap through

[
\cos\theta
=
\frac{F\cdot G}
{\|F\|\|G\|}.
]

A smaller absolute overlap means improved linear identifiability.

In the toy model, the transition-localized template is substantially less aligned with the plateau interaction template.

This suggests a concrete theoretical preference:

[
\boxed{
\text{predictive event-specific structure is more testable than a generic frequency shift}.
}
]

This is not evidence that nature uses (\dot I); it is a criterion for useful model building.

## 8. Control clock/channel

The notebook adds a control channel with the same nuisance structure but no injected temporal-identity signal.

Taking a difference,

[
y_{target}-y_{control},
]

can suppress common-mode nuisance contributions.

The noise variance increases if the two channels have independent noise, but systematic rejection may outweigh that cost.

A future experimental design should therefore favor matched control systems.

## 9. Noise threshold

For a declared design matrix, the expected standard error is

[
\sigma_\epsilon
=
\sigma
\sqrt{
[(X^TX)^{-1}]_{\epsilon\epsilon}
}.
]

The expected significance is

[
Z
=
\frac{|\epsilon|}
{\sigma_\epsilon}.
]

The notebook scans measurement noise and displays the expected detection significance.

The important point is not the toy numerical threshold; it is the scaling law:

[
Z
\propto
\frac{|\epsilon|}
{\sigma}
\times
\text{identifiability factor}.
]

A badly conditioned design can destroy sensitivity even at low noise.

## 10. Identifiability metric

A useful future diagnostic is the variance-inflation factor for (\epsilon):

[
\mathrm{VIF}_\epsilon
=
\frac{
[(X^TX)^{-1}]_{\epsilon\epsilon}
}{
1/(F^TF)
}.
]

It compares the actual variance with the ideal variance obtained if the temporal template were fitted alone.

Large VIF means nuisance degeneracy dominates.

This should become a standard reporting quantity in later mock experiments.

## 11. Cross-system prediction is essential

A flexible (F_i(t)) fitted separately to every experiment would be nearly impossible to falsify.

Therefore a serious theory must use a common functional law:

[
F_i
=
F(
B_i,C_i,A_i,P_i,
\dot B_i,\dot C_i,\dot A_i,\dot P_i;
\boldsymbol\alpha
)
]

with a small shared parameter set (\boldsymbol\alpha).

Then multiple experiments must be explained by the same

[
\epsilon,
\qquad
\boldsymbol\alpha.
]

This changes the problem from curve fitting to cross-system prediction.

## 12. Stronger falsification rule

v0.9 adds a new rejection criterion:

[
\boxed{
F\in\operatorname{span}\{G_1,\ldots,G_n\}
\Rightarrow
\text{the experiment cannot identify temporal physics}.
}
]

An experiment in this condition should not be presented as a test of the hypothesis, regardless of nominal clock precision.

## 13. Experimental-design principle

The best future experiment is not necessarily the clock with the smallest raw uncertainty.

It is the experiment maximizing something like

[
\frac{
\|F_\perp\|
}{
\sigma
},
]

where (F_\perp) is the component of the temporal template orthogonal to the nuisance-template subspace.

This reframes experimental design:

[
\boxed{
\text{maximize distinctive signal, not merely precision}.
}
]

## 14. What v0.9 establishes

The project now has a complete methodological chain:

[
\text{system identity}
\rightarrow
\text{operational clocks}
\rightarrow
\text{hypothetical residual}
\rightarrow
\boxed{\text{statistical identifiability}}.
]

The result is sobering but useful:

> A temporal residual that looks like an ordinary interaction-induced clock shift is not scientifically separable from that shift.

Therefore the theory must predict structure that standard nuisance physics does not naturally mimic.

## 15. v0.10 target — multi-experiment inference

The next stage should simulate several physically different identity events but force them to share the same (\epsilon).

For example:

1. slow merger / slow separation;
2. fast merger / fast separation;
3. asymmetric systemhood change;
4. no-transition control;
5. different interaction-shift amplitudes.

Fit all datasets jointly:

[
\mathcal L_{joint}
=
\prod_m
\mathcal L_m(
\epsilon,
\boldsymbol\alpha,
\boldsymbol\beta_m
).
]

The temporal parameter (\epsilon) is global.

Nuisance parameters (\boldsymbol\beta_m) are experiment-specific.

Then compare:

- null model (M_0: \epsilon=0);
- temporal model (M_1: \epsilon\neq0).

This will test whether one common temporal law can explain multiple synthetic systems better than independent nuisance shifts.

Only after that should the project begin selecting candidate real clock platforms.


---

## 16. v0.10 continuation

Cross-system joint inference is now implemented in:

- [`notebooks/joint_inference_v0.10.ipynb`](../notebooks/joint_inference_v0.10.ipynb)
- [`docs/joint-inference-v0.10.md`](joint-inference-v0.10.md)

Multiple synthetic identity-event profiles now share one global (\epsilon), while each experiment retains independent interaction, drift and offset nuisance parameters. The notebook adds null-vs-temporal model comparison, leave-one-experiment-out prediction, per-experiment consistency checks, a no-transition control, and repeated (\epsilon=0) injection-recovery tests.

The remaining major weakness is no longer statistical methodology but functional freedom: (F_i) is still phenomenological. v0.11 should constrain it directly from the systemhood profile (\mathbf I=(B,C,A,P)).
