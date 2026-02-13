---
layout: page
title: Personal Resource Management
description: A physical data analysis exploring the digital consumption, sleep architecture, and hydration.
img: assets/img/projects/project4/Screenshot 2026-02-13 at 01.14.16.png
importance: 2
category: Fun
giscus_comments: false
---

## Visualization 1: Device Screen Time

The primary objective of this visualization was to determine how daily cognitive energy on screens is distributed among academic productivity, social connection, and personal entertainment.

### Data Collection

The data collection used the integrated Apple Screen Time system, which provides a synchronized record of application usage across both macOS and iOS platforms, which cover two devices I mainly use. This data begin from Monday, February 2, and concluding Sunday, February 8, 2026. Usage metrics were categorized into three functional domains to reflect the user's primary activities: Productivity & Learning (including tools like Google Chrome and Visual Studio Code), Social & Communication (messaging platforms), and Entertainment & Gaming (including entertainment related websites). I didn't use the built-in category made by the Screen Time function, but record the time for each apps and websites to re-categorized.

### Visualization Design

The process involved translating the digital consumption into a physical medium: pizza. The reason why to choose pizza is because I think pie chart will be a good technique to visualize the time usage for each domain, and pizza is perfect for this. Three specific varieties were selected to represent the data categories: Philly Cheese Steak for Productivity, BBQ for Social, and Pepperoni for Entertainment. The pizzas have been cut to standardized 8 slices, where each slice represented a portion of the daily digital "budget." By calculating specific ratios of slices from the three whole pizzas, a unique "Data Pizza" was constructed for each day of the week. This medium was chosen because pizza, like digital media, is a resource consumed to fuel or entertain the user.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project4/Screenshot 2026-02-13 at 01.14.16.png" title="Pizza with Screen Time" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Pizza with Screen Time
</div>
### Data Synthesis

The resulting visualization reveals a distinct "Academic Pulse" within the weekly routine. Thursday, February 5, emerged as the period of highest workload, where Philly Cheese Steak (Productivity) slices accounted for 75% of the pie, directly correlating with a weekly screen time peak of 13 hours and 20 minutes. In contrast, Monday displayed a more balanced leisure ratio, with Pepperoni (Entertainment) occupying 37.5% of the visualization. Throughout the week, Productivity remained the dominant "foundation" slice, confirming that the my digital life is primarily driven by their academic responsibilities.

---

## Visualization 2: Sleep Quality

### Target Question

This visualization addresses how restorative quality and stages of sleep change in a week.

### Data Collection

Sleep metrics were captured using an Apple Watch and processed through the Apple Health application. Monitoring was conducted continuously for seven consecutive nights, tracking five specific variables for each 24-hour cycle: Awake, REM, Core, and Deep sleep stages, in addition to Total Time Asleep.

### Visualization

The chosen medium for this visualization was a digital interactive chart created using Python and the `Plotly` library. This design employed a stacked bar chart to visualize the distribution of sleep phases for each 24-hour cycle. The chart also features a unified hover mode that displays precise duration data for all four stages simultaneously, mimicking the mobile application's functionality.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <iframe 
            src="{{ '/assets/plotly/projects/project4/sleep_stages_interactive.html' | relative_url }}" 
            width="100%" 
            height="500px" 
            style="border:none; background: transparent;" 
            allowtransparency="true"
            scrolling="no">
        </iframe>
    </div>
</div>
<div class="caption">
    Interactive Sleep Architecture: Hover to see precise durations for each stage.
</div>
### Data Synthesis

The synthesis of the sleep data reveals a complex relationship between digital usage and rest. While the total sleep duration showed a positive trend toward the weekend, peaking at 9 hours and 4 minutes on Sunday, the quality of that rest was inconsistent. On Thursday, the day of the highest digital engagement, Deep sleep reached a weekly minimum of only 49 minutes. This suggests that while the user can maintain a consistent sleep duration, high-intensity digital consumption may negatively impact the deeper, more restorative stages of physical recovery.

---

## Visualization 3: Daily Hydration

### Target Question

This visualization seeks to answer how daily hydration levels fluctuate during the week.

### Data Collection

The data collection for this metric involved tracking the total volume of water consumed in milliliters (ml) over the same seven-day period from February 2 to February 8, 2026. Intake was recorded manually each time a standardized water container was consumed. This logging allowed for real-time tracking of hydration throughout the day.

### Visualization

The physical medium selected for this data is a Bar Chart of Water Bottles. To represent the data with high fidelity, three different bottle sizes were used as modular units: large bottles to represent 500ml, small white-capped bottles to represent 200ml, and small blue-capped bottles to represent 100ml. For each day of the week, a vertical arrangement of these bottles was constructed to form a bar, with the total volume of the bottles in each stack corresponding to that day's intake. This choice of media makes the volume of consumption tangible. And the physical space occupied by the bottles reflects the volume of water consumed by the body.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project4/IMG_4108.jpg" title="from front" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/project4/IMG_4109.jpg" title="from top" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Front and Top view of my visualization.
</div>
### Data Synthesis

The hydration data reveals a trend that correlates with academic performance. On Thursday, February 5, which is the day of the highest recorded screen time (13 hours and 20 minutes), hydration reached a weekly low of only 600ml, represented in the visualization by just one 500ml bottle and one 100ml bottle. This indicates that as digital and cognitive demands increased, basic physical maintenance was deprioritized. Conversely, Friday, February 6, showed a spike of 1900ml, the highest of the week, suggesting a conscious effort to physically rehydrate once the most intense academic pressure of the week had passed.

## Wrap-up

The process of creating the three visualizations give me a feeling to significant contrast between "destructive" and "constructive" media. The pizza visualization was essentially destructive; the data required taking whole units and slicing them apart to represent a distribution. This made assessing parts of a whole extremely intuitive. In contrast, the water bottle visualization was additive and modular. Using different sizes of bottles made the volume of consumption immediately tangible. While the pizza represented a "budget" of time, the bottle stacks represented the physical "building" of biological fuel.

An observation from this process is the "Resource Management" theme that is everywhere in my life. By using physical objects from my daily life, the food I eat, the water I drink, and the professional tools I study with, the data felt less like an abstract assignment and more like a biological ledger. The physical act of cutting pizza or stacking bottles forced a moment of reflection on personal health and academic balance that automated tools simply do not provide.
