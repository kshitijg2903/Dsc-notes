# 📊 Data Science — Lecture 7 Summary

### 1. Recap

* χ²-test (goodness of fit, independence).
* Degrees of freedom explanation.
* Errors in hypothesis testing (Type I & II).

---

### 2. Parameter Estimation

Two approaches to estimate unknown parameters (like probability **p** or mean **μ**):

1. **Maximum Likelihood Estimation (MLE):** purely data-driven.
2. **Maximum a Posteriori (MAP):** combines data with prior beliefs.

---

### 3. Maximum Likelihood Estimation (MLE)

* Have random samples X₁, X₂, …, Xn from a distribution with parameter θ.
* Find θ that maximizes the likelihood of observing the data.

**Examples:**

1. **Biased coin (Binomial):** Toss 10 times, observe 4 heads.

   * Candidate probabilities p = {⅓, ½, ⅔}.
   * Compute P(4 heads):

     * p=⅓ → 0.228
     * p=½ → 0.205
     * p=⅔ → 0.057
   * MLE = ⅓ (most likely).

2. **Bernoulli (single trial):** MLE of p = fraction of successes in sample.

3. **Binomial (n trials):** MLE of p = total successes ÷ (n × experiments).

4. **Geometric (trials until success):** MLE of p = 1 ÷ (average number of trials).

**Properties of MLE:**

* Easy to compute.
* Consistent (n → ∞ → estimate → true θ).
* Can overfit.
* Not always unique.

---

### 4. Bayes’ Rule Refresher

* **Prior:** P(H) = belief before seeing data.
* **Likelihood:** P(E|H) = probability of evidence given H.
* **Posterior:** P(H|E) = \[P(E|H) P(H)] / P(E).

**Example: Disease Test**

* Prior: 0.1% chance of disease.
* Test accuracy: 99%. False positive: 1%.
* Posterior after positive test ≈ 9%.
* If prior updated to 9% and test repeated → posterior ≈ 90%.

👉 Shows how evidence accumulates using Bayes’ rule.

---

### 5. Monty Hall Problem (Bayes Application)

* 3 doors: 1 car, 2 goats.

1. You pick a door.
2. Monty opens another door (goat).
3. You can switch or stay.

* If stay → win chance = 1/3.
* If switch → win chance = 2/3.

👉 Switching **doubles chance of winning**.

---

### 6. Maximum a Posteriori (MAP)

* Similar to MLE but includes **prior belief** about θ.
* Formula: θMAP = argmax P(θ|Data) ∝ P(Data|θ) × P(θ).

**Properties:**

* Avoids overfitting (prior acts as regularizer).
* As n → ∞, MAP → MLE (data dominates).

**Analogy:**

* MLE = "believe only data."
* MAP = "believe data + prior experience."

---

## ✅ Key Takeaways

* **MLE:** estimates parameters by maximizing likelihood.
* **Bayes’ Rule:** updates beliefs using evidence.
* **Monty Hall Problem:** example of conditional probability.
* **MAP:** combines MLE with prior → more robust.

👉 Lecture 7 introduces **parameter estimation**: how to move from hypothesis testing to actually estimating the values behind the data.
