
## CATEGORY 1: MODERN PORTFOLIO THEORY & RISK-ADJUSTED PERFORMANCE

### 1. Sharpe Ratio (Ex-Post and Ex-Ante frameworks)

**Ex-Post (Realized):**
$$S_{p, realized} = \frac{\bar{R}_p - \bar{R}_f}{\hat{\sigma}_p}$$

**Ex-Ante (Expected):**
$$S_{p, expected} = \frac{E[R_p] - R_f}{\sigma_p}$$

| Variable | Definition |
| :--- | :--- |
| $\bar{R}_p$ / $E[R_p]$ | Realized sample mean return / Expected forward-looking return of the portfolio. |
| $\bar{R}_f$ / $R_f$ | Realized average risk-free rate / Current risk-free rate. |
| $\hat{\sigma}_p$ / $\sigma_p$ | Sample standard deviation / Expected volatility of excess returns. |

**Institutional Interview Intuition:**
This metric quantifies the excess return generated per unit of total portfolio volatility, establishing the fundamental baseline for risk-adjusted performance. Pitch it to a PM as the quickest heuristic to prove your strategy isn't just taking on naked leverage to juice absolute returns.

### 2. Treynor Ratio (Systematic risk adjustment)

$$T_p = \frac{E[R_p] - R_f}{\beta_p}$$

| Variable | Definition |
| :--- | :--- |
| $E[R_p] - R_f$ | The expected excess return of the portfolio over the risk-free rate. |
| $\beta_p$ | The portfolio's systematic risk (beta) relative to the market benchmark. |

**Institutional Interview Intuition:**
This ratio evaluates excess return scaled by beta, isolating the compensation received strictly for bearing undiversifiable market risk. Present this to an MD to demonstrate that your equity long/short book generates genuine alpha rather than implicitly riding a leveraged market beta.

### 3. Information Ratio (Relationship to Tracking Error and Active Return)

$$IR = \frac{E[R_p - R_b]}{\sqrt{Var(R_p - R_b)}} = \frac{\alpha}{\omega}$$

| Variable | Definition |
| :--- | :--- |
| $E[R_p - R_b]$ | Active return ($\alpha$); the expected return of the portfolio minus the benchmark. |
| $\sqrt{Var(R_p - R_b)}$ | Tracking error ($\omega$); the standard deviation of the active returns. |

**Institutional Interview Intuition:**
This measures the active return of a portfolio divided by its tracking error, effectively scoring the consistency of a manager's alpha generation. Frame it to a PM as the ultimate proof of manager skill, highlighting that your active deviations from the benchmark are reliably profitable.

### 4. Sortino Ratio & Downside Deviation

$$S_R = \frac{E[R_p] - MAR}{\delta}$$

**Continuous Downside Deviation:**
$$\delta = \sqrt{\int_{-\infty}^{MAR} (MAR - R)^2 f(R) dR}$$

| Variable | Definition |
| :--- | :--- |
| $MAR$ | Minimum Acceptable Return (often $0$ or the risk-free rate). |
| $\delta$ | Downside deviation; volatility strictly calculated from returns falling below the $MAR$. |
| $f(R)$ | The probability density function of the return distribution. |

**Institutional Interview Intuition:**
By replacing total volatility with downside deviation, this ratio penalizes only the harmful volatility that falls below a specified Minimum Acceptable Return. Use this in an interview to argue that your asymmetric options strategy shouldn't be penalized for upside convexity.

### 5. Omega Ratio

$$\Omega(MAR) = \frac{\int_{MAR}^{\infty} (1 - F(R)) dR}{\int_{-\infty}^{MAR} F(R) dR}$$

| Variable | Definition |
| :--- | :--- |
| $MAR$ | Minimum Acceptable Return threshold. |
| $F(R)$ | Cumulative distribution function (CDF) of the asset's returns. |
| Numerator/Denominator | Probability-weighted mass of gains vs. probability-weighted mass of losses. |

**Institutional Interview Intuition:**
This probability-weighted ratio compares the entire cumulative distribution of returns above a threshold to those below, capturing all higher moments without assuming normality. Pitch it to a PM running a tail-risk or distress strategy to prove you understand how to underwrite lumpy, non-linear payoff profiles.

### 6. Mean-Variance Optimization Objective Function (Matrix form N-assets)

$$\max_{w} \left( w^T \mu - \frac{\lambda}{2} w^T \Sigma w \right)$$

| Variable | Definition |
| :--- | :--- |
| $w$ | $N \times 1$ column vector of asset weights. |
| $\mu$ | $N \times 1$ column vector of expected asset returns. |
| $\lambda$ | Risk-aversion scalar dictating the trade-off between return and variance. |
| $\Sigma$ | $N \times N$ covariance matrix of asset returns. |

**Institutional Interview Intuition:**
This quadratic programming function seeks to maximize expected portfolio return while penalizing variance through a customized risk-aversion scalar. Explain to an MD that you can dynamically tune this objective to construct the exact efficient frontier suitable for their specific mandate.

### 7. Global Minimum Variance (GMV) Portfolio Weights

$$w_{GMV} = \frac{\Sigma^{-1} \mathbf{1}}{\mathbf{1}^T \Sigma^{-1} \mathbf{1}}$$

| Variable | Definition |
| :--- | :--- |
| $\Sigma^{-1}$ | The inverse of the $N \times N$ covariance matrix. |
| $\mathbf{1}$ | $N \times 1$ column vector of ones. |
| $w_{GMV}$ | $N \times 1$ column vector of optimal weights yielding the lowest possible variance. |

**Institutional Interview Intuition:**
This matrix algebra solution identifies the single portfolio on the efficient frontier with the absolute lowest possible volatility, completely independent of expected returns. Pitch it as the ultimate defensive anchor for an asset allocation model when conviction in forward-looking return forecasts is extremely low.

### 8. Black-Litterman Master Formula

$$E[R] = [(\tau \Sigma)^{-1} + P^T \Omega^{-1} P]^{-1} [(\tau \Sigma)^{-1} \Pi + P^T \Omega^{-1} Q]$$

| Variable | Definition |
| :--- | :--- |
| $E[R]$ | $N \times 1$ vector of newly updated (posterior) expected returns. |
| $\tau$ | Scalar reflecting the uncertainty of the prior (equilibrium) distribution. |
| $\Pi$ | $N \times 1$ vector of implied market equilibrium returns. |
| $P$ | $K \times N$ matrix linking $K$ specific views to the $N$ assets. |
| $\Omega$ | $K \times K$ diagonal matrix of the variance (uncertainty) of the views. |
| $Q$ | $K \times 1$ vector of the expected returns based on the subjective views. |

**Institutional Interview Intuition:**
This Bayesian framework optimally blends implied market equilibrium returns with proprietary absolute or relative subjective views, weighted by investor confidence. Pitch it to a macro PM as the mathematically rigorous way to size trades based on their specific macro convictions without crashing the optimizer.

### 9. Risk Parity Asset Weight Allocation Condition

$$w_i \frac{\partial \sigma_p}{\partial w_i} = \frac{\sigma_p}{N}$$
*or equivalently:*
$$w_i \frac{(\Sigma w)_i}{\sqrt{w^T \Sigma w}} = \frac{\sqrt{w^T \Sigma w}}{N}$$

| Variable | Definition |
| :--- | :--- |
| $w_i$ | Weight of asset $i$. |
| $\partial \sigma_p / \partial w_i$ | Marginal Contribution to Risk (MCR) for asset $i$. |
| $\sigma_p$ | Total portfolio standard deviation. |
| $N$ | Total number of assets (or independent risk factors) in the portfolio. |

**Institutional Interview Intuition:**
This allocation framework mathematically sizes asset weights so that every single component contributes an exactly equal amount of marginal volatility to the aggregate portfolio. Explain to an MD that this solves the illusion of diversification in traditional 60/40 portfolios by balancing true underlying factor risks.

---

## CATEGORY 2: DEEP RISK METRICS & TAIL-RISK ANALYTICS

### 10. Value at Risk (VaR): Parametric, Historical, and Monte Carlo

**Parametric (Variance-Covariance) VaR:**
$$VaR_{\alpha} = - \left( \mu_p + Z_{\alpha} \sigma_p \right)$$
*(Assuming unit portfolio value. Convert to dollar VaR by multiplying by $V_0$.)*

**Historical VaR:**
$$VaR_{\alpha} = - \text{Percentile}(R_{historical}, \alpha)$$

**Monte Carlo VaR:**
$$VaR_{\alpha} = - \text{Percentile}(\hat{R}_{MC}, \alpha)$$

| Variable | Definition |
| :--- | :--- |
| $\alpha$ | The tail probability (e.g., $5\%$ for a $95\%$ confidence level). |
| $Z_{\alpha}$ | The critical Z-score from the standard normal distribution (e.g., $-1.645$). |
| $R_{historical}$ / $\hat{R}_{MC}$ | The vector of actual historical returns / simulated stochastic returns. |

**Institutional Interview Intuition:**
VaR defines the maximum expected loss over a specific horizon at a given confidence interval, serving as the foundational metric for market risk. Pitch it as a standard regulatory and daily reporting baseline that gives trading desks a quick, standardized snapshot of normal market operations.

### 11. Cornish-Fisher VaR Expansion

$$Z_{CF} = Z_{\alpha} + \frac{1}{6}(Z_{\alpha}^2 - 1)S + \frac{1}{24}(Z_{\alpha}^3 - 3Z_{\alpha})K - \frac{1}{36}(2Z_{\alpha}^3 - 5Z_{\alpha})S^2$$

| Variable | Definition |
| :--- | :--- |
| $Z_{CF}$ | The adjusted critical value accounting for non-normality. |
| $Z_{\alpha}$ | The standard normal Z-score. |
| $S$ | Skewness of the empirical return distribution. |
| $K$ | Excess Kurtosis (fat-tailedness) of the empirical return distribution. |

**Institutional Interview Intuition:**
This expansion modifies the standard normal Z-score to explicitly account for negative skewness and excess kurtosis in empirical return distributions. Pitch it in an interview to demonstrate you know how to analytically adjust risk models for real-world fat tails without requiring a full Monte Carlo simulation.

### 12. Expected Shortfall (CVaR)

**Continuous Integral Form:**
$$CVaR_{\alpha} = \frac{1}{1-\alpha} \int_{-\infty}^{-VaR_{\alpha}} x f(x) dx$$

**Discrete Summation Form:**
$$CVaR_{\alpha} = \frac{1}{N(1-\alpha)} \sum_{i=1}^{N(1-\alpha)} L_{(i)}$$

| Variable | Definition |
| :--- | :--- |
| $\alpha$ | The confidence level (e.g., $0.95$). Note: Integrals often use tail probability $(1-\alpha)$. |
| $f(x)$ | The probability density function of portfolio losses. |
| $L_{(i)}$ | The ordered historical or simulated losses, from worst to least worst. |

**Institutional Interview Intuition:**
This metric calculates the probability-weighted average of all losses that exceed the Value at Risk threshold, capturing the true magnitude of tail destruction. Present it to a Chief Risk Officer as a mathematically coherent risk measure that actively penalizes extreme fat tails ignored by standard VaR.

### 13. Tracking Error (Ex-Post and Ex-Ante)

**Ex-Post (Sample Standard Deviation):**
$$TE = \sqrt{\frac{1}{T-1} \sum_{t=1}^T (R_{p,t} - R_{b,t})^2}$$

**Ex-Ante (Active Risk Matrix Form):**
$$TE = \sqrt{w_{active}^T \Sigma w_{active}}$$

| Variable | Definition |
| :--- | :--- |
| $R_{p,t} - R_{b,t}$ | The realized active return of the portfolio over the benchmark at time $t$. |
| $w_{active}$ | $N \times 1$ vector of active weights (Portfolio Weight - Benchmark Weight). |
| $\Sigma$ | $N \times N$ covariance matrix of asset returns. |

**Institutional Interview Intuition:**
This captures the standard deviation of active returns, mathematically defined ex-ante as the volatility of the active weight vector multiplied by the covariance matrix. Pitch this to an index-hugging PM to prove you can surgically manage the exact risk budget allocated for benchmark deviations.

### 14. Marginal Contribution to Risk (MCR)

$$MCR_i = \frac{\partial \sigma_p}{\partial w_i} = \frac{(\Sigma w)_i}{\sigma_p}$$

| Variable | Definition |
| :--- | :--- |
| $\sigma_p$ | Total portfolio standard deviation. |
| $w_i$ | Weight of asset $i$. |
| $(\Sigma w)_i$ | The $i$-th element of the vector resulting from multiplying the covariance matrix by the weight vector. |

**Institutional Interview Intuition:**
This calculus-driven metric isolates the exact change in total portfolio volatility caused by an infinitesimal increase in a single asset's weight. Explain to a PM that this is the scalpel used to identify which specific positions are acting as hidden volatility hogs.

### 15. Incremental VaR (iVaR) and Component VaR (cVaR)

**Incremental VaR:**
$$iVaR_i \approx MCR_i \times \Delta w_i \times Z_{\alpha}$$
*(First-order approximation of VaR change for a small trade $\Delta w_i$)*

**Component VaR:**
$$cVaR_i = w_i \frac{\partial VaR}{\partial w_i} = w_i \times MCR_i \times Z_{\alpha}$$

| Variable | Definition |
| :--- | :--- |
| $MCR_i$ | Marginal Contribution to Risk for asset $i$. |
| $\Delta w_i$ | The proposed change in the weight (or dollar allocation) of asset $i$. |
| $cVaR_i$ | The strictly additive portion of total portfolio VaR attributable to asset $i$ (since $\sum cVaR_i = VaR$). |

**Institutional Interview Intuition:**
Incremental VaR estimates the impact of a new trade on total portfolio VaR, while Component VaR decomposes the current total VaR into additive asset-level attributions. Pitch it to a desk head as the ultimate capital allocation tool to figure out exactly who is consuming the firm's daily risk budget.

### 16. Maximum Drawdown (MDD) and Conditional Drawdown

**Maximum Drawdown:**
$$MDD = \max_{\tau \in (0, T)} \left( \frac{\max_{t \in (0, \tau)} P_t - P_{\tau}}{\max_{t \in (0, \tau)} P_t} \right)$$

**Conditional Drawdown:**
$$CDD_{\alpha} = E[DD | DD > DD_{\alpha}]$$

| Variable | Definition |
| :--- | :--- |
| $P_t$ / $P_{\tau}$ | The portfolio value at time $t$ (historical peak) and $\tau$ (subsequent trough). |
| $DD$ / $DD_{\alpha}$ | The vector of observed drawdowns / the drawdown at the $\alpha$ confidence percentile. |

**Institutional Interview Intuition:**
This represents the maximum peak-to-trough drop in portfolio value over a historical timeline, mapping the absolute worst-case sequence of compounding losses. Highlight this to a PM to show you understand that while volatility is a statistical construct, drawdown is what actually triggers fund liquidations.

---

## CATEGORY 3: FIXED INCOME STRATEGY & CREDIT RISK MATH

### 17. Macaulay Duration and Modified Duration

**Macaulay Duration:**
$$D_{Mac} = \frac{\sum_{t=1}^n \frac{t \cdot CF_t}{(1+y)^t}}{P}$$

**Modified Duration:**
$$D_{Mod} = \frac{D_{Mac}}{1 + \frac{y}{m}}$$

| Variable | Definition |
| :--- | :--- |
| $CF_t$ | The cash flow received at time $t$. |
| $y$ / $m$ | The yield to maturity / compounding periods per year. |
| $P$ | Current dirty price of the bond (sum of discounted cash flows). |

**Institutional Interview Intuition:**
Macaulay calculates the time-weighted center of gravity for a bond's cash flows, while Modified Duration translates this directly into percentage price sensitivity to yield changes. Pitch this to a fixed income desk as the foundational first-order Greek for immunizing parallel shifts in the yield curve.

### 18. Effective Duration and Effective Convexity

**Effective Duration:**
$$ED = \frac{P_{-} - P_{+}}{2 P_0 \Delta y}$$

**Effective Convexity:**
$$EC = \frac{P_{-} + P_{+} - 2P_0}{P_0 (\Delta y)^2}$$

| Variable | Definition |
| :--- | :--- |
| $P_{-}$ / $P_{+}$ | The re-priced bond value if the yield curve shifts down/up by $\Delta y$, factoring in option exercise behavior. |
| $P_0$ | Current initial price of the bond. |
| $\Delta y$ | The absolute shock applied to the benchmark yield curve (e.g., $0.005$ for 50 bps). |

**Institutional Interview Intuition:**
These metrics calculate empirical price sensitivity by actively shifting the yield curve and re-pricing the bond to account for embedded option exercise behavior. Explain to an MBS or callable bond PM that you use these to capture negative convexity when borrowers predictably refinance during rate cuts.

### 19. Taylor Series Expansion for Bond Price Changes

$$\frac{\Delta P}{P} \approx -D_{Mod} \Delta y + \frac{1}{2} C (\Delta y)^2$$

| Variable | Definition |
| :--- | :--- |
| $\Delta P / P$ | The percentage change in the bond's price. |
| $D_{Mod}$ | Modified Duration (first derivative approximation). |
| $C$ | Convexity (second derivative approximation). |
| $\Delta y$ | The parallel shift in the yield to maturity. |

**Institutional Interview Intuition:**
This polynomial expansion combines first-order duration and second-order convexity to generate a highly accurate approximation of bond price shocks under large yield movements. Present this to a rates trader to prove you can accurately model non-linear P&L when the central bank drops a surprise 50 basis point hike.

### 20. Key Rate Duration

$$KRD_i = -\frac{1}{P} \frac{\partial P}{\partial y_i}$$

| Variable | Definition |
| :--- | :--- |
| $KRD_i$ | The Key Rate Duration corresponding to maturity node $i$. |
| $\partial P / \partial y_i$ | The localized change in bond price due to a shock exclusively at maturity node $i$, keeping the rest of the curve constant. |

**Institutional Interview Intuition:**
This vector of partial durations measures a bond portfolio's precise price sensitivity to isolated, specific maturity nodes on the yield curve. Pitch it to a macro rates PM as the essential tool for hedging non-parallel curve twists like steepeners and flatteners.

### 21. Credit VaR (Unexpected Loss Framework)

$$UL_{Credit} = EAD \cdot \sqrt{PD \cdot \sigma_{LGD}^2 + LGD^2 \cdot \sigma_{PD}^2}$$
*(Formula represents single-asset standard structural Unexpected Loss)*

| Variable | Definition |
| :--- | :--- |
| $EAD$ | Exposure at Default (the total at-risk nominal value). |
| $PD$ / $\sigma_{PD}^2$ | Probability of Default / Variance of the default probability driven by credit migration matrices. |
| $LGD$ / $\sigma_{LGD}^2$ | Loss Given Default / Variance of the recovery loss severity. |

**Institutional Interview Intuition:**
This translates standard market VaR into the credit space by modeling default probabilities, loss given default, and downgrade transition matrices. Frame this to a credit risk officer to show you can quantify unexpected tail losses in a loan book caused by systemic rating migrations.

### 22. Merton Model Framework (Distance-to-Default)

**Equity as a Call Option:**
$$E = V_A N(d_1) - D e^{-rT} N(d_2)$$
$$d_1 = \frac{\ln(V_A/D) + (r + \frac{\sigma_A^2}{2})T}{\sigma_A \sqrt{T}}$$

**Distance-to-Default (Risk-Neutral):**
$$DD = d_2 = d_1 - \sigma_A \sqrt{T}$$

| Variable | Definition |
| :--- | :--- |
| $E$ / $V_A$ / $D$ | Value of Equity / Total Asset Value of the Firm / Face value of Zero-Coupon Debt. |
| $\sigma_A$ | The implied volatility of the firm's total assets. |
| $N(\cdot)$ | Cumulative standard normal distribution function. |
| $r$ / $T$ | Risk-free rate / Time to maturity of the debt. |

**Institutional Interview Intuition:**
This structural framework mathematically prices corporate equity as a European call option on the firm's total assets, linking market volatility directly to default probability. Pitch it to a distressed debt PM to show you can cross-pollinate Black-Scholes options math to predict corporate bankruptcies before the ratings agencies do.

"""

with open(filename, "w", encoding="utf-8") as file:
    file.write(markdown_content)

print(f"File '{filename}' generated successfully. Ready for download.")
