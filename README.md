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



## 📈 Key Trends & Insights

<img width="757" height="378" alt="Screenshot 2025-10-08 at 2 50 49 PM" src="https://github.com/user-attachments/assets/863ee8e9-46b9-4bff-8e56-fc29653334b3" />

- Peak hours are 8 a.m. and 5 p.m. with roughly 350 & 475 average hourly riders repectively
- Rindership increases before and decrease after theses points
- Ridership has a strong relation ship with people commuting to work
  
<img width="755" height="566" alt="Screenshot 2025-10-08 at 2 51 24 PM" src="https://github.com/user-attachments/assets/0e7103b3-171e-4abf-a80a-f8cec1419276" />

- Less clear weather correlates with lower average ridership
- Clear weather has >200 Average riders compared to heavy snow/rain with < 100
<img width="600" height="602" alt="Screenshot 2025-10-08 at 2 53 36 PM" src="https://github.com/user-attachments/assets/d7db07a9-ee45-4f1a-91f8-4d300c646d30" />

- Most riders are from registered users with 81.2% comapared to casual users making up the remaining 18.8%
- People who rode a bikes are likely to be repeat users so they register

---

### Hypothesis Testing
### Q1: Working vs. Non-Working Days
- Hypotheses:

Null hypothesis (H0): Mean hourly rides on working and non-working days are equal.

Alternative hypothesis (H1): Mean hourly rides on working and non-working days differ.

## 📊 Hypothesis Test Results

<img width="754" height="566" alt="Screenshot 2025-10-08 at 3 14 16 PM" src="https://github.com/user-attachments/assets/e931a467-931a-4e41-9dd7-eca3ef76ba3a" />


- **Test**:   Welch’s t-test
- **Result**: p-value = 0.00004
- **95% CI**:  (6.15, 17.45)
- **Decision**:  Reject null hypothesis!
- **Practical Insight**: There is a statistically and practically significant difference in hourly ride counts between working and non-working days. On average, working days see 6 to 17 more rides per hour, which can translate to hundreds of additional daily rides.
This pattern reflects likely commuter behavior and should guide weekday-focused operational planning and targeted pricing or promotional strategies.

### Q2: Seasonal Differences

Hypotheses:

Null hypothesis (H0): All seasonal means are equal (no difference in average hourly rides).

Alternative hypothesis (H1): At least one seasonal mean is different.

<img width="764" height="583" alt="Screenshot 2025-10-08 at 3 23 23 PM" src="https://github.com/user-attachments/assets/0b40132b-552a-4009-9b69-84d2903bb138" />

- **Test**: One-way ANOVA
- **Post-hoc**: TukeyHSD
- **Decision**: Reject the null hypothesis!
- **Insight**: Average hourly rides do significantly differ between at least some seasons.
The size of these differences with such a small p-value have clear operational, financial, and strategic implications for pricing, resource allocation, and customer engagement. making it not only statistically significant but practically significant aswell.

- The appropriate post-hoc approch would be a Tukey's HDS for pairwise comparisons between seasons to determine which specific pairs of seasons differ significantly. This would allow stakeholders to focus on seasons that may be underperforming.
---

### 🚴 A/B Test — Commuter Hour Ridership

**Objective:**  
Measure the impact of an app feature (launched on *2012-09-01*) on weekday evening (17:00–19:00) ridership during good weather.

**Eligibility Criteria:**  
- `workingday == 1`  
- `hr ∈ {17, 18, 19}`  
- `weathersit ∈ {1, 2}`  
- `hum ≤ 0.70`

**Windows:**  
- **Pre (Group A):** 2012-08-04 → 2012-08-31  
- **Post (Group B):** 2012-09-01 → 2012-09-28  

**Design:**  
Data was stratified by `(weekday × hour)` and matched by truncating to equal sample sizes across time slots. This ensured balanced groups and fair comparison.

**Balance Check**

<img width="411" height="312" alt="Screenshot 2025-10-08 at 6 58 55 PM" src="https://github.com/user-attachments/assets/a27ff19a-9677-48fb-844f-88595777e585" />


**Test:**  
- **Paired t-test**  
- **Null:** No difference in avg. hourly rides  
- **α = 0.05**

**Results:**  
- **p-value:** 0.0006  
- **95% CI:** [-63.6, -18.7]  
- **Mean Increase:** +41.15 rides/hour  
- **Cohen’s d:** 0.30 (small–medium)

✅ **Statistically and practically significant** (~15% lift).  
Suggests increased demand likely due to the feature — may warrant operational changes (e.g., staffing, fleet availability).


---

## ✅ Recommendations


### 👩‍💼 Product Manager
- **Invest in feature development that supports commuter behavior**
  - A/B test showed a **+41.15 rides/hour** increase after feature launch.
  - Prioritize features aimed at weekday evening rides (17:00–19:00)
- **Support the registered user base**
  - With ~81% of rides from registered users, optimize for retention (e.g., loyalty rewards, referrals)
- **Run additional experiments**
  - Continue controlled A/B testing to evaluate product changes over time

---

### 🛠️ Operations Lead
- **Prioritize commuter peak hours**
  - Focus staffing, bike rebalancing, and maintenance during 8 a.m. and 5 p.m. peaks.
- **Implement weather-based resource planning**
  - Clear weather = high demand; adjust fleet and station support accordingly
- **Plan for seasonal fluctuations**
  - Use seasonal trends to shift operational focus (e.g., more bikes in summer/fall)

---

### 📣 Marketing Lead
- **Target weekday commuters**
  - Use promotions and messaging during high-traffic windows (morning/evening)
- **Design seasonal campaigns**
  - Create special promotions in underperforming seasons identified via ANOVA results
- **Leverage weather**
  - Run weather-sensitive promotions

---

## ⚖️ Ethics & Limitations

### Limitations
- Doesn't include pricing model
- Dates only range from 2011 - 2012
- season date range is incorrect

### Ethics
- dont over prioitize peak hour commuters
- dont over prioritize registered users
---

## 📁 Files in This Repo
- `slides/`: presention with findings and insights.
- `data/`: Cleaned and raw datasets.
- `notebooks/`: Jupyter notebooks for EDA, testing, and modeling.
- `README.md`: Project overview and conclusions.
