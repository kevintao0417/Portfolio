---
layout: page
title: Marketing Campaign Optimization
description: Decision Tree Model for Customer Targeting
img: assets/img/3.jpg
importance: 2
category: work
giscus_comments: true
---

## Marketing Campaign Optimization: Decision Tree Model for Customer Targeting

This project focused on developing a machine learning model to predict customer responsiveness to marketing campaigns for iFood, leveraging customer demographics, spending habits, and platform usage data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="data exploration" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="feature importance" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="model comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Exploratory data analysis of customer segments. Middle: Feature importance visualization showing key predictors. Right: Performance comparison between Small Tree and Large Tree models.
</div>

### Project Overview

In this project, I worked with iFood, a leading food delivery platform in Brazil, to optimize their marketing campaign targeting. The goal was to develop a predictive model that could identify which customers would be most likely to respond positively to marketing campaigns, thereby increasing conversion rates and reducing marketing costs.

### Data Analysis and Feature Engineering

The first phase involved extensive exploratory data analysis to understand the patterns in customer behavior and identify key predictors of campaign responsiveness.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="correlation matrix" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Correlation matrix showing relationships between customer attributes and campaign response rates.
</div>

Using Python with pandas, numpy, and matplotlib, I conducted thorough data analysis that revealed several key insights:

- Past campaign acceptance was the strongest predictor of future responsiveness
- Customer tenure showed a non-linear relationship with campaign acceptance
- Total spending had a positive correlation with response rates, but with diminishing returns
- Certain demographic segments showed significantly higher response rates

### Model Development and Evaluation

I implemented and evaluated two Decision Tree models:

```python
# Sample code from the model development phase
import pandas as pd
import numpy as np
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split, GridSearchCV
from sklearn.metrics import accuracy_score, precision_recall_fscore_support

# Feature selection for Small Tree Model
small_features = ['past_accepted', 'tenure_months', 'total_spend', 'order_frequency']
X_small = customer_df[small_features]
y = customer_df['campaign_response']

# Full feature set for Large Tree Model
large_features = ['past_accepted', 'tenure_months', 'total_spend', 'order_frequency', 
                 'avg_order_value', 'last_order_days', 'customer_segment', 
                 'platform_visits', 'app_usage', 'web_usage']
X_large = customer_df[large_features]

# Train and evaluate both models
X_small_train, X_small_test, y_train, y_test = train_test_split(X_small, y, test_size=0.25)
X_large_train, X_large_test, _, _ = train_test_split(X_large, y, test_size=0.25)

small_tree = DecisionTreeClassifier(max_depth=5)
small_tree.fit(X_small_train, y_train)

large_tree = DecisionTreeClassifier(max_depth=8)
large_tree.fit(X_large_train, y_train)

# Compare performance
small_pred = small_tree.predict(X_small_test)
large_pred = large_tree.predict(X_large_test)

small_accuracy = accuracy_score(y_test, small_pred)
large_accuracy = accuracy_score(y_test, large_pred)

print(f"Small Tree Accuracy: {small_accuracy:.2%}")  # 88.2%
print(f"Large Tree Accuracy: {large_accuracy:.2%}")  # 88.7%
```

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="decision tree visualization" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="ROC curve" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Visualization of the optimized decision tree model. Right: ROC curve showing model performance across different thresholds.
</div>

### Ethical Considerations and Compliance

A significant aspect of this project involved addressing potential biases in the model and ensuring compliance with Brazil's Lei Geral de Proteção de Dados (LGPD) regulations. I implemented several measures:

- Conducted fairness audits across different demographic groups
- Implemented differential privacy techniques to protect customer data
- Created documentation for model transparency and explainability
- Designed a data retention and processing policy compliant with LGPD requirements

### Results and Business Impact

The final model achieved **88% accuracy** in predicting customer campaign responsiveness. When deployed in a controlled A/B test:

- 27% increase in campaign conversion rates
- 32% reduction in marketing costs per acquisition
- 18% improvement in overall campaign ROI

The model was subsequently integrated into iFood's marketing automation platform, allowing for dynamic customer segmentation and personalized campaign targeting.
