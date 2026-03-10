# Credit Card Customer Segmentation

A customer segmentation project focused on identifying meaningful credit card user groups based on behavioral patterns such as purchases, payments, balances, and cash advance usage.

## Team

This project was developed as a team effort by:

- George Zippidis
- Katerina Lama
- Manos Polydoros
- Themis Mamatsopoulos

## Project Overview

Not all credit card customers behave in the same way. Some are highly active and consistently pay in full, others use their card only lightly, while some show stronger cash advance reliance and more financially pressured behavior.

The goal of this project was to segment customers into interpretable groups based on their behavior and identify patterns that could support more targeted decision-making.

## Objective

The main objective was to answer the following question:

**Can we identify meaningful customer groups based on credit card behavior such as purchases, payments, balances, and cash advance usage?**

## Dataset

The project uses the **Market Segmentation in Insurance Unsupervised** dataset from Kaggle, specifically the customer credit card behavior table used in this analysis.

- Source details are provided in: `1. Data/DATA_SOURCE.txt`
- The dataset file is **not included in this repository**
- Download the dataset using the source link in `1. Data/DATA_SOURCE.txt`
- Place the file inside the `1. Data/` folder before running the notebooks

Expected file path:

```text
1. Data/Customer Data.csv
```

## Repository Structure

```text
Credit Card Customer Segmentation/
├── 1. Data/
│   └── DATA_SOURCE.txt
├── 2. Analysis/
│   ├── 01_analysis.ipynb
│   └── figures/
├── 3. EDA/
│   ├── 01_eda.ipynb
│   └── figures/
├── 4. Modeling/
│   ├── 01_modeling.ipynb
│   └── figures/
├── 5. Presentation/
│   ├── Presentation.pdf
│   └── figures/
├── environment.yml
└── requirements.txt
```

## Workflow Summary

The project was developed in three main stages:

### 1. Analysis
Initial dataset inspection and structural review:
- data types
- missing values
- zero-heavy variables
- skewness
- correlation patterns
- feature watchlist for modeling decisions

### 2. Exploratory Data Analysis (EDA)
Behavior-oriented exploration of customer activity:
- purchase mix
- payment behavior
- credit utilization patterns
- purchase frequency and transaction intensity
- behavioral comparisons across customer subgroups

### 3. Modeling
Unsupervised clustering workflow:
- baseline preprocessing
- enhanced preprocessing with improved handling of skewed features
- comparison of multiple clustering approaches
- final customer profiling and interpretation

## Modeling Approach

The following clustering algorithms were evaluated:

- KMeans
- Agglomerative Clustering
- Gaussian Mixture

The modeling process included two main preprocessing strategies:

### Baseline Pipeline
- median imputation
- robust scaling

### Enhanced Pipeline
- median imputation
- selective transformation of highly skewed monetary variables
- robust scaling

The enhanced pipeline produced more balanced and interpretable customer groups, so it was used for the final solution.

## Final Solution

The selected final solution was:

- **Model:** KMeans
- **Number of clusters:** 4
- **Pipeline:** Enhanced preprocessing pipeline

This solution offered the best balance between:
- interpretability
- segment distinctiveness
- cluster balance
- practical usefulness

## Final Customer Segments

The final 4 customer groups were interpreted as follows:

### 1. Mainstream Revolving Users
- largest customer group
- moderate purchases and payments
- balanced but less distinctive overall behavior

### 2. Active Full-Payers
- high purchase activity
- strong installment usage
- consistently high full-payment behavior

### 3. Low-Activity Users
- lower balances
- fewer purchases
- limited overall engagement

### 4. Cash-Advance Stressed Users
- high cash advance usage
- higher balances
- stronger signs of financially pressured behavior

## Key Takeaways

- customers are not one homogeneous group
- the final solution revealed 4 meaningful and interpretable segments
- different groups require different actions
- segmentation can support more targeted and effective decision-making

## Segment Interpretation Focus

This project focuses on **segment interpretation** rather than direct business recommendation deployment.  
The main value of the analysis is understanding how customers differ in their usage and payment behavior, and how these differences can be translated into clear customer profiles.

## Visual Example

Below is a PCA projection of the final KMeans (k=4) solution:

![KMeans k=4 PCA Scatter](4.%20Modeling/figures/16_kmeans_k4_pca_scatter.png)

## Presentation

The final presentation used for this project is available at:

- `5. Presentation/Presentation.pdf`

## Installation

You can run the project using either **conda** or **pip**.

### Option 1 — Conda

```bash
conda env create -f environment.yml
conda activate credit-card-segmentation
```

### Option 2 — Pip

```bash
pip install -r requirements.txt
```

## Main Libraries Used

- numpy
- pandas
- scipy
- scikit-learn
- matplotlib
- seaborn
- jupyter
- notebook
- ipykernel
- openpyxl

## How to Reproduce

1. Clone the repository
2. Create the environment using `environment.yml` or `requirements.txt`
3. Download the dataset using the source link in `1. Data/DATA_SOURCE.txt`
4. Place the dataset file inside `1. Data/` as `Customer Data.csv`
5. Run the notebooks in order:

```text
2. Analysis/01_analysis.ipynb
3. EDA/01_eda.ipynb
4. Modeling/01_modeling.ipynb
```

## Notes

- The project was developed for an unsupervised machine learning assignment.
- The repository includes the notebooks, generated figures, and the final presentation.
- Source attribution for the dataset is provided in `1. Data/DATA_SOURCE.txt`.
- The dataset itself is not distributed in this repository.