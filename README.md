# 🧠 Analogy Detection in Network Logs

This project explores analogy detection from web or server logs using time-based feature engineering and behavioral profiling.

## 📁 Dataset

The dataset (`logs_dataset_final.csv`) consists of:
- `ip_address`: Identifier for network users or machines
- `@timestamp`: Timestamp of each access or event

## ⚙️ Workflow

### 1. Mount Google Drive
Mount Google Drive to access the dataset stored in Colab.

### 2. Preprocessing
- Convert timestamps to `datetime`
- Sort by IP and timestamp
- Create lag features like `time_diff` (in minutes)
- Extract time-based features: `date`, `hour`, `weekday`, `is_weekend`, `hour_bucket`

### 3. Feature Engineering
- `daily_counts`: Number of accesses per IP per day
- `median_daily_count`: Typical usage pattern
- `weekend_counts`: Analyze weekend vs weekday behavior
- Pivoted features for comparative analysis

### 4. Visualization & Insights
- Visualize usage patterns using `matplotlib`
- Group similar IPs based on extracted patterns
- Highlight behavioral analogies and potential anomalies

## 📈 Potential Extensions
- Use PCA or clustering to find analogous users/IPs
- Train ML models (e.g., isolation forest, KMeans) for anomaly/analogy detection
- Incorporate deep learning for time-series embeddings

## 📦 Requirements

- Python 3.7+
- pandas, numpy, matplotlib
- scikit-learn

## 📌 How to Run

```bash
# In Google Colab:
1. Mount your Google Drive
2. Upload or link the dataset to `/content/drive/MyDrive/`
3. Run the notebook cells sequentially
