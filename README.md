# ✈️ Customer Booking Prediction -  British Airways 
💡 **Predictive Modeling for Holiday Booking Completion**  
A machine learning project that anticipates whether a customer will complete a booking based on early behavioral indicators, helping British Airways enhance targeting, improve conversion, and optimize resources.

---

## 🌟 Project Highlights

### 🔍 Business Context  
With a shift to digital booking platforms, customers often explore flight options without immediate commitment. Predicting booking intent empowers British Airways to engage customers proactively and improve conversions.

This project uses historical booking data to:

- Forecast likelihood of booking completion
- Reveal behavioral and temporal patterns behind intent
- Guide retention and marketing efforts with machine learning

---

## 📂 Dataset Overview  

- **Size**: ~10,000+ rows  
- **Target Variable**: `booking_complete` (0 = Not Booked, 1 = Booked)  
- **Features**: Includes travel behavior, preferences, timing, and geographic information  

### 🗃 Key Features

| Feature | Description |
|--------|-------------|
| `purchase_lead` | Days between booking and flight |
| `length_of_stay` | Duration of trip |
| `sales_channel` | Internet, Call Center, etc. |
| `trip_type` | OneWay or RoundTrip |
| `flight_day`, `flight_hour` | Time of travel |
| `booking_origin`, `route` | Geographic attributes |
| `wants_extra_baggage`, `wants_in_flight_meals`, etc. | Travel preferences |

---

## 🧠 Machine Learning Pipeline

### 🔹 Preprocessing & Feature Engineering

- Extracted `origin` and `destination` from route  
- Derived features:
  - `is_weekend_flight`
  - `is_long_trip`
  - `lead_time_category` (binned `purchase_lead`)
- Encoded categorical variables using `LabelEncoder`

### 🔹 Exploratory Data Analysis (EDA)

- Clear **class imbalance** (~90% non-bookers)
- Influential features:
  - `purchase_lead`, `flight_hour`, `num_passengers`
  - Preferences like baggage and meals
- Behavior patterns differ across weekdays, channels

### 🔹 Modeling Techniques

- **Random Forest Classifier** (baseline model)  
- Metrics:
  - Accuracy
  - ROC-AUC
  - Classification report (Precision, Recall, F1-score)

---

## 🧪 Performance Summary  

| Metric | Value |
|--------|-------|
| Accuracy | **85.5%** |
| ROC-AUC | **0.77** |
| Recall (Booked class) | **~11%** |
| Precision (Booked class) | **~55%** |
| Confusion Matrix | TP: 170, FN: 1310, FP: 141, TN: 8379 |

> 🔎 The model performs well overall but struggles to recall customers who actually book due to **class imbalance**.

---

## 🛠 Improvements Implemented  

- 🧹 Feature engineering based on domain insights  
- 🔢 Label encoding of multiple categorical variables  
- 🔎 Visual analysis of booking behavior  
- 📊 Feature importance ranking via Random Forest

---

## 📈 Visual Insights

- Count plots and distributions by:
  - Sales channel, flight day, number of passengers
- Feature importance (e.g., `purchase_lead`, `sales_channel`)
- ROC curve and heatmaps for evaluation

---

## 💾 Model Artifacts

- `rf_model.pkl`: Trained Random Forest Classifier  
- `label_encoders.pkl`: Dictionary of encoders used for transformation  
- Models can be serialized using `pickle` or `joblib` for production

---

## 🚀 Deployment Options

This model can be deployed via:

- **Flask / FastAPI** for API integration with BA’s web platform  
- **Streamlit / Gradio** for interactive customer analytics dashboards  
- **CRM / Marketing Automation** tools for lead scoring & retargeting

---

## 📚 What I Learned

- Effectiveness of behavioral indicators in travel predictions  
- Impact of class imbalance on recall and how to address it  
- Visual storytelling through EDA to align ML with business needs  
- Feature engineering for domain-specific models (e.g., travel seasonality)

---

## ✅ Business Value

This model enables British Airways to:

- Detect potential bookers early in their journey  
- Optimize conversion-focused marketing strategies  
- Increase booking rates through personalized offers  
- Improve operational planning for customer load & staffing

---

## 💡 Recommendations

- ⚖️ **Address class imbalance** with SMOTE or class weights  
- 📊 **Track behavior metrics** (clicks, time spent, revisits) in future datasets  
- 🎯 **Use intent indicators** (baggage, lead time) for smarter targeting  
- 📆 **Monitor seasonality** and update the model periodically

--- 

## Acknowledgment

This project was completed as part of a **Data Science Internship / Job Simulation**, and I am sincerely grateful to **British Airways** for providing the dataset, business context, and the opportunity to work on such a meaningful problem.

Thank you for the opportunity to contribute, learn, and apply machine learning to a real-world airline booking scenario.

---

---

## ✍️ Author  
**[Your Name]**  
Data Science Enthusiast | Machine Learning Developer  
📧 [your.email@example.com]  
🌐 [LinkedIn](#) | [Portfolio](#)
