# 📊 Data Science — Lecture 4 Summary

### 1. Recap

* Probability space, Law of Total Probability.
* Random variables, Linearity of expectation & variance.
* Distributions: Bernoulli, Binomial, Geometric.

---

### 2. Binomial & Geometric Recap

* **Binomial B(n,p):** Number of successes in n trials.

  * Example: Toss 10 coins → distribution of #heads.

* **Geometric Geo(p):** Number of trials until first success.

  * Example: Roll dice until you get a 6 → expected rolls = 6.

---

### 3. Coupon Collector Problem

* Bag with **k types of coupons**.
* Question: How many coupons until we see *all types*?
* Each “time to new coupon” follows a **geometric distribution**.
* Expectation: E\[Xi] = 1/pi.

💡 **Analogy:** Collecting Pokémon cards → first few new ones appear fast, but the last few take forever.

---

### 4. Central Limit Theorem (CLT)

* **Statement:** Sums/averages of large samples → approximate **normal distribution**.

**Example:**

* Toss 1 die: uniform distribution.
* Toss 50 dice & take average → histogram looks Gaussian.

```
Uniform (Die)       →       Approx. Normal (50 dice sum)
 ┌─┬─┬─┬─┬─┬─┐              bell-shaped curve
 █ █ █ █ █ █                ▂▃▅▇▇▆▄▂
```

👉 CLT explains why the **normal distribution appears everywhere** in real-world data.

---

### 5. Hypothesis Testing

Framework for **testing claims** using data.

* **H0 (Null):** Status quo (default claim).
* **H1 (Alternate):** Research claim.
* **p-value:** Probability of observing result if H0 is true.
* **Decision:** Reject H0 if p-value < α (significance level, e.g., 0.05).

---

### 6. Example: Card Guessing

Friend claims she can guess suits better than random (p > 0.25).

* **Case 1:** 200 trials, ≥53 correct → p-value ≈ 0.337 → not convincing.
* **Case 2:** 100 trials, ≥28 correct → p-value ≈ 0.278 → still not convincing.
* **Case 3:** 100 trials, ≥43 correct → p-value ≈ 0.00003 → very strong evidence → reject H0.

👉 Shows how hypothesis testing quantifies belief in claims.

---

### 7. Errors in Hypothesis Testing

* **Type I Error (False Positive):** Reject H0 when true.

  * Example: Convicting an innocent person.
* **Type II Error (False Negative):** Fail to reject H0 when false.

  * Example: Letting a guilty person go free.

```
Decision Table
--------------------------------
 Actual Truth |   Decision
--------------------------------
 H0 True      |  Reject → Type I Error
 H0 True      |  Not Reject → ✅ Correct
 H0 False     |  Reject → ✅ Correct
 H0 False     |  Not Reject → Type II Error
```

---

### 8. Confidence Intervals

* **Empirical Mean:** From sample (e.g., 0.31).
* **Confidence Interval (95%):** Range that likely contains true mean.
* Formula: mean ± Z \* standard error.
* Example: 0.31 ± 0.02 → (0.29, 0.33).

👉 More samples → smaller error → tighter confidence interval.

---

### 9. z-test for Population Mean

Used to check if sample mean differs significantly from population mean.

* Works when:

  * σ (population std. deviation) known.
  * Large n (≥30).

**Formula:**
Z = (x̄ − μ0) / (σ / √n)

**Example:**

* μ0 = 4.0, σ² = 1, n = 9, x̄ = 4.6.
* Z = 1.8.
* Compare with critical value at α = 0.05 → reject or not reject H0.

---

### 10. Applications

* **Medicine:** Does a vaccine reduce illness?
* **Industry:** Do ≥90% of chips work?
* **Health:** Do masks improve lung function?

---

## ✅ Key Takeaway

Lecture 4 introduces **decision-making under uncertainty**:

* Coupon Collector problem shows random collection expectations.
* Central Limit Theorem explains universality of normal distribution.
* Hypothesis testing provides a structured way to test claims.
* z-test is a practical tool when variance is known and n is large.

👉 This is the **foundation of statistical inference**.
