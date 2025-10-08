# 🚲 Bike Share Demand Analysis

## 🧩 Business Problem & Stakeholders

This project analyzes hourly bike-share usage data to identify key demand drivers and guide decisions across product, operations, and marketing teams.

**Stakeholders:**
- **Product Manager**: Rider behavior & feature testing.
- **Operations Lead**: Staffing, rebalancing, maintenance planning.
- **Marketing Lead**: Promo timing, rider segmentation.
- **Policy & Ethics Advisor**: Ensure equitable access and responsible insights.

---

## 🔬 Methods Summary

### Exploratory Data Analysis (EDA)
- Cleaned and transformed data using pandas in Python.
- Visualized hourly ridership trends by time, weather, and user type.

### Hypothesis Testing
- **Q1**: Working vs. non-working day ride counts → *Welch's t-test*
- Hypotheses:

Null hypothesis (H0): Mean hourly rides on working and non-working days are equal.

Alternative hypothesis (H1): Mean hourly rides on working and non-working days differ.

- **Q2**: Seasonal ride differences → *ANOVA + Tukey HSD*

Hypotheses:

Null hypothesis (H0): All seasonal means are equal (no difference in average hourly rides).

Alternative hypothesis (H1): At least one seasonal mean is different.

### Simulated A/B Test
- Feature launch impact on 17–19h commuter ridership.
- Stratified by weekday × hour × weather for control of confounders.

---

## 📈 Key Trends & Insights

<img width="757" height="378" alt="Screenshot 2025-10-08 at 2 50 49 PM" src="https://github.com/user-attachments/assets/863ee8e9-46b9-4bff-8e56-fc29653334b3" />

- Peak hours are 8 a.m. and 5 p.m. with roughly 350 & 475 average hourly riders repectively
- Rindership increases before and decrease after theses points
- Ridership has a strong relation ship with people commuting to work
  
<img width="755" height="566" alt="Screenshot 2025-10-08 at 2 51 24 PM" src="https://github.com/user-attachments/assets/0e7103b3-171e-4abf-a80a-f8cec1419276" />

- Less clear weather correlates with lower average ridership
- Clear weather has >200 Average riders compared to heavy snow/rain with < 100
<img width="600" height="602" alt="Screenshot 2025-10-08 at 2 53 36 PM" src="https://github.com/user-attachments/assets/d7db07a9-ee45-4f1a-91f8-4d300c646d30" />
- 
- 

---

## 📊 Hypothesis Test Results
<img width="754" height="566" alt="Screenshot 2025-10-08 at 3 14 16 PM" src="https://github.com/user-attachments/assets/e931a467-931a-4e41-9dd7-eca3ef76ba3a" />

### Q1: Working vs. Non-Working Days
- **Test**:   Welch’s t-test
- **Result**: p-value = 0.00004
- **95% CI**:  (6.15, 17.45)
- **Decision**:  Reject null hypothesis!
- **Practical Insight**: There is a statistically and practically significant difference in hourly ride counts between working and non-working days. On average, working days see 6 to 17 more rides per hour, which can translate to hundreds of additional daily rides.
This pattern reflects likely commuter behavior and should guide weekday-focused operational planning and targeted pricing or promotional strategies.

### Q2: Seasonal Differences
<img width="764" height="583" alt="Screenshot 2025-10-08 at 3 23 23 PM" src="https://github.com/user-attachments/assets/0b40132b-552a-4009-9b69-84d2903bb138" />

- **Test**: One-way ANOVA
- **Post-hoc**: TukeyHSD
- **Decision**: Reject the null hypothesis!
- **Insight**: Average hourly rides do significantly differ between at least some seasons.
The size of these differences with such a small p-value have clear operational, financial, and strategic implications for pricing, resource allocation, and customer engagement. making it not only statistically significant but practically significant aswell.

- The appropriate post-hoc approch would be a Tukey's HDS for pairwise comparisons between seasons to determine which specific pairs of seasons differ significantly. This would allow stakeholders to focus on seasons that may be underperforming.
---

## 🧪 A/B Test

- **Setup**: Pre (Aug 4–31) vs. Post (Sep 1–28)
- **Stratification**: Weekday × Hour × Weather
- **Result**: p-value = 0.000591
- **Recommendation**: The average increase of 41.15 bike rentals per hour (~15% jump) during commute hours is practically significant, even though the standardized effect size (d = 0.3) is modest.

This change could meaningfully affect staffing requirements, fleet sizing and rebalancing

---

## ✅ Recommendations



---

## ⚖️ Ethics & Limitations

### Limitations
- 

### Ethics
- 
---

## 📁 Files in This Repo
- `slides/`: presention with findings and insights.
- `data/`: Cleaned and raw datasets.
- `notebooks/`: Jupyter notebooks for EDA, testing, and modeling.
- `README.md`: Project overview and conclusions.
