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


---

## 📊 Hypothesis Test Results

### Q1: Working vs. Non-Working Days
- **Test**:   
- **Result**: 
- **95% CI**:  
- **Decision**:  
- **Practical Insight**: 

### Q2: Seasonal Differences
- **Test**: 
- **Post-hoc**: 
- **Decision**: 
- **Insight**: 
---

## 🧪 Simulated A/B Test

- **Setup**: Pre (Aug 4–31) vs. Post (Sep 1–28)
- **Stratification**: Weekday × Hour × Weather
- **Result**: 
- **Recommendation**: 

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
- `slides/`: presention with findings and insights.
- `data/`: Cleaned and raw datasets.
- `notebooks/`: Jupyter notebooks for EDA, testing, and modeling.
- `README.md`: Project overview and conclusions.
