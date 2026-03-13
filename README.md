# Bitcoin Price Analysis

A machine learning project for analyzing and predicting Bitcoin (BTC/USDT) price movements using Recurrent Neural Networks (RNNs).

## Overview

This project explores whether historical Bitcoin price data contains exploitable predictive signals. It employs **Recurrent Neural Networks (RNNs)** with an autoregressive multi-step approach that simulates real-world trading conditions, where models must rely on their own prior predictions rather than actual observed values.

## Features

- **Exploratory Data Analysis (EDA)** - Statistical analysis and visualization of Bitcoin price data
- **Multi-step Time Series Prediction** - RNN-based models for forecasting future prices
- **Autoregressive Prediction** - Models that predict using their own previous outputs
- **MLflow Integration** - Experiment tracking and model management
- **Interactive Dashboards** - Plotly/Dash visualizations for model results

## Project Structure

```
bitcoin_price_analysis/
├── data/
│   ├── dataset/          # Raw BTC/USDT hourly data
│   └── 2026_01_15/       # Processed data snapshots
├── version_english/      # English notebooks and documentation
├── version_français/     # French notebooks and documentation
├── mlruns/               # MLflow experiment tracking data
├── requirements.txt      # Python dependencies
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.10+
- pip

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd bitcoin_price_analysis
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # Windows
   # or
   source .venv/bin/activate  # Unix/macOS
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Install ipykernel for Jupyter notebook support:
   ```bash
   python -m ipykernel install --user --name=bitcoin_price_analysis --display-name "Python (bitcoin_price_analysis)"
   ```

### Usage

1. **Exploratory Data Analysis**: Open `version_english/EDA.ipynb` in Jupyter Notebook
2. **ML Modeling**: Open `version_english/ML modelization.ipynb` in Jupyter Notebook
3. **View MLflow Results**:
   ```bash
   # Start the MLflow tracking server
   mlflow ui --host 127.0.0.1 --port 5000
   ```
   Then open your browser at `http://localhost:5000` to access the MLflow UI and view experiments, metrics, and model artifacts.

4. **Launch Prediction Dashboard**:
   Run the dashboard server from the ML modeling notebook:
   ```bash
   python -c "exec(open('version_english/ML modelization.ipynb').read().split('if __name__')[0])"
   ```
   Or run the notebook and execute the final cell to start the Dash server. Then open your browser at `http://127.0.0.1:8050/` to view interactive prediction curves and grid analysis.

## Data

The project uses hourly BTC/USDT price data from Binance:

- **File**: `data/dataset/BTCUSDT_1h.csv`
- **Format**: CSV with OHLCV (Open, High, Low, Close, Volume) data

## Machine Learning Approach

### Model Architecture

- **Type**: Recurrent Neural Networks (RNNs)
- **Strategy**: Autoregressive multi-step prediction
- **Constraint**: Models use only their own prior predictions for future estimates

### Key Metrics

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- R² Score
- Root Mean Squared Error (RMSE)

## Documentation

| Document | Description |
|----------|-------------|
| Article 1 - Project Introduction | Overview of project goals and methodology |
| Article 4 - A New Direction | Evolution of the research approach |

## Tech Stack

- **Python** - Core programming language
- **TensorFlow/Keras** - Deep learning framework
- **scikit-learn** - Machine learning utilities
- **MLflow** - Experiment tracking
- **Plotly/Dash** - Interactive visualizations
- **Pandas/NumPy** - Data manipulation
- **Jupyter** - Interactive development

## Notebooks

- **EDA.ipynb** - Exploratory Data Analysis
- **ML modelization.ipynb** - Model training and evaluation

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is for research and educational purposes.

## ⚠️ Disclaimer

This project is for **educational and research purposes only**. It is not intended for live trading or financial advice. Cryptocurrency trading involves significant risk of loss.

---

*Last updated: March 2026*
