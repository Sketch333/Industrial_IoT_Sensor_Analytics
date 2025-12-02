This project explores a complete end-to-end workflow for multivariate time-series data collected from 100 industrial IoT devices. The dataset contains 20k records sampled every 30 seconds and includes temperature, humidity, vibration, pressure, light, gas, and anomaly labels.

The goal is to clean the data, understand device behavior, detect anomalies, forecast future values, and build a health scoring system.

Dataset

Sensors:
temperature, humidity, vibration, pressure, light, gas
Extra: anomaly label
Frequency: 30 seconds
Devices: 100
Total Rows: ~20,000

Project Tasks
1. Time-Series Cleaning

Validate timestamp frequency

Identify gaps >5 minutes

Rebuild missing timestamps

Impute missing values (linear, rolling median, EWM, etc.)

Output: missing-interval report + cleaned DataFrame

2. Noise Reduction & Decomposition

Savitzky–Golay for temperature

EMA for humidity

Wavelet denoising for vibration

Seasonal decomposition for all sensors

Output: before/after plots + performance notes

3. Device Behavior Profiling & Clustering

Per-device stats: mean, variance, quantiles, slopes, thresholds

Build device feature matrix

K-means with silhouette score

PCA visualization

Output: cluster assignments + 2D PCA plot

4. Rolling Windows & Advanced Features

1, 5, 10-minute rolling metrics: mean, std, skew, entropy, FFT energy

Local spike/drop detection

Output: rolling feature table + entropy plot

5. Correlation & Cross-Device Sync

Pearson/Spearman across sensors

Cross-correlation across devices

Identify synchronized units

Output: heatmaps + device relation insights

6. Anomaly Detection

Methods used:

Z-score / IQR

Isolation Forest

Local Outlier Factor

Gaussian Mixture

Outputs:

Anomaly labels, evaluation metrics, annotated plots

7. Sensor Health Scoring

Scores based on:

Stability

Missing data

Noise

Anomaly rate

Output: 0–100 health index + device ranking

8. Forecasting

Models:

ARIMA / SARIMA

Prophet

LSTM / GRU / TCN (optional)

Output: 24-hour temperature forecast + MAE/RMSE

9. Cross-Device Similarity Search

DTW similarity

Euclidean window-feature similarity

NetworkX similarity graph

Output: top-5 nearest neighbors per device

Tech Stack

Python, Pandas, NumPy, SciPy, Statsmodels, Scikit-Learn, PyWavelets, Matplotlib, Seaborn, NetworkX
