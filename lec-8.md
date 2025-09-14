# 📊 Data Science — Lecture 8 Summary

### 1. Recap

* Parameter estimation (MLE & MAP).
* Example: biased coin probability.
* Bayes’ rule applications.

---

### 2. Concentration Inequalities

Tools to bound probability of rare events (large deviations from expectation).

#### 🔹 Markov’s Inequality

* For non-negative random variable X:
  **P(X ≥ a) ≤ E\[X] / a**

**Example:** Toss biased coin (p=0.2) 100 times → E\[X]=20.

* Probability of ≥50 heads: 20/50 = 0.4.
* So with probability ≥0.6, heads ≤50.

👉 Simple but often too loose.

---

#### 🔹 Chebyshev’s Inequality

* Uses variance:
  **P(|X−μ| ≥ k) ≤ Var(X) / k²**

**Example:** Same coin (p=0.2, n=100).

* μ = 20, Var = 16.
* Deviation ≥30 → Bound = 16/900 ≈ 0.017.
* So with probability ≥98.3%, heads ≤50.

👉 Much tighter than Markov.

---

#### 🔹 Chernoff Bounds

* Even stronger, especially for sums of independent RVs.
* Gives exponentially decreasing tails.
* Widely used in CS (randomized algorithms, network reliability).

---

### 3. Applications

#### 1. Captcha Database Verification

* Claim: 1M unique captchas.
* If you test m captchas, expected duplicates ≈ m² / (2n).
* Example: m=1000 → check duplicates to verify claim.

👉 Based on **Birthday paradox** idea.

#### 2. Die Rolls Coverage

* For k-sided die, expected rolls to see all faces ≈ k ln(k).
* By Markov: with probability ≥2/3, all faces appear in ≤3k ln(k) rolls.

#### 3. Job Interviews (Markov weakness)

* Friend says: 20% chance per company × 4 companies → claims 80% chance of ≥1 offer.
* True probability = 1 − (0.8⁴) = 0.5904 (≈59%).
* Shows Markov bound can be misleadingly weak.

---

### 4. Moments Refresher

* **1st moment:** Mean = E\[X].
* **2nd moment:** Variance = E\[X²] − (E\[X])².
* **Variance of sum:** Var(X+Y) = Var(X)+Var(Y)+2Cov(X,Y).
* If independent → Var(X+Y) = Var(X)+Var(Y).

---

## ✅ Key Takeaways

* **Markov inequality:** simple bound using mean.
* **Chebyshev inequality:** variance-based, tighter.
* **Chernoff bounds:** exponential decay, strongest.
* Applications: captcha verification, die rolls, interview/job probabilities.

👉 Concentration inequalities are essential in **probability, ML theory, and randomized algorithms**.
