# Intelligent Link Quality Prediction

**Machine Learning-Based Wireless Link Quality Prediction and Remaining Communication Range Estimation Using ESP-NOW and LoRa**

## Project Overview

This research project focuses on developing an intelligent wireless communication prediction system using Machine Learning (ML).

The system aims to predict wireless link reliability and estimate the remaining reliable communication range using real-world communication data collected from a hybrid ESP-NOW and LoRa communication system.

Unlike traditional fixed-distance threshold approaches, the proposed system aims to learn communication patterns from historical signal measurements, transmission outcomes, and distance information.

## Project Objectives

- Develop a machine learning model to predict wireless link reliability.
- Classify predicted link quality into **HIGH, MEDIUM, and LOW** categories.
- Estimate the remaining reliable communication range in meters, with appropriate uncertainty.
- Analyze the relationship between distance, signal strength, signal-to-noise ratio, and communication success.
- Evaluate model performance using independent communication trials.
- Support intelligent communication monitoring in hybrid ESP-NOW and LoRa systems.

## Communication Technologies

| Technology | Description |
|---|---|
| ESP-NOW | Short-range wireless communication using ESP32 devices |
| LoRa | Long-range wireless communication using SX1278 modules |
| ESP32-S3 | Microcontroller used for the communication prototype |
| GPS | Provides location information for distance estimation |
| Machine Learning | Learns historical communication patterns to predict link reliability |

## Dataset Information

The project uses real-world communication data collected from ESP32-S3 devices during multiple experimental trials.

| Dataset Property | Details |
|---|---|
| Dataset | Sea Guardian Communication Dataset |
| Trial Range | T003–T020 |
| Total Records | 2,982 |
| Total Features/Columns | 34 |
| Communication Result Records | 1,174 |
| ESP-NOW Confirmed ACKs | 152 |
| LoRa Confirmed ACKs | 810 |
| No Confirmed ACK | 212 |
| Dataset Format | CSV |

The dataset includes communication events, GPS-based distance information, RSSI, SNR, ACK results, and other system measurements.

**Data integrity:** Original measurements are preserved. Data cleaning and feature engineering are performed separately without modifying the original source files.

**Important:** A missing ACK does not necessarily prove that the original message was not received. Environmental obstacle categories are not separately recorded in the current dataset.

## Machine Learning Development Workflow

1. Dataset Integration and Validation
2. Exploratory Data Analysis (EDA)
3. Data Quality Assessment and Cleaning
4. Target Definition and Label Preparation
5. Trial-Based Train, Validation, and Test Splitting
6. Historical Feature Engineering
7. Feature Selection and Preprocessing
8. Baseline Model Training
9. Hyperparameter Optimization
10. Model Evaluation and Probability Calibration
11. Link Quality Classification
12. Remaining Communication Range Estimation
13. Final Prediction System Integration

To reduce data leakage, evaluation will use trial-based splits rather than randomly distributing closely related communication measurements across training and testing sets.

Features will use information available before a transmission outcome, including historical RSSI, SNR, and ACK measurements where available.

## Expected System Outputs

### 1. Link Quality Prediction

The proposed system will classify predicted communication quality into:

- **HIGH** — High predicted communication reliability
- **MEDIUM** — Moderate predicted communication reliability
- **LOW** — Low predicted communication reliability

The categories will be derived from model-based reliability estimates rather than fixed distance rules alone.

### 2. Remaining Communication Range Estimation

The system will aim to estimate the remaining reliable communication distance based on observed communication history and current available measurements.

Range estimates will be treated as uncertain predictions, not guaranteed maximum transmission distances.

## Tools and Technologies

- Python
- Google Colab
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Git and GitHub
- ESP-NOW and LoRa communication technologies

## Project Status

**Status: In Development**

- [x] Real-world communication data collection
- [x] Dataset integration and chronological validation
- [ ] Exploratory Data Analysis
- [ ] Data Cleaning and Feature Engineering
- [ ] Train / Validation / Test Splitting
- [ ] Machine Learning Model Training
- [ ] Hyperparameter Tuning
- [ ] Model Evaluation
- [ ] Link Quality Prediction Implementation
- [ ] Remaining Range Estimation
- [ ] Final System Integration

## Research Considerations

The model will be evaluated using data from unseen trials wherever possible.

Special attention will be given to:

- Missing and outdated GPS measurements
- Imbalanced communication outcomes
- Historical feature availability
- Prevention of target leakage
- Generalization across different test sessions
- Prediction uncertainty and limited environmental information

## Future Improvements

- Additional evaluation under varied environmental conditions
- Improved radio-specific reliability prediction
- Real-time link quality monitoring
- Integration with a live communication dashboard
- Validation of remaining range estimates in new communication trials

---

**Project Type:** Machine Learning Research Project

**Research Area:** Wireless Communication, IoT, Machine Learning

**Development Environment:** Google Colab / Python

**Current Phase:** Dataset Preparation and Exploratory Data Analysis
