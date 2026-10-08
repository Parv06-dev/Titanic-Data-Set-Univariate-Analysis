# Titanic Dataset — Univariate Analysis

## 📌 Overview

This project performs **univariate analysis** on the Titanic dataset.

The objective is to understand the distribution of individual variables using visualizations such as:

- Pie charts
- Bar charts
- Histograms
- KDE (density) plots
- Box plots

The analysis is focused on **one variable at a time**, without studying relationships between multiple variables.

---

## 📂 Dataset

The dataset contains **891 passengers** and **12 columns**.

| Column | Description |
|---|---|
| `PassengerId` | Unique passenger identifier |
| `Survived` | Survival status (`0` = No, `1` = Yes) |
| `Pclass` | Passenger class (`1`, `2`, `3`) |
| `Name` | Passenger name |
| `Sex` | Passenger gender |
| `Age` | Passenger age |
| `SibSp` | Number of siblings/spouses aboard |
| `Parch` | Number of parents/children aboard |
| `Ticket` | Ticket number |
| `Fare` | Ticket fare |
| `Cabin` | Cabin number |
| `Embarked` | Port of embarkation |

### Missing Values

From the initial dataset inspection:

- `Age` contains missing values: **714 / 891** observations are available.
- `Cabin` contains many missing values: **204 / 891** observations are available.
- `Embarked` has **889 / 891** non-null observations.

> **Note:** The analysis below uses the data as present in the notebook. Missing-value handling is not performed in this notebook.

---

# 📊 Univariate Analysis

## 1. Gender Distribution

The `Sex` column was analyzed using a pie chart to understand the proportion of male and female passengers.

### Observation

The Titanic dataset contains a **higher proportion of male passengers than female passengers**.

This gives us an initial understanding of the gender composition of the passengers.

<img width="389" height="389" alt="gender_distribution" src="https://github.com/user-attachments/assets/f39a9aa7-87a0-4ec0-abf9-9e3e071b2db8" />


---

## 2. Survival Distribution

The `Survived` column was analyzed using a pie chart.

- `0` → Did not survive
- `1` → Survived

### Observation

Approximately **61.6% of the passengers did not survive**, while the remaining passengers survived.

This shows that the majority of passengers in the dataset lost their lives in the Titanic disaster.

<img width="389" height="389" alt="survival_distribution" src="https://github.com/user-attachments/assets/abe7b1ca-9d09-4280-8f7e-6e209159f8a1" />


---

## 3. Port of Embarkation

The `Embarked` column represents the port from which passengers boarded the Titanic.

The observed counts are:

| Port | Count |
|---|---:|
| Southampton (`S`) | 644 |
| Cherbourg (`C`) | 168 |
| Queenstown (`Q`) | 77 |

### Observation

The majority of passengers boarded from **Southampton**, followed by **Cherbourg** and **Queenstown**.

Southampton accounts for a substantially larger portion of the passengers than the other two ports.

<img width="389" height="389" alt="embarked_distribution" src="https://github.com/user-attachments/assets/b686f27e-cb9f-47cf-a18e-eb98a5f69a4c" />



---

## 4. Passenger Class — Bar Chart

The `Pclass` variable was visualized using a bar chart.

`Pclass` represents the passenger's travel class:

- `1` → First class
- `2` → Second class
- `3` → Third class

### Observation

The bar chart shows that **third-class passengers form the largest group** in the dataset.

This indicates that a significant proportion of the passengers travelled in third class.

<img width="552" height="427" alt="pclass_bar" src="https://github.com/user-attachments/assets/f3346163-c8a9-4eb7-9401-2d932b1a517f" />


---

## 5. Passenger Class — Pie Chart

The same `Pclass` variable was further visualized using a pie chart to examine the percentage distribution of passengers across the three classes.

### Observation

The pie chart makes the proportion of passengers in each class easier to compare.

**Third class has the largest share**, followed by first class and second class.

> Note: The fact that third class was the largest group does not, by itself, prove that passengers selected it because it was cheaper. That would require additional information or analysis involving fare/class.

<img width="389" height="389" alt="pclass_pie" src="https://github.com/user-attachments/assets/73b7fb1c-b3e3-4fd4-8ef1-3f05f472bd21" />


---

## 6. Age Distribution — Histogram

The `Age` variable was visualized using a histogram with five bins.

### Observation

Most passengers are concentrated in the **younger age groups**, with the largest number of observations falling approximately between **16 and 32 years**.

The number of observations in the five bins is:

| Age Range (approx.) | Observations |
|---|---:|
| 0.42 – 16.34 | 100 |
| 16.34 – 32.25 | 346 |
| 32.25 – 48.17 | 188 |
| 48.17 – 64.08 | 69 |
| 64.08 – 80.00 | 11 |

The distribution decreases as age increases, with relatively few passengers in the oldest age group.

<img width="552" height="413" alt="age_histogram" src="https://github.com/user-attachments/assets/3dfcf693-0f42-4eee-b35d-48c2f0d94c5a" />


---

## 7. Age Distribution — KDE Plot

A KDE (Kernel Density Estimate) plot was used to visualize the distribution of passenger ages as a smooth density curve.

### Observation

The density is highest among the **younger and middle-aged passengers**, while the density decreases for older passengers.

The KDE provides a smoother representation of the age distribution compared with the histogram.

<img width="585" height="432" alt="age_kde" src="https://github.com/user-attachments/assets/594230c6-21d2-4c9f-9a8c-ddf49f48507b" />


---

## 8. Age Distribution — Box Plot

A box plot was used to examine the distribution of passenger ages and identify potential outliers.

### Observation

The box plot provides information about:

- Median age
- Interquartile range (IQR)
- Spread of the age variable
- Potential outliers

There are some observations at the higher end of the age range that appear as potential outliers relative to the central distribution.

<img width="563" height="394" alt="age_boxplot" src="https://github.com/user-attachments/assets/bcfb359c-d1c6-4951-b208-fb3b8623f91e" />


---

# 🔎 Key Findings

From the univariate analysis:

1. **Male passengers are more numerous than female passengers.**
2. Approximately **61.6% of passengers did not survive**.
3. **Southampton** was the most common port of embarkation.
4. **Third class** contains the largest number of passengers.
5. Most passengers are concentrated in the **younger age groups**.
6. The age distribution has relatively few passengers at the upper end of the age range.
7. The box plot helps identify the spread and potential high-age outliers.

---

# 🧠 What This Analysis Shows

Univariate analysis is useful as an initial step in Exploratory Data Analysis (EDA).

Before studying relationships such as:

- `Sex` vs `Survived`
- `Pclass` vs `Survived`
- `Age` vs `Survived`
- `Fare` vs `Pclass`

it is useful to first understand the distribution of each individual variable.

This notebook therefore provides a **first-level understanding of the Titanic dataset** before moving towards bivariate and multivariate analysis.

---

## 🛠️ Technologies Used

- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 📁 Suggested Project Structure

```text
Titanic-Univariate-Analysis/
│
├── Univariate data_Analysis.ipynb
├── Train.csv
├── README.md
```

