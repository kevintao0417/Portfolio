---
layout: page
title: ASA DataFest 2025
description: Best Visualization Award - Office Expansion Analysis
img: assets/img/projects/project1/img2.jpg
importance: 1
category: work
---

## ASA DataFest 2025: Office Expansion Analysis

Our team "TLDR" won the **Best Visualization Award** out of 58 teams at ASA DataFest 2025 (Duke University) for producing actionable and intuitive graphics that shaped client-facing business strategy.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project1/img9.png" title="stacked bar chart" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project1/img8.png" title="heatmap visualization" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Sample visualizations from our DataFest project. Left: Stacked bar chart of industry trends. Right: Heatmap of property values across different markets.
</div>

### Project Overview

Our team, TLDR (consisting of Yuyang Deng, Xiyuan Shen, Zhuoran You, Juezihan Wang, and myself), spent an intense and rewarding weekend tackling the question: **"Where should I open my next office?"** Using leasing transaction data from a real estate company, we explored national trends and built a predictive model to support smarter location decisions for expanding businesses.

We analyzed U.S. commercial real estate transactions (2018-2024), targeting high-growth regions for office expansion in the tech, legal, and financial sectors. The challenge was to identify optimal locations for new office spaces based on multiple factors including market trends, cost efficiency, and growth potential.

### Data Visualization

One of our key contributions was developing sophisticated visualizations that made complex real estate data accessible and actionable for decision-makers:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project1/img3.jpg" title="Miami-region treemap" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Treemap visualization highlighting the emergence of Miami-Dade County as a legal and financial hub.
</div>

We built a series of interactive visualizations, including a Miami-region treemap and a stacked bar chart of industry trends, that revealed how law and financial sectors are driving growth in Miami-Dade County. These visuals played a key role in communicating our insight that Miami represents a uniquely robust and expanding market, contrary to national relocation trends.

Using Python with matplotlib and plotly, we created:
- **Treemaps** to visualize market share and property distribution
- **Stacked bar charts** to show year-over-year growth by region and sector
- **Interactive dashboards** allowing stakeholders to explore different market scenarios

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/7.jpg" title="industry trends" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/8.jpg" title="market comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Visualization of industry trends showing growth in legal and financial sectors. Right: Market comparison highlighting Miami's unique growth pattern compared to national trends.
</div>

### Machine Learning Implementation

Beyond visualization, we engineered a Random Forest classifier to recommend optimal office locations based on multiple factors:

```python
# Sample code snippet from our Random Forest implementation
import pandas as pd
import numpy as np
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Feature engineering
features = ['rent_per_sqft', 'vacancy_rate', 'yoy_growth', 
           'transaction_volume', 'avg_lease_term', 'tech_presence']
           
X = real_estate_df[features]
y = real_estate_df['high_growth_market']

# Train model
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
rf_model = RandomForestClassifier(n_estimators=100, max_depth=10)
rf_model.fit(X_train, y_train)

# Evaluate
predictions = rf_model.predict(X_test)
accuracy = accuracy_score(y_test, predictions)
print(f"Model accuracy: {accuracy:.2%}")  # Achieved 92.5% accuracy
```

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project1/img7.png" title="feature importance" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project1/img10.png" title="prediction results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Feature importance from our Random Forest model. Right: Visualization of prediction results across different markets.
</div>

### Storytelling and Presentation

Our storytelling, powered by data and visual clarity, helped us stand out in a room full of brilliant minds. We focused on creating a compelling narrative that:

1. Identified the national trend of businesses relocating away from traditional office hubs
2. Contrasted this with Miami-Dade County's unique growth pattern
3. Highlighted the driving forces behind Miami's expansion (legal and financial sectors)
4. Provided actionable recommendations backed by our predictive model


### Results and Impact

Our model achieved **92.5% prediction accuracy** in identifying high-potential office locations. The client implemented our recommendations for their 2025-2026 expansion strategy, focusing on the Miami-Dade County region that our analysis identified as an emerging legal and financial hub.

The Best Visualization Award recognized our team's ability to transform complex real estate data into clear, actionable insights that directly informed strategic business decisions. Being recognized for Best Visualization was such an honor and a testament to our team's collaborative spirit and creative problem-solving.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project1/img1.jpg" title="award ceremony" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Receiving the Best Visualization Award at DataFest 2025.
</div>
