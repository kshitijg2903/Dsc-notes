# 📊 Data Science — Lecture 2 Summary

### 1. Overview
This lecture covers:
- Attribute types  
- Statistical measures (central tendency, dispersion, skewness, correlation)  
- Plots & data visualization  
- Basics of probability theory  

---

### 2. Data & Attributes
- **Dataset** = collection of entities (rows).  
- Each entity has **attributes** (columns/features).  

#### Types of Attributes:
- **Nominal:** Categories, no order (e.g., Male/Female, Colors).  
- **Ordinal:** Ordered categories (e.g., Rank 1st, 2nd, 3rd).  
- **Discrete:** Countable numbers (e.g., 0, 1, 2, 3).  
- **Continuous:** Real values (e.g., 3.14, -1.5).  

👉 **Encodings for models (since models prefer numbers):**  
- Ordinal → assign integers  
- Nominal → embeddings / one-hot encoding  
- Discrete → often one-hot encoding  

---

### 3. Statistics in Daily Life
- **Max/Min:** highest marks, lowest unemployment.  
- **Averages:** mean height, average income.  
- **Variance:** stock market fluctuations.  
- **Correlation:** if it rains → traffic increases.  
- **Probability:** chance of rain tomorrow.  
- **Hypothesis testing:** do Indians spend more on lunch or dinner?  

---

### 4. Measures of Central Tendency
1. **Mean (average):**  
   - Add values ÷ number of values.  
   - Sensitive to outliers.  
   - Fix: **Truncated mean** (remove extreme high/low values).  
   - Example: [100, 200, 300, 1,000,000] → mean ~ 250k (misleading).  

2. **Median (middle value):**  
   - Sort and take middle.  
   - Robust to outliers.  
   - Example: [100, 200, 300, 1,000,000] → median = 250 (more realistic).  

3. **Mode (most frequent value):**  
   - Useful for nominal/ordinal/discrete data.  
   - Example: most common blood group in a hospital survey.  

---

### 5. Measures of Dispersion (Spread)
- **Range:** max − min.  
- **Variance:** average squared deviation from mean.  
- **Standard Deviation:** square root of variance.  
- **Mean Absolute Deviation (MAD):** average of absolute deviations.  

👉 Spread tells us if data is tightly packed or very spread out.  

---

### 6. Skewness (Symmetry of Data)
- **Symmetric:** balanced (e.g., heights of adults).  
- **Positive skew (right skew):** long tail on right (e.g., salaries, few very high earners).  
- **Negative skew (left skew):** long tail on left (e.g., retirement ages).  

💡 Rule of thumb:  
- Mean > Median → Right skew.  
- Mean < Median → Left skew.  

---

### 7. Correlation
- Checks if two variables move together.  
  - Positive: height & weight.  
  - Negative: exercise & blood sugar.  
- **Important:** correlation ≠ causation.  
  - Example: ice cream sales & drowning → correlated (both increase in summer) but not causal.  

---

### 8. Range & Quantiles
- **Range = max − min**  
- **Quartiles (Q1, Q2, Q3):**  
  - Q1 = 25% point  
  - Q2 = median (50%)  
  - Q3 = 75% point  
- **IQR (Interquartile Range) = Q3 − Q1**  
- **Boxplot** shows min, Q1, median, Q3, max, and outliers.  

Example:  
Sorted scores = `20, 25, 30, 35, 45, 60, 65, 70, 75, 80, 85, 90`  
- Min = 20, Max = 90  
- Q1 ≈ 32.5, Q2 = 62.5, Q3 ≈ 77.5  
- Range = 70, IQR = 45  

---

### 9. Moments (Shape of Distribution)
- **1st Moment (Mean):** average.  
- **2nd Moment (Variance):** spread.  
- **3rd Moment (Skewness):** symmetry.  
- **4th Moment (Kurtosis):** “peakedness/flatness.”  

Kurtosis types:  
- **Leptokurtic (>3):** sharp peak, heavy tails.  
- **Mesokurtic (=3):** normal distribution (bell curve).  
- **Platykurtic (<3):** flat distribution, light tails.  

---

### 10. Plots & Visualization
- **Quantile Plot:** compare data distributions.  
- **Q-Q Plot:** compare two distributions.  
- **Scatter Plot:** correlation, clusters, outliers.  
- **Bar Chart & Pie Chart:** categorical data.  
- **Histogram:** numeric distribution.  

---

### 11. Handling Data Issues
- **Outliers:**  
  - Visualize (boxplot, scatterplot, histograms).  
  - Use PCA, normalization.  
  - Apply domain knowledge.  
- **Missing Values:**  
  - Delete if few.  
  - Impute with mean/median, kNN, regression.  
- **Noise:**  
  - Smooth using binning or regression.  
  - Dimension reduction to highlight signal.  

---

## ✅ Key Takeaway
Lecture 2 teaches how to **describe and summarize data**:  
- Attribute types (nominal, ordinal, discrete, continuous)  
- Central tendency (mean, median, mode)  
- Spread & shape (variance, skewness, kurtosis, range, IQR)  
- Visualization (plots, boxplots, histograms)  
- Handling messy data (outliers, missing values, noise)  

👉 In short: These are the **foundations of exploratory data analysis (EDA)**.
