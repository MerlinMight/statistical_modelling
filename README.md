# 🏏 Quantifying "Killer Instinct": A Bayesian Cricket Analytics Project

### *Can we mathematically measure mental strength in T20 Cricket?*

![Project Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Tech Stack](https://img.shields.io/badge/Tech-Python%20%7C%20PyMC%20%7C%20Bayesian%20Inference-blue)
![Domain](https://img.shields.io/badge/Domain-Sports%20Analytics-orange)

## 📖 Executive Summary
In high-stakes T20 cricket auctions, teams often rely on "gut feeling" to judge intangible traits like mental toughness. This project resolves a strategic dilemma for a franchise deciding between two death-over specialists:
* **Bowler A ("The Machine"):** Consistent, economical, but accused of lacking "bite" under pressure.
* **Bowler B ("The Gambler"):** Volatile, expensive, but rumored to possess a "Killer Instinct."

**The Goal:** To translate the coach's intuition of "Killer Instinct" into a quantifiable metric using **Bayesian Hierarchical Modeling**.

**The Verdict:** The analysis rigorously proved that Bowler B's performance improves significantly under pressure, validating the "Killer Instinct" hypothesis and leading to a definitive recommendation to sign him despite his higher economy rate.

---

## ⚙️ Methodology

### 1. Defining the Metric
We defined "Pressure" quantitatively as a **Dot Ball bowled in the Death Overs (16-20)**. "Killer Instinct" was measured as the change in wicket-taking probability on the *immediate next ball* following a pressure event.

### 2. The Model (Bayesian Hierarchical Logistic Regression)
Built using **PyMC**, the model estimates the probability of a wicket ($p$) based on:
$$\text{logit}(p) = \alpha + \beta_{pressure} \cdot \text{Pressure} + \beta_{control} \cdot \text{Controls}$$

* **Hierarchical Structure:** Partially pools data across bowlers to prevent overfitting while capturing individual variances.
* **Control Variables:** Adjusted for **Pitch Type** (Batting/Bowling/Neutral) and **Batsman Quality** (Batting Average Z-Score).

---

## 📊 Key Findings

| Metric | Bowler A ("The Machine") | Bowler B ("The Gambler") |
| :--- | :---: | :---: |
| **Pressure Coefficient ($\beta$)** | **-0.71** (Negative Effect) | **+2.69** (Massive Positive Effect) |
| **94% HDI (Certainty)** | Crosses Zero (Insignificant) | **[2.32, 3.07]** (Highly Significant) |
| **Real-World Impact** | Wicket probability **drops** or stays flat. | Wicket probability **spikes by ~30%**. |
| **Conclusion** | Chokes or stays neutral under pressure. | **Thrives under pressure.** |

> **Insight:** 81.4% of Bowler B's death wickets occurred immediately after he applied pressure (a dot ball), compared to only 18.9% for Bowler A.

---

## 📈 Visualizations
*(Note: These plots are generated in the analysis notebook)*

1.  **Posterior Distribution:** Shows Bowler B's "Killer Instinct" curve shifted far to the right (positive), while Bowler A hovers near zero.
2.  **Calibration Curve:** The model achieved near-perfect calibration, proving the predicted probabilities match real-world frequency.
3.  **Posterior Predictive Check:** Simulated match data aligns perfectly with observed data, validating the model's physics.

---

## 🛠️ Tech Stack
* **Language:** Python 3.9+
* **Probabilistic Programming:** PyMC (MCMC Sampling, NUTS)
* **Visualization:** ArviZ, Seaborn, Matplotlib
* **Data Manipulation:** Pandas, NumPy
* **Reporting:** ReportLab (PDF Generation)

---

## 🚀 How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/cricket-killer-instinct.git](https://github.com/yourusername/cricket-killer-instinct.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pymc arviz pandas matplotlib seaborn reportlab
    ```
3.  **Run the Notebook:**
    Open `Killer_Instinct_Analysis.ipynb` to see the full Bayesian analysis and model diagnostics.
4.  **Generate Report:**
    Run the final cell to generate the `Executive_Summary.pdf`.

---

## 📝 Strategic Recommendation
**Sign Bowler B.**
While Bowler A saves runs, Bowler B wins matches. The "premium" paid in his economy rate buys a rare, statistically verified skill: the ability to convert pressure into breakthroughs. In a format where wickets are the only way to stop scoring momentum, Bowler B is the superior asset.

---
