# Anomaly Detection and Predictive Analysis for API Response Times

## 1.Description
This project implements anomaly detection using Isolation Forest and Autoencoder, combined with LSTM-based time series forecasting to analyze API response times. The model enables real-time anomaly detection, proactive failure prediction, and performance optimization. Built with Python, Scikit-Learn, and TensorFlow, it ensures scalable and data-driven log analysis.

## 2. Features

### Anomaly Detection:
#### Isolation Forest:
- Uses a tree-based approach to isolate anomalies based on feature splits.
- Efficient for high-dimensional data with low computational cost.
- Detects anomalies based on their uniqueness in the dataset.
#### Autoencoder:
- Neural network-based anomaly detection using unsupervised learning.
- Learns compressed representations of normal data patterns.
- Identifies anomalies through high reconstruction error when input deviates from learned patterns.
### Predictive Analysis:

#### LSTM Model for Response Time Forecasting

- Utilizes a **Long Short-Term Memory (LSTM) network**, a specialized **Recurrent Neural Network (RNN)**, to model sequential dependencies in API response times.  
- Learns from **historical response time logs** to predict future latency trends with high accuracy.  
- Captures **seasonality, sudden spikes, and anomalies** in response behavior for better trend analysis.  
- Enables **proactive performance optimization**, aiding in **server scaling, request load balancing, and anomaly prevention**.  
- Supports **real-time decision-making** by identifying potential slowdowns before they impact system performance.

#### Real-time Monitoring

- Implements **continuous log analysis** to detect anomalies and predict trends dynamically.  
- Can be integrated with **real-time dashboards** for live system health monitoring.  
- Enables **quick response to system failures**, minimizing downtime and ensuring system reliability.  

#### Optimized Detection:

- Combines statistical (Isolation Forest), deep learning (Autoencoder), and sequential (LSTM) methods for robust anomaly detection.
- Hybrid approach improves accuracy by reducing false positives and capturing complex anomalies.
- Allows adaptive thresholding and dynamic anomaly detection based on evolving system behavior.
  
## 4. Installation & Execution  

### Prerequisites  
Ensure you have the following installed:  
- Python 3.8+  
- Jupyter Notebook or JupyterLab  
- Virtual Environment (optional but recommended)  

### Installation  
- Install the required Python libraries:  
```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow torch torchvision torchaudio jupyterlab
```
-clone the repo
```bash 
git clone https://github.com/parthmanekar25/HackOHire_ML_Model.git
```
- check for required path
## 4. Usage  

### 1. Data Preparation  
Ensure API logs are in **CSV format** with the following columns:  

- `timestamp` – Request timestamp  
- `method` – HTTP method (GET, POST, DELETE, etc.)  
- `endpoint` – API endpoint accessed  
- `status_code` – HTTP response status code (200, 404, 500, etc.)  
- `size` – Response size in bytes  
- `response_time` – Time taken to process the request (in ms)  

**Example Log Data (`synthetic_logs.csv`):**  
```csv
timestamp,method,endpoint,status_code,size,response_time
2025-01-01 00:11:13,DELETE,/usr,303,5027,130
2025-01-01 00:56:48,POST,/usr/login,304,5036,353
2025-01-01 00:26:13,GET,/usr/admin/developer,403,5006,8126
```
### 2. Running Anomaly Detection  
To detect anomalies in API logs using **Isolation Forest** and **Autoencoder**, run:  

```bash
python API_Anomaly_Detection_Unsupervised.ipynb
```
### 3. Running LSTM forecasting for response time
to predict anamalies and failure in api calls using response call timestamps and also forecast it

```bash
python Predictive_api_response_spike.ipynb
```
## 5. Result
The anomaly detection study yields outstanding results, effectively analyzing 1000 response time entries (response_time_ms) across hours (hour) using Autoencoder, Isolation Forest, and One-Class SVM methods. Visualizations brilliantly showcase most response times between 80 and 120 ms, with anomalies at 40 ms or 160 ms, demonstrating clear and actionable insights. The Isolation Forest method stands out as a stellar performer, precisely identifying the most relevant anomalies with exceptional accuracy, proving its immense value for real-world applications. Data tables further highlight this success, with a sample Isolation Forest entry of 131.584256 ms at hour 17 labeled "Normal" (score: 0.112814) and a One-Class SVM entry of 107.869708 ms at hour 5 also labeled "Normal" (score: 0.000181), reflecting robust detection capabilities. Future enhancements promise even greater potential, with plans to integrate advanced techniques such as status code analysis for deeper system insights, large language model (LLM) integration for contextual anomaly interpretation, transformer models for enhanced pattern recognition, and deep learning architectures to further improve accuracy and scalability, paving the way for groundbreaking advancements in anomaly detection.
