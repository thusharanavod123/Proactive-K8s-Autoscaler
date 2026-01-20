
---# ML-DevOps Workload Predictor



This project implements a proactive auto-scaling framework using LSTM neural networks to predict Kubernetes workloads and optimize resource allocation.



1️⃣ GAP ANALYSIS

├── Systematic literature review (40+ papers)

├── Identify reactive vs proactive gaps

└── Confirm: No pre-deployment prediction frameworks



2️⃣ FRAMEWORK DESIGN

├── ML-Driven DevOps Architecture

├── Jenkins → ML Prediction → K8s Auto-scaling

└── Modules: Workload Predictor + Resource Optimizer



3️⃣ ML MODEL TRAINING

├── LSTM (time-series workload prediction)

├── Isolation Forest (anomaly detection)

├── Dataset: Google Cluster Data 2019 (2GB public)

└── Target: 85% accuracy, RMSE < 0.1



4️⃣ PROTOTYPE IMPLEMENTATION

├── Jenkins CI/CD pipeline with ML webhook

├── Minikube/Kubernetes deployment

├── AWS Free Tier EC2 hosting

├── Prometheus + Grafana monitoring

└── Auto-scaling trigger (predict → scale)



5️⃣ EVALUATION & TESTING

├── Locust load simulation (3 scenarios: normal/spike/crash)

├── Metrics: CPU utilization, cost/hour, response time

├── Baseline: Traditional K8s HPA (reactive)

└── Expected: 20-30% cost savings



6️⃣ ANALYSIS & DOCUMENTATION

├── Statistical analysis (t-test)

├── Graphs + results tables

├── Best practices guide

└── Limitations + future work

# 🚀 Stage 3: ML Model Training – Proactive K8s Autoscaling

This repository contains the core predictive engine for a proactive cloud autoscaling framework. Stage 3 focuses on developing a "Dual-Brain" machine learning system to forecast workload demands and detect system anomalies before they impact performance.

## 🎯 Research Goal

To move cloud operations from a **reactive** model (scaling only after CPU > 80%) to a **proactive** model by predicting workload spikes **60 minutes in advance**.

## 📊 Dataset Strategy

We utilize a hybrid data approach to ensure the model is both production-ready and agile.

| Dataset | Phase Usage | Purpose | Target |
| --- | --- | --- | --- |
| **Synthetic Data** | Initial Prototype | Rapid iteration and CI/CD pipeline reliability testing. | 100% "Green" runs |
| **Google Cluster 2019** | Production Model | Training on real-world production task usage patterns. | **RMSE < 0.1** |

## 🧠 Model Architectures

### 1. Workload Predictor (LSTM)

* **Purpose**: Forecasts future CPU/Memory usage based on historical trends.
* **Inputs**: Past 6 time-series data points (60 minutes of history).
* **Output**: Predicted CPU demand for the next interval.
* **Success Metric**: 85% Prediction Accuracy and RMSE < 0.1.

### 2. Anomaly Detector (Isolation Forest)

* **Purpose**: Identifies sudden, non-linear spikes and potential crash scenarios (Outliers).
* **Role**: Triggers "Self-Healing" alerts or emergency recovery procedures.

## 🛠️ Implementation Progress

* [x] **Data Preprocessing**: Normalized all CPU usage metrics to a [0, 1] range using `MinMaxScaler`.
* [x] **Initial Training (Synthetic)**: Successfully trained a prototype LSTM on 1,000 rows of synthetic data to validate the architecture.
* [ ] **Production Training (Google Cluster)**: Currently sampling 10,000 rows from the 2019 Google dataset to hit the 85% accuracy target.

## 📈 Expected Outcomes (Phase 5 Comparison)

Our testing aims to validate the following improvements over standard Reactive HPA:

* **Cost Savings**: 15% reduction during normal operations.
* **Downtime Reduction**: 25% faster scaling during sudden traffic spikes.
* **Recovery Speed**: 30% improvement in anomaly recovery times.

## 📂 Repository Structure

```text
├── data/
│   ├── synthetic_traffic.csv   # Fast-iteration test data
│   └── google_sample.csv      # Real-world production data (10k rows)
├── models/
│   ├── proactive_model_v1.h5   # Trained LSTM weights (Synthetic)
│   └── anomaly_detector.pkl   # Trained Isolation Forest (Prototype)
├── notebooks/
│   └── Stage3_Model_Training.ipynb  # Google Colab Training Script
└── README.md

```

## 📅 Timeline Status: **Day 4 of 4 (Intensive Execution)**

* **Today's Focus**: Finalizing ML accuracy benchmarks and exporting the `.h5` model for Stage 4 pipeline integration.

---

**Supervisor:** Prof. S. Vasanthapriyan | **Student:** H.M.T.N. Padiwela (20APSE4838)