# Quantitative Methods

Quant is the mathematical backbone of the CFA curriculum. Level 1 focuses on tools you will apply in every other topic area — especially Fixed Income, Equity, and Portfolio Management.

## Time Value of Money

The core idea: **a dollar today is worth more than a dollar tomorrow** because of its earning potential.

### Key formulas

**Future Value (FV)**
$$FV = PV \times (1 + r)^n$$

**Present Value (PV)**
$$PV = \frac{FV}{(1 + r)^n}$$

**Annuity (PV of regular payments)**
$$PV = PMT \times \frac{1 - (1+r)^{-n}}{r}$$

Where: PV = present value, FV = future value, r = interest rate per period, n = number of periods, PMT = payment per period.

## Statistics Essentials

| Measure | What it tells you |
|---|---|
| Mean | Average value |
| Median | Middle value (less affected by outliers) |
| Variance | Average squared deviation from the mean |
| Standard deviation | Square root of variance — same units as data |
| Covariance | How two variables move together |
| Correlation | Covariance scaled to [-1, +1] |

**Correlation formula:**
$$\rho_{XY} = \frac{Cov(X,Y)}{\sigma_X \cdot \sigma_Y}$$

## Probability

**Multiplication rule (independent events):**
$$P(A \text{ and } B) = P(A) \times P(B)$$

**Addition rule:**
$$P(A \text{ or } B) = P(A) + P(B) - P(A \text{ and } B)$$

**Bayes' theorem:**
$$P(A|B) = \frac{P(B|A) \times P(A)}{P(B)}$$

## Common distributions

- **Normal** — symmetric, mean = median = mode. Described by μ and σ.
- **Lognormal** — used for asset prices (can't go below zero).
- **Student's t** — used when sample size is small or population variance is unknown.

## Hypothesis testing

1. State H₀ (null) and Hₐ (alternative)
2. Choose significance level α (typically 5%)
3. Calculate test statistic
4. Compare to critical value (or use p-value)
5. Reject or fail to reject H₀

**Common trap:** "Fail to reject H₀" does not mean H₀ is true. It just means you don't have enough evidence against it.

## Common exam traps

- Always check whether to use **population** (σ known → z-test) or **sample** (σ unknown → t-test)
- **Type I error** = rejecting a true H₀ (false positive). Probability = α.
- **Type II error** = failing to reject a false H₀ (false negative). Probability = β.
- Power of a test = 1 − β. Higher is better.
