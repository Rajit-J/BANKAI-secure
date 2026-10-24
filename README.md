# BankAI Secure

A local Flask prototype for exploring how a banking customer-service assistant can classify requests and route them to safe, mock workflows. It uses a TF-IDF and Logistic Regression intent classifier trained on a small synthetic dataset.

## What it demonstrates

- Seven example banking-support intents, with the predicted intent and confidence.
- Mock balance, transaction, and policy responses.
- A separate authorization boundary for sensitive actions. Transfers are not executed.
- Security-aware request handling and model evaluation views.

This is an academic demonstration, not a banking product. It has no real banking credentials, customer records, banking APIs, or transaction execution.

## Technology

- Python and Flask
- scikit-learn, TF-IDF, and Logistic Regression
- pandas, NumPy, joblib, and Matplotlib

## Run locally on Windows

Install Python 3.12 or a compatible Python version supported by `requirements.txt`. In PowerShell, from the repository root:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m flask --app app run --host 127.0.0.1 --port 5101
```

Open [http://127.0.0.1:5101](http://127.0.0.1:5101). Stop the server with **Ctrl+C** and leave the virtual environment with `deactivate`.

The included model is already trained. To retrain it using the project dataset:

```powershell
python train_model.py
```

## Data and limitations

The training examples and responses are synthetic/mock. The reported evaluation is based on a small test split and should not be interpreted as production performance or financial advice. Model predictions do not authorize actions.

## Before publishing

Exclude virtual environments, caches, and local logs. Confirm that included model/data assets are project-owned. No license is included; add one only after confirming ownership and license terms.
