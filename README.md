# Drone-Vibration-Analysis-on-Simulated-Data
A comprehensive project that simulates drone flights, collects vibrational data using smartphone sensors, filters the collected signals, and performs statistical analysis and visualization. The future goal is to build a dataset for training machine learning models to classify motor health, propeller condition, structural integrity, and stability.

---

## **Project Overview**  
This project focuses on simulating drone flights to capture and analyze gyroscopic vibrational data using smartphone sensors. The collected data is processed for further analysis, including statistical summaries and detailed visualizations. The future objective is to create a dataset for training machine learning models that can classify motor health, propeller condition, structural integrity, and stability.

---

## **Key Features**  
- **Data Collection:**  
  Vibration data collected during a drone's ascent using a smartphone accelerometer at a constant sampling rate of 200 Hz.  

- **Data Preprocessing:**  
  - Trimmed to the first 40 seconds of the ascent.  
  - Noise reduction using an averaging filter (moving average window of size 50).  

- **Statistical Analysis:**  
  - Computation of metrics such as mean, standard deviation, root mean square (RMS), and crest factor.  

- **Data Visualization:**  
  - Signal plots before and after filtering.  
  - Autocorrelation and rolling mean plots for trend analysis.  
  - Frequency spectrum and spectrogram analysis to identify dominant frequencies.  
  - Detection of low and high-frequency peaks.  

---

## **Data Filtering Process**  
1. **Averaging Filter:**  
   ```python
   df['Filtered Absolute acceleration (m/s^2)'] = df['Absolute acceleration (m/s^2)'].rolling(window=50).mean()
   ```  
   This filter reduces noise and stabilizes the signal for clearer analysis.  

2. **Frequency Spectrum Analysis:**  
   Using Welch's method to compare the power spectral density of original and filtered signals.  

---

## **Key Data Visualizations**  
- **Signal Comparison:**  
  Visualization of absolute acceleration before and after filtering.  
- **Autocorrelation:**  
  A plot showing repetitive signal patterns.  
- **Spectrogram:**  
  Visualization of frequency and intensity variations over time.  
- **Frequency Spectrum:**  
  Fourier transform to identify dominant frequencies in the signal.  

---

## **Statistical Summary**  
- **RMS Calculation:**  
   ```python
   rms = np.sqrt(np.mean(df['Absolute acceleration (m/s^2)'] ** 2))
   ```
   ![image](https://github.com/user-attachments/assets/20a2c207-fd7d-4391-bdae-efaa4dd348f8)

- **Crest Factor Calculation:**  
   ```python
   crest_factor = df['Absolute acceleration (m/s^2)'].max() / rms
   ```  
- Metrics such as mean, standard deviation, and crest factor were computed and plotted alongside time-series graphs for detailed trend insights.

---

## **Future Work and Motivation**  
The long-term objective is to develop a labeled dataset for training machine learning models that can:
- Classify motor health.
- Detect propeller issues.
- Evaluate structural integrity.
- Assess drone stability during flight.

This research aims to contribute to drone maintenance and performance monitoring systems.

---

## **Data Collection and Experimentation**  
The experiment followed a structured approach, including:
- Preparing and attaching the smartphone securely to the drone.
- Configuring a seismograph app to record vibrations during the flight.
- Ensuring environmental noise minimization during data collection.

Sample data characteristics:
- Sampling frequency: **200 Hz**
- Duration: **40 seconds of flight data**
  
---

## **Sample Output Plot**

A before-and-after filtering comparison plot of drone vibration data:
![image](https://github.com/user-attachments/assets/a4d91047-a8d4-45d8-b8c3-311a053b9dc1)

Autocorrelation of absolute acceleration:
![image](https://github.com/user-attachments/assets/5278df48-2510-477d-a161-153d07eb715d)

Freq spectrum before & after filtering:
![image](https://github.com/user-attachments/assets/a4c3ba58-172c-4cc4-8e2a-3718250a6c53)

Sampling Freq vs Sampling Time of filtered signal:
![image](https://github.com/user-attachments/assets/4090f6a3-c3b2-4250-a531-4038600c7060)

Spectrogram of Normalized Freq:
![image](https://github.com/user-attachments/assets/f66975b4-fbf9-405c-89a1-f3806b92ce5c)

Acceleration X,Y & Z with statistical markers:
![image](https://github.com/user-attachments/assets/639d0a1b-81de-4fa3-a57b-38a467f013be)
![image](https://github.com/user-attachments/assets/1517af36-9eda-434b-91ee-cb1c08e75ece)
![image](https://github.com/user-attachments/assets/a08f867c-199d-44b4-b6a6-fa80b0708415)

Unfiltered and filtered absolute acceleration:
![image](https://github.com/user-attachments/assets/b63d1d92-30d3-42de-ba36-08a11cc4f8ff)
![image](https://github.com/user-attachments/assets/a9fc1193-d1db-4c95-8de3-1d476bdf2698)

---
