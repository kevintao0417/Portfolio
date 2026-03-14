# The $100,000 Question — H-1B Visa Data Story

**Author:** Shengkai Tao  
**Original Story:** [$100,000 Per Employee: How the H-1B Visa Fee Could Reshape Work Forces](https://www.nytimes.com/interactive/2025/09/25/business/economy/h1b-visa-fee.html) — *The New York Times*

## Design Process & Decisions

### 1. Conceptualization
The original New York Times story focused on the impact of a proposed fee hike on the H-1B program, primarily through anecdotal evidence and broad economic analysis. My goal for this remix was to **ground the narrative in raw data**, allowing the user to explore the actual distribution of H-1B dependence across different dimensions: volume, geography, and industry sector.

### 2. Visual Design
To maintain the gravity and authority of the original piece, I adopted a "NYT" design system same as the original story:
- **Typography:** Used Serif fonts for headings and narrative text, and Sans-serif for UI controls and labels.
- **Color Palette:** A minimalist palette using deep blues, high-contrast blacks/whites, and subtle gray borders to create a professional, "newsroom" feel.

### 3. Implementation of the Three Visualizations

#### **Visualization 1: Top 20 Employers**
- **Design Goal:** Reveal the "scale" of the top filers.
- **Interactivity:** Users can toggle between *Total*, *Initial*, and *Continuing* approvals. This allows the reader to see that while tech giants dominate continuing filings, the landscape changes for initial filings.

#### **Visualization 2: Geography of Dependence**
- **Design Goal:** Show that H-1B dependence is a national issue, not just a Silicon Valley one.
- **Interactivity:** Tooltips show exact counts and denial rates per state. A toggle between *Logarithmic* and *Linear* scales allows users to see both the dominance of states like California/Texas and the relative activity in smaller states.

#### **Visualization 3: Approvals vs. Denials by Industry**
- **Design Goal:** Highlight sectors that face higher bureaucratic hurdles.
- **Interactivity:** Hovering reveals the *Denial Rate*. Users can sort by either raw volume or denial percentage.

## Attribution
- **Data Source:** [USCIS H-1B Employer Data Hub (FY 2023)](https://www.uscis.gov/tools/reports-and-studies/h-1b-employer-data-hub).
