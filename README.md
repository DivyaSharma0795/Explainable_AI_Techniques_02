# Model Interpretability using PDP, ICE, and ALE Plots

## Project Overview

This project focuses on **interpreting machine learning models** using three complementary visualization techniques:

* **Partial Dependence Plots (PDP)**
* **Individual Conditional Expectation (ICE) Plots**
* **Accumulated Local Effects (ALE) Plots**

The goal is to understand how individual features influence the model’s predictions, identify key drivers of the target variable, and ensure the model's behavior is both reasonable and trustworthy.

---

## Objective

* Visualize and compare the **global** and **local** effects of features on the target variable.
* Determine which features have the most significant impact on model predictions.
* Improve model transparency to support decision-making and responsible deployment.

---

## Workflow and Explanation

### 1. Feature Importance Analysis

Selected six features based on initial modeling results and domain relevance:

* **Duration**
* **Heart Rate**
* **Age**
* **Height**
* **Gender** (binary encoded)
* **Body Temperature**

### 2. Visualization Techniques

#### a. Partial Dependence Plots (PDP)

* **Purpose:** Show the *average marginal effect* of a feature on the target variable.
* **Why it matters:** PDP provides a simple, global view but can obscure individual-level variations.

#### b. Individual Conditional Expectation (ICE) Plots

* **Purpose:** Show how model predictions change for individual observations as a feature varies.
* **Why it matters:** ICE plots reveal *individual-level heterogeneity* and interactions that PDP might miss.

#### c. Accumulated Local Effects (ALE) Plots

* **Purpose:** Show *local feature effects* while addressing issues of feature correlation and extrapolation.
* **Why it matters:** ALE plots provide more reliable interpretations for complex, real-world datasets.

---

### 3. Key Findings

#### Primary Influencers:

* **Duration:**

  * Strongest impact across all plots.
  * PDP shows a clear positive trend.
  * ICE confirms consistent upward trends with slight individual variation.
  * ALE shows a significant positive increase (+80 units across the feature range).

* **Heart Rate:**

  * Moderate influence.
  * PDP shows a gradual increase from 65 to 110 BPM.
  * ICE reveals individual differences in sensitivity.
  * ALE suggests the effect strengthens at higher heart rates.

#### Secondary Influencer:

* **Age:**

  * Modest positive effect.
  * ICE plots show varied individual responses, highlighting diverse patterns.
  * ALE confirms a positive but smaller overall contribution (+25 units).

#### Minimal Impact Features:

* **Height:**

  * Appears nearly flat in PDP.
  * ICE shows scattered, individual-specific effects.
  * ALE indicates a complex but ultimately low-impact, non-linear relationship.

* **Gender:**

  * Minimal effect across all plots.

* **Body Temperature:**

  * Negligible influence confirmed by all three plots.

---

### 4. Interpretation Summary

* **PDP:** Provides a global, averaged understanding of feature effects.
* **ICE:** Reveals variability at the individual observation level.
* **ALE:** Offers a more accurate, localized interpretation that accounts for feature interactions.

Together, these tools:

* Validate that **Duration** and **Heart Rate** are the primary drivers of the target.
* Confirm that **demographic and physical features like Gender, Height, and Body Temperature have limited influence.**
* Help detect potential model biases and ensure the model’s decision logic aligns with domain expectations.

---

## Key Takeaways

* **Duration** and **Heart Rate** are the most impactful features.
* ALE plots are particularly valuable when features are correlated or when a localized understanding is needed.
* Using all three plot types provides a comprehensive view of model behavior—global trends, individual-level effects, and localized sensitivities.

---

## Future Directions

* Investigate additional features and potential feature interactions.
* Extend analysis to multiple models to compare interpretability across different algorithms.
* Explore SHAP values as another method for feature attribution.

---

## Contact

For any questions or further collaboration, please reach out to **Divya Sharma** via LinkedIn or email.
