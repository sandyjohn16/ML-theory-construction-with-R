# ML-theory-construction-with-R
# Machine Learning-Informed Theory Construction: An Inductive-to-Deductive Workflow

This repository contains a functional implementation of an **inductive-to-deductive scientific pipeline** written in R. It demonstrates how regularized machine learning can be used as an inductive engine to isolate structural predictive anchors, formalize them into a causal directed acyclic graph (DAG), and deductively validate them using confirmatory statistical models.

The workflow is evaluated using the UCI Student Performance dataset.

---

## 🛠️ Pipeline Architecture

1. **Inductive Feature Screening:** A Random Forest regressor filters through 30+ multi-dimensional behavioral and demographic variables to determine key non-linear anchors for final student grades ($G3$).
2. **Structural Formalization:** Variables displaying significant incremental Mean Squared Error (%IncMSE) are extracted and mapped into a formal causal network graph using `dagitty`.
3. **Deductive Confirmatory Testing:** The structurally implied paths of the customized theory are formally evaluated using an Ordinary Least Squares (OLS) linear regression model.

---

## 📈 Key Empirical Metrics

* **Random Forest Baseline:** The machine learning model successfully explained **29.56%** of the variance in final student grades, establishing a highly realistic predictive baseline for behavioral datasets.
* **The Dominant Structural Anchor:** Academic `failures` emerged as the most resilient predictor across both frameworks, mapping to a top position in the Random Forest (%IncMSE = 27.72) and a devastatingly significant coefficient in the linear test ($p < 0.001$), estimating a **1.81 point drop** in final grade per past failure.

---

## 🔬 Methodological Discovery: The "Absences Paradox"

The core takeaway of this pipeline highlights the structural limitations of traditional social science workflows:
* **The Paradox:** In the Random Forest model, `absences` emerged as the **second most critical predictor** globally (`%IncMSE = 25.54`). However, when built into the causal graph and run through a traditional linear regression framework (`lm`), the statistical effect of absences completely evaporated ($p = 0.297$).
* **Methodological Conclusion:** This divergence reveals that traditional linear validations completely mask non-linear threshold mechanics (e.g., small absences are minor, but large absences trigger failure cascades) or complex interaction loops. This beautifully validates the core objective of the INSIGHT Lab: we cannot rely on flat linear constraints to test complex human behavior.

---

## 🚀 Environment and Dependencies
* **Language:** R v4.6.0
* **Core Libraries:** `tidyverse` (data wrangling), `randomForest` (machine learning), `dagitty` (causal structures), `rpart` & `rpart.plot` (decision tree structures).
