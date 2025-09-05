# 📊 Data Science — Lecture 3 Summary

### 1. Recap
- **Attribute Types:** Nominal, Ordinal, Discrete, Continuous.  
- **Statistical Measures:** Mean, Median, Mode, Variance, Standard Deviation.  
- **Shape of Data:** Skewness & Correlation.  
- **Data Cleaning:** Handling outliers, missing values, noise.  

---

### 2. Probability Basics

**Probability Space (Ω, F, P):**  
- **Ω (Sample Space):** all outcomes of an experiment.  
  - Example: Toss coin → Ω = {H, T}.  
- **F (Event Space):** collection of events (subsets of Ω) that satisfy σ-algebra rules:  
  - Contains Ω.  
  - Closed under complement (if A in F, then not-A also in F).  
  - Closed under countable unions.  
- **P (Probability Measure):** assigns probabilities between 0 and 1.  
  - P(Ω) = 1.  
  - Additivity: disjoint events’ probabilities add.  

👉 Example: Toss 2 coins  
- Ω = {HH, HT, TH, TT}  
- Event: “at least one head” = {HH, HT, TH} → P = 3/4  

---

### 3. Conditional Probability
- **Definition:** P(A|B) = P(A ∩ B) / P(B), if P(B) > 0.  

**Examples:**  
1. Toss 2 coins:  
   - A = First toss is Head.  
   - B = At least one Head.  
   - P(A|B) = 2/3.  

2. Toss 2 coins:  
   - A = At least one Head.  
   - B = First toss is Head.  
   - P(A|B) = 1.  

---

### 4. Law of Total Probability & Bayes’ Rule
- **Law of Total Probability:**  
  If sample space divided into disjoint events A1, A2, …, An:  
  P(B) = Σ P(B|Ai) P(Ai).  

- **Bayes’ Rule:**  
  P(A|B) = [P(B|A) P(A)] / P(B).  

👉 Example: Medical Testing — Bayes’ rule helps find probability of having disease given a positive test.  

---

### 5. Random Variables (RVs)
- Function assigning numbers to outcomes.  
- **Discrete RVs:** finite/countable (coin toss, dice roll).  
- **Continuous RVs:** infinite real values (height, weight).  

**Example:** Toss coin → X = number of heads  
- Ω = {H, T}, X(H)=1, X(T)=0.  

---

### 6. Expectation & Variance
- **Expectation:** E[X] = Σ x · P(x).  
  - Example: Toss coin → E[X] = 0.5.  
- **Variance:** Var(X) = E[(X − E[X])²].  
- **Properties:**  
  - E[cX] = c·E[X]  
  - Var(cX) = c²·Var(X)  
  - Var(X+Y) = Var(X) + Var(Y) + 2Cov(X,Y)  

---

### 7. Linearity of Expectation
- Always holds, independent of variable independence.  
- E[X+Y] = E[X] + E[Y].  

**Example:** Toss 3 coins → expected heads = 1.5.  

---

### 8. Special Random Variables

**1. Bernoulli RV:**  
- One trial, success (1) with prob p, failure (0) with prob 1−p.  
- E[X] = p, Var(X) = p(1−p).  

**2. Binomial RV:**  
- n independent Bernoulli trials, success probability p.  
- X ~ B(n, p).  
- E[X] = np, Var[X] = np(1−p).  
- Example: Toss coin 10 times → expected heads = 5.  

**3. Geometric RV:**  
- Number of trials until first success.  
- E[X] = 1/p.  
- Example: Roll die until 6 appears → expected rolls = 6.  

---

## ✅ Key Takeaway
Lecture 3 builds the **mathematical foundation for probability**:  
- Probability spaces, events, and probability measures.  
- Conditional probability, law of total probability, Bayes’ theorem.  
- Random variables with expectation & variance.  
- Linearity of expectation and covariance.  
- Key distributions: Bernoulli, Binomial, Geometric.  

👉 These concepts form the **basis for statistical inference and machine learning models**.
