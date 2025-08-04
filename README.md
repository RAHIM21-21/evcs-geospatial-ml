# ⚡ Optimal EV Charging Station Placement in Italy  


This project applies **Big Data Engineering**, **Geospatial Analytics**, and **Machine Learning** to optimize the placement of Electric Vehicle Charging Stations (EVCS) across five key Italian cities. The initiative supports smarter infrastructure investment decisions, energy utilization forecasts, and sustainability goals.

---

## 🚀 Project Objective

To identify **high-potential locations** for new EV charging stations by:

- Estimating **monthly energy throughput** (kWh) per area.
- Profiling **charging behaviors** and client personas.
- Applying **predictive models** to optimize station placement and expected usage.

---

## 🧩 Challenge Breakdown

### 🎯 Business Goals

- **Client Profiling** – Segment customers based on charging behavior.
- **Demand Forecasting** – Predict energy throughput per location.
- **Site Recommendation** – Suggest optimal EVCS placement based on both usage potential and spatial dynamics.

---

## 📍 Target Locations

- **Rome** – High tourist influx and traffic complexity.  
- **Milan** – Italy’s economic engine and innovation hub.  
- **Turin** – Industrial city with strong mobility focus.  
- **Florence** – Tourism-driven EV behavior.  
- **Catania** – Emerging southern market with no current stations.

---

## 🗃️ Data Pipeline

### 🧪 Data Sources

- `cdr`, `pdr` – Charging session and point data  
- `hypercharge_sessions`, `hypercharge_locations` – Charging infrastructure usage  
- Public socio-economic and geographic datasets

### 🛠️ Data Engineering Steps

1. **Data Cleaning & Transformation**  
2. **Behavioral Feature Engineering**  
   - Frequency, duration, and timing of charges  
   - Energy per session  
   - Spending behavior  
3. **Grid Generation**  
   - Cities divided into polygon-based grids for spatial modeling

---

## 🧠 Modeling Strategy

### 🗂️ Charging Station Placement – Classification

**Goal**: Predict whether a location is suitable for an EVCS

| Model                        | Accuracy | Precision | Recall | F1-score | AUC  |
|-----------------------------|----------|-----------|--------|----------|------|
| Linear Discriminant Analysis| 0.96     | 0.73      | 0.71   | 0.72     | 0.71 |
| GaussianNB                  | 0.90     | 0.62      | 0.83   | 0.66     | 0.83 |
| QDA                         | 0.90     | 0.62      | 0.81   | 0.66     | 0.81 |
| Nearest Centroid            | 0.87     | 0.60      | 0.84   | 0.64     | 0.84 |

*Evaluation: 5-fold stratified cross-validation to address class imbalance*

---

### ⚡ EVCS Utilization – Regression

**Goal**: Predict energy consumption (kWh) per station per month

| Model               | Mean RMSE | Std. Dev |
|--------------------|-----------|-----------|
| Linear Regression   | **85.61**  | 15.87     |
| Gradient Boosting   | **92.41**  | 30.16     |
| Random Forest       | 82.88     | 25.02     |
| Ridge Regression    | 70.48     | 20.73     |
| Lasso Regression    | 68.67     | 21.73     |
| SVM                 | 64.99     | 23.41     |

---

## 📊 Key Insights

### ⏰ Charging Patterns

- Most users charge around **25% battery** level.
- Peak times: **9–11 AM** and **2–4 PM**
- Significant overnight charging between **6 PM – 12 AM**

### 👤 User Personas

- **Morning Commuters** → Office zones  
- **Midday Chargers** → Commercial/shopping areas  
- **Night Chargers** → Depot/fleet zones  
- **Quick Chargers** → High-traffic fast-charge stations  
- **Moderate Users** → Transit hubs  
- **Long-Distance** → Highway stations

---

## 📍 Best Locations Identified

| Location ID | Latitude   | Longitude  | Predicted Energy (kWh) |
|-------------|------------|------------|-------------------------|
| 15          | 43.5602    | 13.51086   | 447.91                  |
| 24          | 44.90774   | 8.63623    | 447.95                  |
| 51          | 45.56667   | 10         | 447.93                  |
| 54          | 44.7088    | 10.6252    | 447.94                  |
| 83          | 45.51667   | 12.18333   | 447.95                  |

---


## 🔧 Technologies Used

- **Big Data Processing**: Apache Spark  
- **Spatial Analysis**: Apache Sedona (GeoSpark)  
- **ML Frameworks**: Scikit-learn, XGBoost  
- **Visualization**: Seaborn, Matplotlib  
- **Data Storage**: Parquet files  
- **Geospatial Mapping**: OpenStreetMap

---

## 💡 Contributions & Limitations

### ✅ Contributions

- A reusable pipeline for **EVCS site selection** in any city
- Predictive insights for **energy consumption**
- Behavioral segmentation to **guide station type and power**

### ⚠️ Limitations

- Models trained on **historical data** – could be improved with forecast data  
- **Data imbalance** still presents minor bias despite stratified sampling

---


## 🙏 Acknowledgments

We extend our thanks to **Akansh Maurya**, **Cicy Kuriakose Agnes**, **Bahram Khan Baloch**, **Saira Sohail Anwari**, and **Umer Butt**, whose methodology in  
_“Spatial-Economic Analysis for Optimal Electric Vehicle Charging Station Placement” (SASI-ITE 2024)_  
provided a foundation for our modeling approach.

---

## 📂 Repository Structure

```bash
.
├── dataset/               # Socio-economic and charging session data
├── task_1/                # Data preparation & feature engineering
├── task_2/                # Classification models for placement
├── task_3/                # Regression models for energy prediction
├── maps/                  # Interactive maps and visualizations


