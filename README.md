# ACE and the Race to Class: Improving Bus Speeds for CUNY Students

## Overview

This project analyzes NYC bus routes serving CUNY campuses to identify optimal candidates for Automated Camera Enforcement (ACE) implementation. Through predictive modeling and comprehensive data analysis, we demonstrate that ACE can significantly reduce bus delays and improve on-time arrival for CUNY students.

**Live Project:** [View Interactive Dashboard](https://furkanberatay.github.io/MTA_Project/)

## Table of Contents
- [Problem Statement](#problem-statement)
- [Research Questions](#research-questions)
- [Key Findings](#key-findings)
- [Methodology](#methodology)
- [Recommended Routes](#recommended-routes-for-ace-implementation)
- [Results](#results)
- [Recommendations](#recommendations)
- [Technical Stack](#technical-stack)
- [Team](#team)

## Problem Statement

Over **65% of CUNY students** experience class lateness due to inadequate bus service, with more than **50%** reporting chronic lateness when commuting by bus. Currently, only **16.7%** of CUNY bus routes are covered by ACE, leaving the majority of students vulnerable to delays caused by bus lane violations.

## Research Questions

1. What effect does ACE have on bus speeds?
2. How can ACE implementation improve CUNY students' on-time arrival to class?
3. What strategies can strengthen ACE effectiveness?

## Key Findings

### ACE Impact
- CUNY ACE buses experience a **10.1% increase** in speed overall
- Routes with ACE implementation show **+0.83 mph** average improvement
- After controlling for selection bias using propensity score matching, ACE demonstrates a conservative **+0.15 mph** improvement with 95% confidence

### Geographic Disparities
- **Manhattan** has the slowest average bus speeds at **7.1 mph** (48% reduction compared to Staten Island)
- Brooklyn and Manhattan require critical priority for ACE implementation
- Manhattan CUNY routes average below 7 mph during peak hours

### ACE Violations
- **46.7%** of exempt violators are repeat offenders
- Emergency vehicles account for **32.9%** of bus lane violations
- One repeat offender recorded over **1,377 violations**
- Most violations come from exempt emergency vehicles

### Route Selection Analysis
- Classification models reveal pre-ACE speed is the biggest determining factor for ACE route selection
- Routes are purposely selected based on their baseline speeds
- CUNY routes with ACE start from lower baseline speeds (7.6 mph) compared to non-ACE routes (8.3 mph)

## Methodology

### Data Sources
1. **MTA Bus Open Data** - Historical and near-real-time bus performance data across all boroughs
2. **NYC Traffic Violation Database** - 2022-2024 violations within 500-meter radius of CUNY campuses
3. **Student Survey** - 185 validated responses across 12 CUNY campuses (response rate 34%, margin of error ±7.2%)

### Analysis Approach
1. **Predictive Modeling** - Four regression algorithms evaluated (Linear, Ridge, Random Forest, Gradient Boosting)
2. **Model Selection** - Linear regression selected with R² = 0.850, indicating 85% of variance explained
3. **Feature Engineering** - Geographic encoding, temporal variables, route characteristics, ACE status
4. **Validation** - 70/30 train-test split with 5-fold cross-validation
5. **Matching Analysis** - Propensity score matching to control for selection bias

### Model Performance

| Model | Test R² | CV R² | RMSE/10 | Status |
|:------|:--------|:------|:--------|:--------|
| Linear Regression | 0.850 | 0.861 | 0.891 | **Selected** |
| Ridge Regression | 0.848 | 0.863 | 0.891 | Alternative |
| Random Forest | 0.850 | 0.868 | 0.891 | Alternative |
| Gradient Boosting | 0.830 | 0.863 | 0.891 | Alternative |

## Recommended Routes for ACE Implementation

### Priority Routes

#### 1. M9 (BMCC Students)
- **Current Speed:** 6.4 mph
- **Predicted with ACE:** 7.0 mph
- **Expected Improvement:** +0.6 mph (9.4% increase)

#### 2. B11 (Brooklyn College Students)
- **Current Speed:** 6.7 mph
- **Predicted with ACE:** 7.3 mph
- **Expected Improvement:** +0.6 mph (9.0% increase)

#### 3. Q34 (Queens College Students)
- **Current Speed:** 7.4 mph
- **Predicted with ACE:** 7.9 mph
- **Expected Improvement:** +0.5 mph (6.8% increase)

### Secondary Routes

#### 4. M101
- **Current Speed:** 12.5 mph
- **Predicted with ACE:** 12.7 mph
- **Expected Improvement:** +0.2 mph (1.6% increase)
- **Note:** High violation count indicates severe congestion challenges

#### 5. B103
- **Current Speed:** 8.8 mph
- **Predicted with ACE:** 9.0 mph
- **Expected Improvement:** +0.2 mph (2.3% increase)
- **Note:** Most frequently utilized route by students (10 mentions)

## Results

### Borough Performance Comparison

| Borough | Average Speed | ACE Priority |
|:--------|:--------------|:-------------|
| Staten Island | 13.6 mph | Low |
| Other | 10.7 mph | Medium |
| Queens | 10.0 mph | Medium |
| Bronx | 8.8 mph | High |
| Brooklyn | 8.4 mph | High |
| Manhattan | 7.1 mph | **Critical** |

### ACE Violation Analysis

| Exempt Category | Percentage | Implication |
|:----------------|:-----------|:------------|
| Emergency Vehicle | 32.9% | Essential services requiring priority access |
| Commercial Under 20 | 29.6% | Delivery vehicles contributing to congestion |
| Bus/Paratransit | 21.8% | Public transit requiring dedicated infrastructure |
| Other | 15.7% | Miscellaneous exempt vehicles |

### Pre vs Post ACE Performance

| Route Category | Pre-Implementation | Post-Implementation | Improvement |
|:---------------|:-------------------|:--------------------|:------------|
| CUNY with ACE | 7.6 mph | 8.3 mph | +0.7 mph (9.2%) |
| CUNY without ACE | 8.3 mph | 8.8 mph | +0.5 mph (6.0%) |

## Recommendations

### Implementation Strategy
1. Deploy ACE on **M9, B11, and Q34** routes as immediate priorities
2. Focus resources on **Manhattan and Brooklyn** corridors
3. Target routes with baseline speeds below **7.5 mph** for maximum impact

### Enforcement Improvements
1. Review exempt status for chronic offenders
2. Monitor exempt vehicle compliance, particularly emergency vehicles
3. Investigate repeat offenders with excessive violation counts
4. Implement stricter accountability for vehicles with repeated abuses

### Expected Outcomes
- Reduction in student lateness from **65% to below 40%** within 18 months
- Average speed improvement of **0.5-0.6 mph** on priority routes
- Enhanced service reliability across CUNY corridors

## Technical Stack

- **Programming:** Python
- **Data Analysis:** pandas, numpy
- **Machine Learning:** scikit-learn
- **Visualization:** matplotlib, seaborn
- **Statistical Analysis:** statsmodels

## Team

**Data Sultans**

## License

This project uses publicly available data from MTA Open Data and NYC Open Data portals.

---

*For questions or additional information about this analysis, please refer to the [project website](https://furkanberatay.github.io/MTA_Project/) or contact the Data Sultans team.*

