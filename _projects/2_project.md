---
layout: page
title: Marketing Campaign Optimization for iFood
description: A case study on using data-driven insights to optimize marketing campaigns.
img: assets/img/projects/project2/project_poster.png
importance: 2
category: Study
giscus_comments: false
---

## Marketing Campaign Optimization for iFood

This project, developed by Yi Tan, Gordan Tao, Shengkai Tao, and Thomas You, aimed to enhance the effectiveness of iFood's marketing campaigns by predicting customer response. By leveraging data-driven insights, the team developed a model to identify customers most likely to engage with marketing initiatives, thereby optimizing resource allocation and maximizing revenue.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project2/project_poster.png" title="Project Poster" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A high-level overview of the project, from data exploration to deployment.
</div>

### Project Overview

The primary research question was to determine the extent to which spending habits, demographic features, and activity patterns influence a customer’s likelihood of responding to marketing campaigns. The goal was to build a predictive model to help iFood target customers more effectively, improving campaign ROI and customer engagement.

### Data Analysis and Feature Engineering

The project utilized a dataset from iFood's internal database, containing customer demographics, purchasing trends, and campaign reactions. The data preparation phase involved several key steps:

- **Dropping Redundant Features:** Features like `Z_CostContact` and `Z_Revenue` were removed as they had no predictive value.
- **Consolidating Campaign Data:** Individual campaign acceptance features (`AcceptedCmp1`, `AcceptedCmp2`, etc.) were consolidated into a single `AcceptedCmpOverall` feature.
- **Ordinal Encoding:** The five mutually exclusive education features were converted into a single ordinal variable, `education_level`.
- **Handling Redundancy:** The `MntRegularProds` feature was dropped due to its perfect correlation with `MntTotal`.

Correlation matrices and visualizations were used to identify the most promising features for the model.

### Key Findings

The exploratory data analysis revealed several important insights:

- **`AcceptedCmpOverall`:** This feature had the highest correlation with the campaign response, indicating that past engagement is a strong predictor of future behavior.
- **`Customer_Days`:** The number of days a customer has been on the platform showed a positive correlation with their likelihood to respond.
- **`MntTotal` and `Income`:** Both total spending and income were identified as significant predictors of campaign response.

### Model Development and Evaluation

The team developed two Decision Tree Classifier models:

1.  **Small Tree Model:** Used a selected subset of the most predictive features (`AcceptedCmpOverall`, `Customer_Days`, `MntTotal`, `Income`).
2.  **Large Tree Model:** Utilized all available features to serve as a baseline for comparison.

Both models were optimized for tree depth to maximize performance while avoiding overfitting.

```python
# Pseudocode for creating the ordinal education variable
education_matrix = raw_data.filter(['education_Basic', 'education_2n_Cycle', 'education_Graduation', 'education_Master', 'education_PhD'])
education_level = education_matrix.values @ np.array([1, 2, 3, 4, 5])
raw_data['education_level'] = education_level
raw_data.drop(columns=['education_Basic', 'education_2n_Cycle', 'education_Graduation', 'education_Master', 'education_PhD'])
```

### Results and Deployment

Both the Small Tree and Large Tree models achieved a mean test accuracy of approximately **88%**. This demonstrated that careful feature selection could produce a model that was just as effective as one that used all features, but with greater interpretability and efficiency.

The deployment vision for the model includes:

- **Customer Segmentation:** Identifying and targeting customers with a high probability of responding to campaigns.
- **Resource Optimization:** Focusing marketing efforts on the most receptive audience to maximize ROI.
- **Personalized Offers:** Enabling the creation of targeted advertisements and promotions.

The team also highlighted the importance of addressing challenges such as data privacy (in compliance with LGPD), model scalability, and the need for continuous monitoring and retraining to adapt to changing customer behaviors.
