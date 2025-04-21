# 📊 Ultimatum Game Regression Analysis

This project explores human behavior in economic decision-making using the **Ultimatum Game**. Through regression modeling, we investigate how offer sizes, gender, and year-based experimental conditions influence the behavior of responders in a game setting that challenges the classical notion of rational self-interest.

---

## 🎯 Objective

To determine:
- How proposers’ offers evolve over time
- How responder decisions are influenced by offer size, time, and gender
- Whether regression models can reveal patterns in perceived fairness and acceptance behaviors

---

## 🧠 Background

The **Ultimatum Game**, introduced by Güth et al. (1982), illustrates the tension between economic rationality and fairness. In this game:
- One player (the **proposer**) offers a split of a fixed amount to another player (the **responder**).
- The responder can either **accept** (both players get the proposed split) or **reject** (neither gets anything).

This project aims to analyze variations in proposer offers and responder behavior using datasets from **classroom experiments (2016–2021)**, emphasizing fairness, altruism, and social norms.

---

## 🗃️ Dataset

Three main datasets were used:
- `2016.csv`
- `2019.csv`
- `2020–2021.csv`

They were **merged and processed** using Python's `pandas` library to create:
- Year-based dummy variables (`Y_2021`, `Y_2020`, `Y_201916`)
- A binary gender variable (1 = Male, 0 = Female)

---

## 📈 Methodology

Multiple **Ordinary Least Squares (OLS)** regressions were run in Python (`statsmodels`) to study:

### 1️⃣ Round 1 Offers
- With and without gender as an independent variable

### 2️⃣ Final Round Offers
- Focus on the last round of each session

### 3️⃣ Mean Offers Across Rounds
- Grouped by round to study average proposer behavior

### 4️⃣ Responder Decisions
- Binary regression to understand what influences the decision to accept/reject offers (via OLS due to multicollinearity limitations with Probit)

---

## 🧪 Tools & Libraries

- `Python 3.x`
- `Pandas` – for data manipulation
- `Statsmodels` – for regression analysis
- `Jupyter Notebook` – for exploration and reproducibility

---

## 📊 Regression Models

### ▶️ Model 1: Round 1
```math
Offers_1 = β0 + β1Y_2021 + β2Y_2020 + β3Y_201916 (+ β4Gender) + ε

🔍 Key Findings
Offers tended to be higher in recent years, potentially reflecting changing norms or experimental settings.

Gender had marginal influence on proposer behavior in some models.

Responder decisions were heavily influenced by the size of the offer—supporting fairness-based rejections.

Multicollinearity issues arose with year dummies in binary regression; OLS was used instead of Probit for interpretability.
