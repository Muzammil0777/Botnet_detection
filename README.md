
# 🔐 Botnet Traffic Detection using Machine Learning (LightGBM)

This project implements a machine learning-based system to detect botnet traffic using behavioral features extracted from network sessions. Built with **LightGBM** for classification and **Streamlit** for an interactive user interface, this system offers real-time prediction, explainability, and actionable security insights.

## 🚀 Features

- ✅ Trained on a synthetic dataset reflecting real-world network behavior
- ⚡ Utilizes LightGBM for efficient and scalable model training
- 📊 ROC Curve, Confusion Matrix, and AUC score visualizations
- 🔍 SHAP-based feature explanation for model transparency
- 🛡️ Security recommendations based on prediction results
- 📝 Logs all predictions with timestamp into `predictions_log.csv`

## 📁 Project Structure

```
.
├── app.py                     # Streamlit web app
├── train_model.py             # Model training script (LightGBM)
├── evaluate_model.py          # ROC and feature importance visualizations
├── enhanced_botnet_dataset.csv  # Expanded synthetic dataset
├── model.pkl                  # Trained LightGBM model
├── scaler.pkl                 # Fitted StandardScaler
├── predictions_log.csv        # Logged predictions (app runtime)
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

## 📦 Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/botnet-detection-lightgbm.git
cd botnet-detection-lightgbm
```

2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run the Streamlit app:

```bash
streamlit run app.py
```

## 🧪 Sample Test Inputs

Try inputting values such as:

```text
login_Attempts: 2
failed_Validations: 1
avg_flow: 550
current_flow: 545
packets_flow: 3
```

Or for suspicious activity:

```text
login_Attempts: 7
failed_Validations: 8
avg_flow: 550
current_flow: 950
packets_flow: 10
```

## 📈 Model Performance

| Metric     | Value  |
|------------|--------|
| Accuracy   | 0.60   |
| AUC        | 0.64   |
| Precision  | 0.62   |
| Recall     | 0.51   |

## 🔍 Explainability with SHAP

SHAP values are used to provide per-feature contribution analysis for each prediction, helping users and analysts understand **why** a session was classified as malicious or normal.

## 🔐 Security Recommendations

The app provides automated tips based on classification:

- Enable Firewalls and Intrusion Prevention Systems (IPS)
- Use Multi-Factor Authentication (MFA)
- Apply rate-limiting and anomaly detection policies
- Monitor login attempts and flow sizes regularly

## 🧠 Future Work

- Real-time packet sniffing and detection
- Integration with live APIs or SIEM tools
- Deployment via Docker and CI/CD pipelines
- Adversarial testing for improved robustness

## 📄 License

This project is licensed under the MIT License – free to use and modify.

---

**Developed using LightGBM, SHAP, and Streamlit – with a focus on secure and explainable ML.**
