# Probability & Statistics

Probability is the mathematical language of uncertainty. In finance, almost everything is uncertain — asset returns, default rates, volatility. Understanding probability is non-negotiable.

## Sample space and events

A **sample space** Ω is the set of all possible outcomes. An **event** is a subset of Ω.

Example: If you flip a coin, Ω = {H, T}. The event "heads" = {H}.

## Probability axioms (Kolmogorov)

1. P(A) ≥ 0 for any event A
2. P(Ω) = 1
3. For mutually exclusive events: P(A ∪ B) = P(A) + P(B)

## Key distributions

### Normal distribution N(μ, σ²)

The most important distribution in finance. The bell curve.

- Mean = μ, Variance = σ²
- 68% of data within 1σ, 95% within 2σ, 99.7% within 3σ
- Used for: log-returns, factor models, hypothesis testing

**PDF:**
$$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$

### Lognormal distribution

If X ~ N(μ, σ²), then e^X is lognormal. Asset **prices** (not returns) are often modelled as lognormal because prices cannot go negative.

### Poisson distribution

Models the number of events in a fixed time period. Used in credit risk (default counting) and jump processes.

$$P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}$$

## Expectation and variance

**Expectation** (mean):
$$E[X] = \sum_i x_i P(X = x_i)$$

**Variance:**
$$Var(X) = E[(X - \mu)^2] = E[X^2] - (E[X])^2$$

**Standard deviation:** σ = √Var(X)

## Covariance and correlation

**Covariance** measures how two variables move together:
$$Cov(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]$$

**Correlation** scales it to [-1, +1]:
$$\rho_{XY} = \frac{Cov(X,Y)}{\sigma_X \sigma_Y}$$

In finance: correlation between asset returns is central to portfolio construction. The benefit of diversification comes from combining assets with low or negative correlation.

## Central Limit Theorem (CLT)

> If you take the average of n independent, identically distributed random variables with mean μ and variance σ², the distribution of the average approaches N(μ, σ²/n) as n → ∞.

**Why it matters:** Even if individual asset returns are not normally distributed, the average return of a large portfolio tends toward normality. This underpins much of statistical inference in finance.

## Skewness and kurtosis

Real financial returns are **not** perfectly normal:

| Property | Normal | Real returns |
|---|---|---|
| Skewness | 0 (symmetric) | Negative (left tail) |
| Kurtosis | 3 | > 3 (fat tails) |

**Fat tails** mean extreme events (crashes, spikes) happen more often than a normal distribution predicts. This is why models like VaR based purely on normality underestimate risk.
