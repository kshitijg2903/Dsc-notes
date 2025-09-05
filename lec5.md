# 📊 Data Science — Lecture 5 Summary

### 1. Recap

* Coupon Collector Problem.
* Central Limit Theorem.
* Statistical Inference basics.
* Hypothesis testing (Null vs Alternate).
* z-test for population mean.

---

### 2. z-test for a Proportion (Binomial Approximation)

* Used when **n > 30** (large sample).
* Tests if sample proportion **p** differs from population proportion **p₀**.
* Based on normal approximation of binomial distribution.

**Examples:**

1. Friend claims >0.25 chance of guessing suit correctly.

   * H0: p ≤ 0.25 (random).
   * H1: p > 0.25 (better than random).
   * If 35/100 correct → compute z, check with α=0.05.

2. Belief: ≥65% wear glasses. Sample: 55/100.

   * H0: p ≥ 0.65.
   * H1: p < 0.65.
   * Test whether evidence rejects belief.

---

### 3. t-test for Population Mean

* Used when **population variance unknown**.
* Can be applied to small samples.
* Degrees of freedom = n − 1.

**Example:**

* μ₀ = 4.0, n = 9, x̄ = 4.9, s² = 1.0.
* t = 2.7, df = 8 → reject H0 at α=0.05.

👉 Think of t-test as a **flexible z-test** when σ² not known.

---

### 4. χ²-test for Population Variance

* Tests if sample variance differs from population variance.
* Statistic follows χ² distribution with df = n−1.

**Example:**

* Last month: train delays σ = 2 hrs.
* This month: n = 17, observed s² = 7.
* χ² = 28, df = 16 → do not reject H0 → reliability same.

📈 Shape of χ² distribution: skewed right, more symmetric as df ↑.

---

### 5. z-test for Two Population Means

* Compares means of two populations (σ known).
* Useful if populations are normal & n large.

**Example:** Vaccine trial

* Group 1 (n1=900): mean = 9.78, σ1 = 4.05.
* Group 2 (n2=1000): mean = 15.1, σ2 = 4.28.
* z-test checks if difference significant.

---

### 6. z-test for Two Proportions

* Compares proportions in two populations.
* Assumes large n, normal approximation.
* H0: p1 = p2, H1: p1 ≠ p2.

---

### 7. t-test for Two Population Means

1. **Independent samples:** Compare two groups when σ unknown.

   * df = n1 + n2 − 2.
2. **Paired samples:** Compare before/after on same group.

   * df = n − 1.

**Example:** Test lung function before vs after masks → paired t-test.

---

### 8. t-test for Correlation Coefficient

* Tests if correlation coefficient r = 0 (no linear relation).
* df = n − 2.
* Limitation: only detects **linear dependence**.

---

### 9. F-test for Two Population Variances

* Compares variances of two populations.
* H0: σ1² = σ2², H1: σ1² ≠ σ2².
* Statistic follows F-distribution with df = (n1−1, n2−1).

📈 Shape of F-distribution: always positive, skewed right.

---

## ✅ Key Takeaway

Lecture 5 extends hypothesis testing into **different tests for means, proportions, correlations, and variances**:

* **z-test:** known variance, large sample.
* **t-test:** unknown variance, small sample.
* **χ²-test:** test for variance itself.
* **F-test:** compare variances of two populations.

👉 Together, these tests form the **toolbox of classical hypothesis testing**.
