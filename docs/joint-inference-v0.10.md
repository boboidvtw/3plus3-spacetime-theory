# Joint Inference v0.10 — Cross-System Predictivity

> **Status:** synthetic multi-experiment inference. No real measurements are analyzed and no evidence for emergent time is claimed.

Executable notebook:

[`notebooks/joint_inference_v0.10.ipynb`](../notebooks/joint_inference_v0.10.ipynb)

## 1. Why joint inference matters

A flexible temporal correction fitted independently to every dataset would have little predictive content.

v0.10 therefore imposes a stronger hypothesis:

[
\boxed{
\epsilon_1=\epsilon_2=\cdots=\epsilon_M\equiv\epsilon.
}
]

The nuisance physics remains experiment-specific.

For experiment (m),

[
y_m(t)
=
\epsilon F_m(t)
+
\beta_m G_m(t)
+
\gamma_m D_m(t)
+
c_m
+
n_m(t).
]

Thus the temporal law must generalize across different dynamical-identity histories.

## 2. Synthetic experiment family

Five mock experiments are generated:

1. slow merger/separation;
2. fast merger/separation;
3. asymmetric identity transition;
4. strong conventional nuisance shift;
5. no-transition control.

The first four receive different (F_m(t)) shapes but share the injected

[
\epsilon_{true}=1.8\times10^{-4}.
]

The control has

[
F_{control}=0.
]

All experiments have independent interaction, drift and offset nuisance coefficients.

## 3. Joint design matrix

Stack all observations into

[
\mathbf y=
(\mathbf y_1,\ldots,\mathbf y_M)^T.
]

The joint parameter vector is

[
\boldsymbol\theta
=
(
\epsilon,
\beta_1,\gamma_1,c_1,
\ldots,
\beta_M,\gamma_M,c_M
)^T.
]

Only the first column of the design matrix is global across experiments.

This prevents the temporal model from explaining each dataset with a separate arbitrary amplitude.

## 4. Global estimate

For Gaussian equal-variance noise,

[
\hat{\boldsymbol\theta}
=
(X^TX)^{-1}X^T\mathbf y.
]

The uncertainty of the common temporal parameter is

[
\sigma_\epsilon
=
\sigma
\sqrt{
[(X^TX)^{-1}]_{00}
}.
]

The relevant synthetic recovery statistic is

[
Z_\epsilon
=
\frac{\hat\epsilon}{\sigma_\epsilon}.
]

The numerical value is only a property of the declared mock experiment.

It must not be interpreted as an empirical detection significance.

## 5. Null versus temporal model

Define

[
M_0:\epsilon=0
]

and

[
M_1:\epsilon\neq0.
]

The notebook compares the residual sums of squares and

[
\Delta\chi^2
=
\chi_0^2-\chi_1^2.
]

It also reports

[
\mathrm{BIC}
=
N\ln(\mathrm{RSS}/N)
+
k\ln N.
]

With the sign convention used in the notebook,

[
\Delta\mathrm{BIC}
=
\mathrm{BIC}_0-\mathrm{BIC}_1.
]

Positive values favor the temporal mock model.

Again, because the data were generated with an injected temporal term, model preference is an injection-recovery validation, not evidence.

## 6. Leave-one-experiment-out prediction

A more demanding test is:

1. remove experiment (m);
2. infer (\epsilon) from all remaining experiments;
3. freeze that (\epsilon);
4. fit only conventional nuisance parameters in the held-out experiment;
5. evaluate predictive residuals.

Symbolically,

[
\hat\epsilon_{-m}
=
\operatorname{Fit}
\{D_{k\neq m}\}.
]

Then

[
D_m
\stackrel{?}{\sim}
\hat\epsilon_{-m}F_m
+
\text{nuisance}_m.
]

This tests cross-system prediction rather than interpolation.

## 7. Why this is stronger than significance

A model may obtain a large (Z)-score by fitting one highly informative dataset.

But a proposed law of nature should survive changes in:

- transition speed;
- system asymmetry;
- nuisance amplitude;
- event duration.

Therefore cross-system prediction is more important than maximizing a single synthetic significance.

## 8. Per-experiment consistency

The notebook also estimates (\epsilon_m) separately for each sensitive experiment.

A universal temporal hypothesis predicts statistical compatibility:

[
\epsilon_m
\sim
\epsilon.
]

If future real experiments require incompatible values,

[
\epsilon_1\neq\epsilon_2\neq\epsilon_3
]

beyond uncertainty, the simple universal ansatz is falsified.

The correct response would not be to assign a new free (\epsilon_m) to every system unless a deeper theory independently predicts those differences.

## 9. Role of the no-transition control

The control has

[
F=0.
]

Therefore it contains no direct information about (\epsilon).

Its role is different:

- characterize nuisance behavior;
- test common environmental models;
- detect pipeline artifacts;
- provide a negative-control dataset.

A control that unexpectedly demands a temporal residual would be evidence against the analysis model before it is evidence for new physics.

## 10. Null injection-recovery

v0.10 repeats the complete pipeline on synthetic datasets generated with

[
\epsilon_{true}=0.
]

Over repeated realizations, the fitted standardized statistic

[
Z=\hat\epsilon/\sigma_\epsilon
]

should be centered near zero with approximately unit variance under the declared Gaussian model.

This tests whether the analysis procedure itself creates a systematic false temporal signal.

## 11. Theoretical consequence

The Version 2 hypothesis is now stronger than

> “some systems may have different local times.”

Its first quantitatively testable form is closer to:

> There exists a common law linking objective dynamical-identity structure to differential operational clock evolution across physically distinct systems.

That law must explain multiple (F_m(t)) with shared parameters.

## 12. Hierarchical extension

The natural statistical extension is a hierarchical model.

A strict universal theory has

[
\epsilon_m=\epsilon.
]

A controlled universality-breaking theory could instead posit

[
\epsilon_m
\sim
\mathcal N(\epsilon,\sigma_{sys}^2),
]

but only if (\sigma_{sys}) has physical motivation.

Introducing unexplained between-system scatter simply to rescue failed universality would weaken falsifiability.

## 13. Candidate real-experiment selection criteria

v0.10 is not yet selecting hardware, but it now tells us what properties a useful platform must have.

A candidate experiment should provide:

- a high-quality operational clock observable;
- a controllable and independently characterized identity transition;
- a matched no-transition or weak-transition control;
- conventional clock shifts that can be modeled independently;
- repeated trials;
- multiple transition speeds/shapes;
- enough stability to compare a shared parameter across configurations.

## 14. Stop condition before real experiments

The project should **not** jump directly from a synthetic fit to claims about atomic clocks or other precision platforms.

Before selecting a real system, the theory should pass one more conceptual stage:

[
\boxed{
\text{derive or strongly constrain }F_i
}
]

from the systemhood/dynamic-identity quantities developed in v0.2–v0.6.

At present the shape of (F) is still chosen phenomenologically.

This functional freedom is now the largest theoretical weakness.

## 15. v0.10 conclusion

The project has moved from single-dataset detectability to cross-system predictivity.

The decisive requirement is now:

[
\boxed{
\text{one shared temporal law must survive multiple distinct identity events}.
}
]

A theory that can fit only one transition profile is insufficient.

## 16. v0.11 target — constrain the functional law

The next stage should reconnect the temporal ansatz to the systemhood vector

[
\mathbf I=(B,C,A,P).
]

Rather than freely choosing (F(t)), define a small family such as

[
F_i
=
\alpha_B B_i
+
\alpha_C C_i
+
\alpha_A A_i
+
\alpha_P P_i
+
\alpha_{\dot A}\dot A_i
+
\alpha_{\dot P}\dot P_i.
]

Then impose:

1. dimensionless consistency;
2. relabeling invariance;
3. no arbitrary partition dependence;
4. standard limit;
5. minimal parameter count;
6. cross-system shared coefficients;
7. regularization/model-selection penalties;
8. rejection of terms that are observationally degenerate with known clock shifts.

The goal of v0.11 should be **functional-law compression**: determine whether the temporal hypothesis can remain predictive with only a few shared coefficients.

Only after that stage should the repository begin a literature-backed search for candidate real clock platforms.


---

## 17. v0.11 continuation

Functional-law compression is now implemented in:

- [`notebooks/functional_law_compression_v0.11.ipynb`](../notebooks/functional_law_compression_v0.11.ipynb)
- [`docs/functional-law-compression-v0.11.md`](functional-law-compression-v0.11.md)

The main theoretical correction is that (\epsilon) cannot be interpreted independently of the normalization of (F): the transformation (F\to cF, \epsilon\to\epsilon/c) leaves the phenomenology unchanged. v0.11 therefore works with directly identifiable product coefficients (\theta_k=\epsilon\alpha_k).

It also exposes a mechanistic-identifiability problem: systemhood features generated from the same merger profile can be strongly collinear. v0.12 should deliberately construct counterexample systems that vary (B,C,A,P) independently enough to test whether this basis is physically meaningful.
