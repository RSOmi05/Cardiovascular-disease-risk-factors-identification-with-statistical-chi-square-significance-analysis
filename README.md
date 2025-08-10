# Cardiovascular-disease-risk-factors-identification-with-statistical-chi-square-significance-analysis

# Healthcare Chi-Square Statistical Significance Analysis

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Data Science](https://img.shields.io/badge/Data%20Science-Chi--Square-orange.svg)]()
[![Healthcare](https://img.shields.io/badge/Domain-Healthcare-red.svg)]()

## 📋 Table of Contents
- [Overview](#-overview)
- [Dataset Information](#-dataset-information)
- [Methodology](#-methodology)
- [Chi-Square Test Algorithm](#-chi-square-test-algorithm)
- [Mathematical Foundation](#-mathematical-foundation)
- [Key Findings](#-key-findings)
- [Statistical Results](#-statistical-results)
- [Clinical Implications](#-clinical-implications)
- [Installation & Usage](#-installation--usage)
- [Project Structure](#-project-structure)
- [Future Work](#-future-work)
- [Contact](#-contact)

## 🏥 Overview

This project presents a comprehensive **Chi-Square statistical analysis** of healthcare data to identify statistically significant categorical features associated with **cardiovascular disease** and **diabetes** outcomes. The analysis employs rigorous statistical methodology to uncover meaningful associations between demographic, socioeconomic, and health-related variables.

### 🎯 Research Objectives
- Identify statistically significant predictors of cardiovascular disease and diabetes
- Apply Chi-Square test of independence for categorical feature selection
- Provide evidence-based insights for public health interventions
- Analyze demographic and regional health disparities

### 🔬 Scientific Context
This work is complemented by a systematic review of the **Kaunas cardiovascular risk cohort study**, which demonstrates the long-term impact of childhood anthropometric measures on adult cardiovascular risk over a 35-year follow-up period.

## 📊 Dataset Information

| Characteristic | Value |
|----------------|-------|
| **Total Records** | 29,000+ individuals |
| **Data Type** | Cross-sectional health survey |
| **Primary Outcomes** | Cardiovascular Disease, Diabetes |
| **Feature Categories** | Demographics, Socioeconomics, Health Metrics |
| **Analysis Method** | Chi-Square Test of Independence |

### 📋 Key Variables Analyzed
- **Demographics**: Age group, Gender, Union name (location)
- **Health Status**: Hypertension, Stroke history, BMI status
- **Clinical Measurements**: Blood pressure, Blood sugar, SpO2, MUAC
- **Socioeconomic**: Income level, Poverty status
- **Special Categories**: Disability status, Freedom fighter status

## 🔬 Methodology

### Data Preparation Pipeline
1. **Missing Data Handling**: Listwise deletion for complete case analysis
2. **Age Categorization**: 
   - Child/Adolescent (< 18 years)
   - Young Adult (18-39 years)
   - Middle-aged Adult (40-59 years)
   - Older Adult (≥ 60 years)
3. **Disability Recoding**: '0' values → 'No Disability'

### Statistical Framework
- **Test**: Chi-Square Test of Independence
- **Significance Level**: α = 0.05
- **Null Hypothesis (H₀)**: Variables are independent
- **Alternative Hypothesis (Hₐ)**: Variables are dependent

## 🧮 Chi-Square Test Algorithm

### Step-by-Step Implementation

#### 1️⃣ **Hypothesis Definition**
```
H₀: The two categorical variables are independent
Hₐ: There is a statistically significant association between variables
```

#### 2️⃣ **Significance Level Setting**
```
α = 0.05 (5% probability of Type I error)
```

#### 3️⃣ **Contingency Table Construction**
Create cross-tabulation showing observed frequencies (Oᵢⱼ)

#### 4️⃣ **Expected Frequencies Calculation**
```
Eᵢⱼ = (Row Total i × Column Total j) / Grand Total
```

#### 5️⃣ **Chi-Square Statistic Calculation**
```
χ² = Σᵢ Σⱼ [(Oᵢⱼ - Eᵢⱼ)² / Eᵢⱼ]
```

#### 6️⃣ **Degrees of Freedom**
```
df = (Number of Rows - 1) × (Number of Columns - 1)
```

#### 7️⃣ **p-value Determination**
Compare χ² statistic against Chi-Square distribution

#### 8️⃣ **Statistical Decision**
```
If p-value ≤ α: Reject H₀ (Significant association)
If p-value > α: Fail to reject H₀ (No significant association)
```

## 📐 Mathematical Foundation

### Core Formula
The Chi-Square test statistic is calculated as:

```
χ² = Σᵢ₌₁ʳ Σⱼ₌₁ᶜ [(Oᵢⱼ - Eᵢⱼ)² / Eᵢⱼ]

Where:
- Oᵢⱼ = Observed frequency in cell (i,j)
- Eᵢⱼ = Expected frequency in cell (i,j)
- r = Number of rows
- c = Number of columns
```

### Example Calculation: Gender vs Cardiovascular Disease

| | Has CVD | No CVD | Total |
|---|---------|--------|-------|
| **Male** | 9 (7.67) | 6,754 (6,755.33) | 6,763 |
| **Female** | 25 (26.33) | 23,211 (23,209.67) | 23,236 |
| **Total** | 34 | 29,965 | 29,999 |

**Results**: χ² = 0.3006, df = 1, p = 0.5835 (Not Significant)

## 🏆 Key Findings

### 🔥 Highly Significant Associations (p < 0.001)
| Feature | χ² Statistic | p-value | Interpretation |
|---------|-------------|---------|----------------|
| **Hypertension Status** | 230.07 | < 0.001 | 🔴 **Critical Risk Factor** |
| **Stroke History** | 1,151.66 | < 0.001 | 🔴 **Strongest Predictor** |
| **Diabetes Status** | 91.69 | < 0.001 | 🔴 **Major Comorbidity** |
| **Geographic Location** | 125.95 | < 0.001 | 🔴 **Regional Disparities** |

### ⚠️ Significant Associations (p < 0.05)
| Feature | χ² Statistic | p-value | Clinical Relevance |
|---------|-------------|---------|-------------------|
| **Age Group** | 12.83 | 0.005 | 🟡 Age-related risk increase |
| **Blood Pressure Status** | 11.67 | < 0.001 | 🟡 Circulatory health marker |
| **Blood Sugar Status** | 26.08 | 0.0002 | 🟡 Metabolic dysfunction |

### ❌ Non-Significant Associations
- Gender (p = 0.5835)
- Income Level (p = 0.177)
- BMI Status (p = 1.0)
- Disability Status (p = 0.999)

## 📈 Statistical Results

### Distribution of Significant Features
```
Highly Significant (p < 0.001): 4 features (25%)
Significant (p < 0.05): 3 features (18.8%)
Non-Significant (p ≥ 0.05): 9 features (56.2%)
```

### Effect Size Analysis
- **Large Effect**: Stroke history, Hypertension (χ² > 100)
- **Medium Effect**: Diabetes, Geographic location (χ² = 50-150)
- **Small Effect**: Age group, Blood parameters (χ² < 50)

## 🏥 Clinical Implications

### 🎯 **Primary Risk Factors**
1. **Hypertension Management**: Critical intervention target
2. **Stroke Prevention**: Highest priority for cardiovascular risk reduction
3. **Diabetes Control**: Essential comorbidity management
4. **Regional Health Programs**: Address geographic disparities

### 📍 **Public Health Strategies**
- **Targeted Screening**: Focus on high-risk age groups and regions
- **Preventive Care**: Early intervention for hypertension and diabetes
- **Resource Allocation**: Prioritize areas with significant regional variations
- **Integrated Care**: Address multiple risk factors simultaneously

### 🔍 **Population Health Insights**
- Age-related cardiovascular risk increases significantly after 40
- Geographic location indicates environmental/lifestyle factors
- Gender shows no significant independent association
- Socioeconomic factors require further multivariate analysis

## 🛠️ Installation & Usage

### Prerequisites
```bash
pip install pandas numpy scipy
```

### Quick Start
```python
# Clone repository
git clone https://github.com/yourusername/healthcare-chi-square-statistical-significance-analysis.git

# Navigate to directory
cd healthcare-chi-square-statistical-significance-analysis

# Run analysis
python chi_square_analysis.py
```

### Usage Example
```python
from chi_square_analysis import ChiSquareAnalyzer

# Initialize analyzer
analyzer = ChiSquareAnalyzer('test-dataset.xlsx')

# Perform chi-square tests
results = analyzer.analyze_features(['has_cardiovascular_disease', 'diabetic'])

# Generate report
analyzer.generate_report(results)
```

## 📁 Project Structure

```
├── data/
│   ├── test-dataset.xlsx
│   └── processed_data/
├── src/
│   ├── chi_square_analysis.py
│   ├── data_preprocessing.py
│   ├── statistical_tests.py
│   └── visualization.py
├── results/
│   ├── statistical_reports/
│   ├── contingency_tables/
│   └── visualizations/
├── notebooks/
│   └── Healthcare_Statistical_Analysis.ipynb
├── docs/
│   ├── methodology.md
│   └── clinical_interpretations.md
├── README.md
└── requirements.txt
```

## 🔮 Future Work

### 🚀 **Statistical Enhancements**
- [ ] Multivariate logistic regression analysis
- [ ] Subgroup analysis by demographics
- [ ] Effect size calculations (Cramér's V)
- [ ] Multiple comparison corrections

### 📊 **Advanced Analytics**
- [ ] Machine learning feature importance validation
- [ ] Longitudinal analysis integration
- [ ] Predictive modeling development
- [ ] Causal inference analysis

### 🏥 **Clinical Applications**
- [ ] Risk prediction score development
- [ ] Clinical decision support tools
- [ ] Population health dashboards
- [ ] Intervention effectiveness studies



## 📧 Contact

**Rahat Shahrior**
- 📧 Email: rahat.shahriar04@gmail.com
- 📱 Phone: +880 1975714851
- 🏢 Affiliation: AIMS Lab

## 📚 References

### Scientific Publications
- Petkeviciene, J., et al. (2015). Anthropometric measurements in childhood and prediction of cardiovascular disease risk factors in adulthood: Kaunas cardiovascular risk cohort study. *BMC Public Health*, 15, 218.

### Statistical Methods
- Pearson, K. (1900). On the criterion that a given system of deviations from the probable in the case of a correlated system of variables is such that it can be reasonably supposed to have arisen from random sampling.
- Cochran, W.G. (1954). Some methods for strengthening the common χ² tests.

---

⭐ **If this analysis helped your research, please star this repository!**

💡 **For questions about methodology or clinical interpretations, feel free to reach out!**
