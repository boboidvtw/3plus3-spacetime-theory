# Temporal Residual v0.8 — A Falsifiable Phenomenological Ansatz

> **Status:** deliberately hypothetical. The correction introduced here is not derived from a fundamental theory, is not supported by experimental evidence, and must not be described as a discovered law.

Executable notebook:

[`notebooks/temporal_residual_v0.8.ipynb`](../notebooks/temporal_residual_v0.8.ipynb)

## 1. Purpose

v0.7 established an operational clock and the correct null residual

[
\Delta R_{ij}
=
R_{ij}^{obs}-R_{ij}^{std}.
]

v0.8 asks:

> If dynamical identity really modified local temporal evolution, what mathematical signal would we search for?

The goal is not explanation. It is falsifiability.

## 2. Phenomenological ansatz

For each system (S_i), write

[
\boxed{
\frac{d\tau_i}{dt}
=
N_i^{std}
\left[
1+\epsilon F_i
\right]
}
]

where

[
F_i
=
F(
\mathbf I_i,
\dot{\mathbf I}_i,
\ldots
).
]

Here:

- (N_i^{std}) is the complete standard prediction for the local clock rate;
- (\epsilon) is a small dimensionless phenomenological parameter;
- (F_i) is a dimensionless function of objective dynamical-identity diagnostics.

Neither (\epsilon) nor (F_i) is currently derived.

## 3. First toy functional

For the notebook only, use a scalar effective identity profile (I_i(t)) and

[
\boxed{
F_i
=
a(I_i-1/2)
+
b\tanh(2\dot I_i)
}
]

with illustrative constants

[
a=0.6,
\qquad
b=0.35.
]

The first term represents sensitivity to the current identity profile.

The second term represents sensitivity to an identity transition.

This is a **signal generator**, not a law of nature.

## 4. Relational prediction

For two clocks,

[
R_{ij}^{new}
=
\frac{N_i^{std}}{N_j^{std}}
\frac{1+\epsilon F_i}
{1+\epsilon F_j}.
]

Thus

[
\boxed{
\Delta R_{ij}
=
R_{ij}^{std}
\left[
\frac{1+\epsilon F_i}
{1+\epsilon F_j}
-1
\right].
}
]

For small (\epsilon),

[
\boxed{
\Delta R_{ij}
\approx
\epsilon R_{ij}^{std}
(F_i-F_j)
+
O(\epsilon^2).
}
]

This already produces a useful experimental principle:

> a universal common correction to all clocks cancels in a relational comparison.

Only differential temporal response is visible through (R_{ij}).

## 5. Standard-limit test

The notebook verifies

[
\epsilon=0
\quad\Rightarrow\quad
\Delta R_{ij}=0.
]

Therefore

[
\boxed{
\lim_{\epsilon\to0}
\text{Version 2 phenomenology}
=
\text{standard clock dynamics}.
}
]

Any future modification that fails this test should be rejected.

## 6. Positivity / monotonicity guardrail

A local clock rate must remain forward-running in this simple model:

[
1+\epsilon F_i>0.
]

The notebook explicitly tests positivity over the scanned parameter range.

A more complete theory would need to decide whether clock-rate zeros or sign changes are physically admissible. v0.8 does not allow them.

## 7. Transitivity is preserved

Because every local rate is first defined relative to the same auxiliary parameter,

[
N_i=\frac{d\tau_i}{dt},
]

relational ratios satisfy

[
R_{ij}=\frac{N_i}{N_j}.
]

Therefore

[
\boxed{
R_{ij}R_{jk}=R_{ik}
}
]

identically wherever the ratios are defined.

The notebook verifies this numerically for three clocks.

Thus v0.8 remains an **integrable local-clock model**.

It does not invoke non-integrable temporal geometry.

## 8. Relabeling test

For the same physical pair,

[
R_{ji}=\frac1{R_{ij}}.
]

The notebook verifies

[
R_{ij}R_{ji}=1
]

to numerical precision.

Merely renaming (A\leftrightarrow B) therefore cannot create or destroy a temporal anomaly.

This is a minimal permutation-covariance check.

## 9. Identical-profile null test

If two systems have

[
N_A^{std}=N_B^{std}
]

and

[
F_A=F_B,
]

then

[
\boxed{
R_{AB}^{new}=1
}
]

regardless of (\epsilon).

Thus the ansatz does not produce a relative effect merely because two clocks are declared to belong to different systems.

This guards against a semantic subsystem effect.

## 10. Identity-event signal shape

The toy (F_i) contains both (I_i) and (\dot I_i).

Therefore a merger/separation episode can generate two qualitatively different signatures:

### State-like contribution

[
\Delta R\propto I_A-I_B.
]

This persists while the two systems occupy different identity regimes.

### Transition-like contribution

[
\Delta R\propto
\tanh(2\dot I_A)
-
\tanh(2\dot I_B).
]

This becomes localized near formation/separation events.

An experiment could in principle distinguish these shapes.

## 11. A crucial degeneracy

Suppose a conventional interaction shifts a clock frequency by

[
\delta\omega_i^{int}(t).
]

Then the measured rate may look like

[
\dot\tau_i
=
N_i^{std}
+
\delta N_i^{int}
+
\delta N_i^{new}.
]

Without an independently calibrated standard model, (\delta N_i^{new}) can be absorbed into an ordinary frequency shift.

Therefore the central experimental problem is not merely measuring a clock shift.

It is demonstrating that the residual cannot be explained by:

- interaction energy shifts;
- AC/DC Stark or Zeeman-like shifts;
- collisional shifts;
- decoherence;
- state-preparation changes;
- measurement back-action;
- gravitational/time-dilation effects;
- thermal/environmental perturbations.

This degeneracy is one of the strongest challenges to the hypothesis.

## 12. Common-mode invisibility

If

[
F_i(t)=F_{common}(t)
]

for every clock, then

[
R_{ij}^{new}=R_{ij}^{std}.
]

Thus relational-clock experiments are blind to a perfectly universal multiplicative correction.

This means the current framework can test **differential emergent time**, not an unobservable universal rescaling of time.

That distinction should remain explicit.

## 13. Connection to systemhood

v0.8 deliberately does not set

[
F_i=I_i.
]

The full systemhood profile remains

[
\mathbf I_i=(B_i,C_i,A_i,P_i).
]

A future theory might use

[
F_i=
F(B_i,C_i,A_i,P_i,
\dot B_i,\dot C_i,\dot A_i,\dot P_i).
]

However, introducing many arbitrary coefficients would make the theory unfalsifiable through overfitting.

Therefore the next versions must strongly constrain functional freedom.

## 14. Falsification criteria

This phenomenological branch should be considered unsupported or falsified if:

1. all apparent (\Delta R) is explained by standard clock shifts;
2. fitted (F_i) requires arbitrary observer-selected partitions;
3. the result changes under pure relabeling;
4. no single functional form predicts multiple experiments;
5. the inferred (\epsilon) is inconsistent across equivalent clock systems;
6. the effect disappears when environmental/systematic corrections improve;
7. the model requires violation of causality or established conservation laws without independent evidence.

## 15. What would count as progress

A meaningful experimental anomaly would require a reproducible residual

[
\Delta R_{ij}\neq0
]

that:

- correlates with an independently measured dynamical-identity transition;
- survives the complete standard-physics model;
- follows the same functional form across multiple systems;
- scales with a common parameter (\epsilon);
- respects the declared consistency conditions.

Only then would it be reasonable to investigate whether the effect deserves a temporal interpretation.

## 16. Current epistemic status

The project has now progressed from:

[
\text{verbal intuition}
]

to

[
\text{systemhood diagnostics}
]

to

[
\text{dynamic identity}
]

to

[
\text{operational clocks}
]

to

[
\boxed{
\text{explicit falsifiable residual template}.
}
]

But the strongest statement supported by v0.8 is only:

> **If** temporal identity modifies clock rates according to the declared ansatz, **then** a differential relational residual of the derived form should occur.

There is currently no evidence that nature contains the (\epsilon F_i) term.

## 17. v0.9 target — identifiability and mock experiment

The next stage should treat the problem as an inference experiment.

Generate synthetic clock data containing:

[
\text{standard interaction shift}
+
\text{noise}
+
\epsilon F_i
]

and ask whether (\epsilon) can actually be recovered without confusing it with ordinary nuisance parameters.

The key questions are:

1. What signal-to-noise ratio is required?
2. Which nuisance shifts are degenerate with (F_i)?
3. Does transition-localized (\dot I_i) improve identifiability?
4. Can a control clock with no identity transition reject common-mode systematics?
5. Can one value of (\epsilon) explain multiple merger/separation profiles?

This is the correct next step before discussing real experiments.


---

## 18. v0.9 continuation

Synthetic identifiability analysis is now implemented in:

- [`notebooks/mock_experiment_v0.9.ipynb`](../notebooks/mock_experiment_v0.9.ipynb)
- [`docs/mock-experiment-v0.9.md`](mock-experiment-v0.9.md)

The central result is structural: if the temporal template lies in the span of ordinary nuisance templates,

[
F\in\operatorname{span}\{G_k\},
]

then (\epsilon) is not identifiable from that experiment, regardless of how small the random measurement noise becomes.

The next stage should therefore test one shared (\epsilon) across multiple synthetic experiments with experiment-specific nuisance parameters.
