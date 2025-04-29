# Unsupervised Anomaly Detection on Semiconductor Manufacturing
---
Semiconductor manufacturing processes generate high-dimensional sensor data that can indicate equipment faults or process deviations. Labeling failures is costly and time-consuming; therefore, unsupervised methods that learn normal behavior and flag deviations are highly valuable. This project focuses on:

- Building a robust pipeline for raw sensor data ingestion and preprocessing.
- Comparing several unsupervised algorithms for anomaly detection.
- Selecting and tuning a final model that optimally balances recall on true failures and false-alarm rate.
- Packaging the solution into a deployable pipeline.

---
## ℹ️  Intro 
This repository implements an end-to-end unsupervised anomaly detection pipeline for semiconductor manufacturing sensor data (SECOM) using Python. The final model is an Isolation Forest trained on imputed sensor features, packaged as a deployable pipeline.

---

## 📁 Project Structure
```
project-root/
├── data/
│   ├── raw/
│   │   ├── incoming_secom.csv
│   │   ├── secom.data
│   │   └── secom_labels.data
│   └── processed/
├── models/
│   └── secom_iforest_pipeline.joblib
├── notebooks/
│   └── semi-manufacturing-anomaly.ipynb
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started
Follow these steps to set up your environment and run the analysis notebook.

### 1. Install Miniforge (Conda)
```bash
# macOS/Linux
eval "$(curl -fsSL https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh)"

# Windows (PowerShell)
winget install --id=conda-forge.Miniforge3
```

Restart your terminal after installation so that `conda` is available.

### 2. Create & Activate the Conda Environment
```bash
conda create -n secom python=3.9 -y
conda activate secom
```

### 3. Install Jupyter Notebook
```bash
conda install -c conda-forge notebook ipykernel -y
python -m ipykernel install --user --name secom --display-name "SECOM Env"
```

### 4. Install Python Dependencies
```bash
pip install -r requirements.txt
```

### 5. Launch the Notebook
```bash
jupyter notebook notebooks/semi-manufacturing-anomaly.ipynb
```

---

## 📦 Requirements
The `requirements.txt` includes:
```text
pandas>=1.3
numpy>=1.21
scipy>=1.7
scikit-learn>=1.0
joblib>=1.1
matplotlib>=3.4
notebook>=6.4
```

---

## 📖 Usage
1. **Data preparation:**
   - Download `secom.data` and `secom_labels.data` from the UCI repository into `data/raw/`.
2. **Notebook walkthrough:**
   - Follow the cells in `01_secom_anomaly.ipynb` (labeled Cell 1–Cell 19) to reproduce the analysis.
3. **Generate final reports:**
   - The PDF and PPTX can be generated via the `scripts/generate_report.py` script or manually by running the relevant Python cells.

---

## 📊 Outputs
- **Model pipeline:** `models/secom_iforest_pipeline.joblib`
- **Final report PDF:** `Final_Project_Report.pdf`
- **Presentation PPTX:** `SECOM_Anomaly_Detection_Presentation.pptx`

---

## 🚧 Future Work
- Improve recall using ensemble methods or temporal sliding-window detectors.
- Enhance interpretability with rule-based or sparse models.
- Integrate real-time scoring and alerting.

---

## 📜 License
None, all content for educational purpose :)

---
Author: ekulyyev
SJ @ 2025
