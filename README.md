# Canonical Correlation Analysis: Overthinking & Decision-Making Quality

> **Multivariate Statistical Analysis | Canonical Correlation Analysis (CCA) | R**

This project investigates the relationship between **dimensions of overthinking** and **decision-making quality** using **Canonical Correlation Analysis (CCA)**.

The analysis focuses on identifying relationships between two multivariate variable sets:

* **Overthinking (X):** Rumination, Control, Indecisiveness, Negative Thinking, and Regret
* **Decision-Making Quality (Y):** Speed, Confidence, Consistency, Evaluation, and Satisfaction

A major focus of this project is examining how **data normality and different normality-handling approaches affect the results of CCA**.

---

## Research Objective

The main objectives of this project are to:

1. Examine the validity and reliability of the measurement dimensions.
2. Identify dimensions that satisfy the required measurement criteria.
3. Evaluate the assumptions required for Canonical Correlation Analysis.
4. Investigate the impact of non-normality on CCA results.
5. Compare CCA results under different data transformations.
6. Compare conventional CCA with Kernel CCA as a distribution-free alternative.
7. Identify the strongest canonical relationship between overthinking and decision-making quality.
8. Interpret the dominant dimensions contributing to the canonical relationships.

---

## Methodology

The analysis follows a structured multivariate statistical workflow.

### 1. Measurement Model

The initial measurement structure consists of:

**Overthinking Dimensions**

* Rumination
* Control
* Indecisiveness
* Negative Thinking
* Regret

**Decision-Making Quality Dimensions**

* Speed
* Confidence
* Consistency
* Evaluation
* Satisfaction

Each dimension consists of four questionnaire items.

### 2. Confirmatory Factor Analysis (CFA)

CFA is performed to evaluate construct validity.

An item is considered valid when:

* Standardized loading > 0.70
* p-value < 0.05

Dimensions are retained for subsequent analysis only when their measurement indicators satisfy the predefined validity criteria.

### 3. Reliability Analysis

Internal consistency is evaluated using **McDonald's Omega**.

A dimension is considered reliable when:

> **Omega > 0.70**

Only dimensions that pass both validity and reliability criteria are included in the final CCA model.

### 4. Assumption Testing

Several assumptions and diagnostic checks are performed before conducting the final CCA:

* Linearity using the **Ramsey RESET Test**
* Multivariate normality using **Mardia's Test**
* Multicollinearity using **Variance Inflation Factor (VIF)** and **Tolerance**

### 5. Normality Handling

Because CCA is sensitive to distributional assumptions, multiple approaches are evaluated when multivariate normality is not satisfied.

The project compares **8 approaches**:

| No. | Method                                |
| --- | ------------------------------------- |
| 1   | Raw / Baseline                        |
| 2   | Log Transformation                    |
| 3   | Square Root Transformation            |
| 4   | Box-Cox Transformation                |
| 5   | Yeo-Johnson Transformation            |
| 6   | Nonparanormal (NPN) Transformation    |
| 7   | Rank + Normal Quantile                |
| 8   | Ordered Quantile (ORQ) Transformation |

For each approach, multivariate normality is reassessed and CCA is performed to evaluate changes in canonical correlations and statistical significance.

### 6. Kernel Canonical Correlation Analysis

As an alternative to transformation-based approaches, **Kernel CCA** is also implemented.

Three kernel approaches are compared:

* Linear Kernel CCA
* RBF Kernel CCA
* Polynomial Kernel CCA

The RBF kernel is additionally evaluated across different sigma values to identify potential overfitting.

### 7. Method Comparison

Overall, **11 approaches** are compared:

* 8 transformation-based CCA approaches
* 3 Kernel CCA approaches

The comparison considers:

* Canonical correlations
* Statistical significance
* Number of significant canonical functions
* Potential overfitting

The best transformation-based method is selected based on the highest first canonical correlation that remains statistically significant and does not indicate overfitting.

---

## Analysis Workflow

```text
Questionnaire Dataset
        │
        ▼
Measurement Model
        │
        ▼
Confirmatory Factor Analysis
        │
        ▼
Validity Testing
        │
        ▼
Reliability Testing
        │
        ▼
Dimension Selection
        │
        ▼
Assumption Testing
 ┌──────┼───────────┐
 ▼      ▼           ▼
Linearity  Normality  Multicollinearity
        │
        ▼
Normality Handling
        │
 ┌──────┴─────────────────────┐
 ▼                            ▼
Transformation-Based CCA    Kernel CCA
 │                            │
 └──────────────┬─────────────┘
                ▼
       Method Comparison
                │
                ▼
       Best Method Selection
                │
                ▼
      Canonical Loadings &
        Canonical Weights
                │
                ▼
       Statistical Interpretation
```

---

## Statistical Techniques

This project applies the following statistical methods:

* Confirmatory Factor Analysis (CFA)
* McDonald's Omega
* Ramsey RESET Test
* Mardia's Multivariate Normality Test
* Canonical Correlation Analysis
* Wilks' Lambda Significance Test
* Kernel Canonical Correlation Analysis
* Variance Inflation Factor (VIF)
* Tolerance
* Canonical Loadings
* Canonical Weights

---

## Tools & Technologies

| Tool              | Purpose                                         |
| ----------------- | ----------------------------------------------- |
| **R**             | Statistical analysis                            |
| **R Markdown**    | Reproducible analysis and reporting             |
| **Excel**         | Dataset storage                                 |
| **lavaan**        | Confirmatory Factor Analysis                    |
| **semTools**      | Reliability analysis                            |
| **semPlot**       | Measurement model visualization                 |
| **MVN**           | Multivariate normality testing                  |
| **CCA**           | Canonical Correlation Analysis                  |
| **CCP**           | Significance testing for canonical correlations |
| **kernlab**       | Kernel CCA                                      |
| **MASS**          | Box-Cox transformation                          |
| **bestNormalize** | Normality transformations                       |
| **huge**          | Nonparanormal transformation                    |
| **car**           | Multicollinearity diagnostics                   |

---

## Repository Structure

```text
CCA-of-Overthinking-Dimensions-and-Decision-Making-Quality/
│
├── AOL_Multivariate.Rmd
├── AOL_Multivariate.html
├── MulVar_dataset.xlsx
├── [Paper PDF] Kelompok 2_AoL Multivariate Stat.pdf
├── [Paper Word] Kelompok 2_AoL Multivariate Stat.docx
└── README.md
```

### File Description

**`AOL_Multivariate.Rmd`**
Main R Markdown file containing the complete statistical analysis workflow.

**`AOL_Multivariate.html`**
Rendered HTML report containing the analysis results and explanations.

**`MulVar_dataset.xlsx`**
Dataset used for the multivariate analysis.

**Paper PDF / Word**
Supporting documentation describing the research and statistical analysis.

---

## Key Analytical Questions

This project addresses several questions:

* Which dimensions of overthinking and decision-making quality demonstrate adequate validity and reliability?
* Does the dataset satisfy the assumptions required for CCA?
* How does non-normality affect canonical correlation results?
* Do different transformation methods produce substantially different CCA results?
* Does Kernel CCA provide a meaningful alternative to transformation-based CCA?
* Which dimensions contribute most strongly to the canonical relationship between overthinking and decision-making quality?

---

## Results Interpretation

The final CCA model provides:

* Canonical correlation coefficients
* Significance testing using Wilks' Lambda
* Canonical loadings for both variable sets
* Canonical weights
* Dominant dimensions within each canonical function
* Comparison of alternative normality-handling methods

A canonical loading with an absolute value of **≥ 0.50** is treated as substantively meaningful for interpretation.

The final model is selected by considering both **statistical significance and the magnitude of the canonical correlation**, while avoiding solutions that indicate potential overfitting.

---

## Reproducibility

To reproduce the analysis:

### 1. Clone the repository

```bash
git clone https://github.com/zahraafandii/CCA-of-Overthinking-Dimensions-and-Decision-Making-Quality.git
```

### 2. Open the project in RStudio

Make sure `MulVar_dataset.xlsx` is located in the same directory as `AOL_Multivariate.Rmd`.

### 3. Install required packages

```r
install.packages(c(
  "readxl",
  "dplyr",
  "lavaan",
  "semTools",
  "semPlot",
  "MVN",
  "car",
  "CCA",
  "CCP",
  "kernlab",
  "huge",
  "bestNormalize",
  "MASS",
  "lmtest"
))
```

### 4. Run the R Markdown file

Open:

```text
AOL_Multivariate.Rmd
```

Then use **Knit → Knit to HTML** in RStudio.

---

## Project Focus

This project demonstrates the application of **multivariate statistical methods** to investigate relationships between two sets of psychological constructs while explicitly considering measurement quality and distributional assumptions.

Rather than applying CCA directly to the raw questionnaire data, the analysis follows a structured process of:

> **Measurement Validation → Assumption Testing → Normality Handling → CCA → Method Comparison → Interpretation**

This approach provides a more comprehensive assessment of how methodological choices can influence multivariate statistical results.

---

## Author
* Britney Angeline Soeseno
* Ivana Joyceline
* Zahra Annisa Afandi

Computer Science & Statistics Undergraduate
BINUS University

---

## License

This repository is intended for **academic and educational purposes**.
