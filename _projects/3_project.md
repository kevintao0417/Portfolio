---
layout: page
title: Evaluating Fire Response Strategies in Chapel Hill
description: A spatial analysis and optimization project balancing emergency response efficiency with community noise reduction.
img: assets/img/projects/project3/1.png
importance: 2
category: Study
giscus_comments: false
---

## Evaluating Fire Response Strategies in Chapel Hill

[cite_start]This project, developed by **Kevin Tao, Maggie Xu, Tony Hou, and William Gresham**, explores the critical trade-off between emergency response safety and community nuisance in Chapel Hill, NC[cite: 3, 10]. [cite_start]By integrating 911 dispatch data with fire station records, the team analyzed the impact of fire engine sirens on residential sleep and health, proposing optimized routing strategies to maintain the 4-minute national response standard while minimizing disruption[cite: 5, 8, 70, 98].

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project3/fire_response_poster.png" title="Project Poster" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Visualizing the conflict: Fire safety necessity vs. community nuisance.
</div>

### Project Overview

[cite_start]The core conflict addressed in this study is the "Chapel Hill Trade-off": Fire engine sirens are essential for clearing traffic to save lives, yet repeated high-volume noise, especially at night, erodes community health and sleep quality[cite: 5, 7, 10]. [cite_start]With budget constraints preventing the addition of new fire engines or stations (estimated at $1.5 million per engine plus personnel costs), the research question focused on optimization: **Can we design quieter routes that do not compromise safety?**[cite: 93, 98].

### Data Sources and Processing

[cite_start]The team collaborated with Assistant Chief David Sasser to obtain a comprehensive 5-year fire incident dataset[cite: 12]. [cite_start]This required merging distinct datasets from the 911 Center and the Chapel Hill Fire Station to create a unified view of the incident lifecycle[cite: 13].

Key processing steps included:

- [cite_start]**Data Merging:** Joining disparate datasets by timestamp to link call receipt, dispatch, and arrival times[cite: 13, 18, 22].
- **Filtering:** Removing invalid dates and isolating non-EMS calls to serve as a proxy for "full-siren" events[cite: 13].
- [cite_start]**Geospatial Mapping:** Utilizing Latitude/Longitude coordinates to map incidents against Fire Zones and Response Zones[cite: 43, 51, 55].

```python
# Proxy code representing the data cleaning process described
import pandas as pd

# Load datasets
dispatch_data = pd.read_csv('911_center_data.csv')
station_data = pd.read_csv('fire_station_data.csv')

# Merge by time and filter for validity
merged_df = pd.merge(dispatch_data, station_data, on='timestamp', how='inner')

# Filter to non-EMS calls (Full-Siren Proxy) and remove invalid dates
fire_events = merged_df[
    (merged_df['call_type'] != 'EMS') &
    (merged_df['arrival_time'].notnull())
].copy()
```
