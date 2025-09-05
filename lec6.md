# 📊 Data Science — Lecture 6 Summary

### 1. Recap

* z-tests (means & proportions, known variance).
* t-tests (unknown variance).
* χ²-tests.
* Correlation tests.
* F-tests.

---

### 2. t-test for Two Population Means (Independent Samples)

* Compares whether two population means are significantly different.
* Variance unknown but assumed equal.
* Degrees of freedom = n1 + n2 − 2.

**Example:** Body fat % in men vs women.

* H0: μ₁ = μ₂ (no difference).
* H1: μ₁ ≠ μ₂ (significant difference).
* Compute means & pooled variance → calculate t → compare with critical value.

👉 Used to compare **two independent groups** (e.g., trial vs control).

---

### 3. F-test for Two Population Variances

* Tests if two populations have the same variance.
* H0: σ₁² = σ₂².
* H1: σ₁² ≠ σ₂².
* Test statistic follows **F-distribution** with df = (n1−1, n2−1).

📈 F-distribution: always positive, skewed right.

👉 Often used before ANOVA or pooled t-tests.

---

### 4. χ²-test for Goodness of Fit

* Checks if observed frequencies match expected frequencies.
* H0: observed = expected.
* H1: not equal.
* Valid when expected counts > 5.
* df = K − 1 (or K − 1 − m if parameters estimated).

**Examples:**

1. 10% of people are left-handed.

   * Sample: 140 students, 21 left-handed.
   * Expected = 14 → χ² test checks if difference significant.

2. Circuit board defects → check if counts follow Poisson distribution.

👉 Used to check if real-world data follows **theoretical distribution**.

---

### 5. χ²-test for Independence

* Tests whether **two categorical variables** are independent.
* H0: Independent.
* H1: Dependent.

**Example:** Social media preference vs gender (n=120).

| Platform  | Male | Female | Total |
| --------- | ---- | ------ | ----- |
| TikTok    | 15   | 20     | 35    |
| Instagram | 30   | 35     | 65    |
| Facebook  | 5    | 15     | 20    |
| **Total** | 50   | 70     | 120   |

Expected (TikTok & Male) = (50/120 × 35) = 14.6.

χ² = 2.84, df = 2 → **Do not reject H0**.

👉 Conclusion: Social media preference is **independent of gender**.

---

## ✅ Key Takeaways

* **t-test (two means):** Compare averages of two groups.
* **F-test (two variances):** Compare variability of two groups.
* **χ² Goodness of Fit:** Compare observed vs expected distribution.
* **χ² Independence:** Test relationship between categorical variables.

👉 Lecture 6 extends hypothesis testing to **group comparisons & categorical data analysis**.
