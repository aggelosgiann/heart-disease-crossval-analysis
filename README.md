# Heart Disease Prediction: A Recall-Optimized Approach

This repository contains a reproductive analysis and methodological suggestion based on the primary research paper **"Comparative analysis of heart disease prediction using logistic regression, SVM, KNN, and random forest with cross-validation for improved accuracy"** (2025).

While the original paper prioritizes overall accuracy, the notebook included here (`Suggestions.ipynb`) introduces a **clinically-focused methodology** that prioritizes **Recall** (Sensitivity). In medical diagnostics, minimizing false negatives is often more critical than maximizing raw accuracy, ensuring that potential positive cases are not missed.

## Reference Paper

This work is based on the following publication:

* **Title:** [Comparative analysis of heart disease prediction using logistic regression, SVM, KNN, and random forest with cross-validation for improved accuracy](https://www.nature.com/scientificreports/)
* **Authors:** Yagyanath Rimal, Navneet Sharma, Siddhartha Paudel, Abeer Alsadoon, Madhav Parsad Koirala & Sumeet Gill
* **Journal:** *Scientific Reports* (2025) 15:13444
* **DOI:** [10.1038/s41598-025-93675-1](https://doi.org/10.1038/s41598-025-93675-1)

### Original Code Repository
The code associated with the original paper can be found here:
* [https://github.com/yagyarimal/Heart22](https://github.com/yagyarimal/Heart22)

---

##Methodology & Suggestions

In `Suggestions.ipynb`, I have re-evaluated the dataset using a different strategic approach compared to the original study.

### 1. The Critique: Accuracy vs. Clinical Safety
The original paper concludes that **Random Forest** is the superior model based on macro accuracy (94%) and precision. However, this repository proposes that for heart disease prediction, **Recall** is the safety-critical metric.

### 2. The New Approach: Recall-Constrained Optimization
Instead of selecting the model solely based on the highest accuracy, `Suggestions.ipynb` implements a two-stage selection process:

1.  **Recall Constraint:** A strict filter is applied where models must achieve a **minimum average recall of ≥ 90%** across 5-fold cross-validation.
2.  **Accuracy Optimization:** Among the models that pass the safety constraint, the one with the highest accuracy is selected.

### 3. Key Findings & Corrections
* **Random Forest:** While favored in the original paper for its high accuracy, it failed to meet the ≥ 90% recall safety threshold in this specific validation setup and was excluded.
* **Selected Model:** **K-Nearest Neighbors (KNN)** was identified as the optimal model for this specific clinical context. It successfully met the recall constraint while maintaining a high average accuracy of **84.29%**.
* **Other Candidates:** Logistic Regression also met the safety criteria (80.96% accuracy), whereas the Support Vector Classifier (SVC) achieved 80.12%.

---

## How to Run

This notebook is designed to be standalone and hassle-free.

1.  **Download:** Simply download the `Suggestions.ipynb` file from this repository.
2.  **Run:** Open the file in Jupyter Notebook, JupyterLab, or Google Colab and run all cells.
**Requirements:**
* **No special setup required:** The code is self-contained. You do not need to set specific file paths or manually download the dataset; the notebook handles data fetching automatically.
* **Libraries:** Standard Python data science libraries are used (`pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`).
