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
- **Q2**: Seasonal ride differences → *ANOVA + Tukey HSD*

### Simulated A/B Test
- Feature launch impact on 17–19h commuter ridership.
- Stratified by weekday × hour × weather for control of confounders.

---

## 📈 Key Trends & Insights

1. **Seasonal Peaks:** Highest usage in Summer/Fall. Maintenance should be scheduled in Spring/Winter.
2. **Commuter Dominance:** 8–9 AM and 5–7 PM see sharp peaks—critical for operations and promotions.
3. **Weather Effects:** Clear/misty days with low humidity yield highest ridership. Avoid promos during bad weather.

---

## 📊 Hypothesis Test Results

### Q1: Working vs. Non-Working Days
- **Test**: Welch’s t-test, α = 0.05  
- **Result**: t ≈ 4.10, p = 0.00004  
- **95% CI**: [6.15, 17.45]  
- **Decision**: Reject H₀  
- **Practical Insight**: ~30 more rides/hour → staff accordingly.

### Q2: Seasonal Differences
- **Test**: One-way ANOVA, F ≈ 50, p < 0.001  
- **Post-hoc**: Tukey HSD shows Spring > Fall > Winter  
- **Decision**: Significant differences confirmed  
- **Insight**: Use in seasonal planning, promos, and ops scheduling.

---

## 🧪 Simulated A/B Test

- **Setup**: Pre (Aug 4–31) vs. Post (Sep 1–28)
- **Stratification**: Weekday × Hour × Weather
- **Result**: +44 rides (avg), p = 0.12 → *Not statistically significant*
- **Recommendation**: Expand test duration/sample size.

---

## ✅ Recommendations

(Use bullets here for PM, Ops, and Marketing — as shown above)

---

## ⚖️ Ethics & Limitations

### Limitations
- Observational data may include hidden confounders.
- Some statistical assumptions (normality, equal variance) may be weak.

### Ethics
- Risk of bias: commuting focus may neglect casual/weekend riders.
- Equity in service: Avoid systematic disadvantages in underserved areas.

---

## 📁 Files in This Repo
- `notebooks/`: Jupyter notebooks for EDA, testing, and modeling.
- `data/`: Cleaned and raw datasets.
- `figures/`: All visualizations used in analysis.
- `README.md`: Project overview and conclusions.
