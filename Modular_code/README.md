# Credit Card Fraud Detection

This folder contains the modular implementation of a credit card fraud detection pipeline using Isolation Forest and Local Outlier Factor (LOF).

## Project Structure

- `input/`
  - `config.yaml` - configuration file that defines dataset and model output paths.
  - `credit_card_transactional_data.csv` - transaction dataset used for training and analysis.
- `output/`
  - output directory for saved models and generated artifacts.
- `src/`
  - `engine.py` - main entrypoint for reading config, preprocessing data, training models, predicting scores, and saving models.
  - `requirements.txt` - Python dependencies for this modular code.
  - `ml_pipeline/`
    - `utils.py` - utility functions for reading data, loading config, and computing contamination.
    - `preprocessing.py` - data preprocessing functions such as null handling.
    - `model.py` - model training, prediction, and saving functions for Isolation Forest and LOF.
- `lib/`
  - notebook and exploratory analysis files.

## Setup

1. Install a Python environment (recommended Python 3.8+).
2. From the repository root, install dependencies:

```bash
pip install -r Modular_code/src/requirements.txt
```

## Configuration

`Modular_code/input/config.yaml` includes:

```yaml
model_path: ../output
data_path: ../input/credit_card_transactional_data.csv
```

The config file uses relative paths from the repository root when running `engine.py`.

## Usage

From the repository root (`credit-card-copy`), run:

```bash
python Modular_code/src/engine.py
```

This will:
- load configuration from `Modular_code/input/config.yaml`
- read the transaction dataset
- handle missing values
- compute contamination score for the `Class` target
- train an Isolation Forest model
- compute and save anomaly scores
- train a LOF model
- save both models to the configured output path

## Notes

- Ensure the `output/` directory exists and is writable.
- The engine expects the dataset path configured in `input/config.yaml` to match the actual dataset location.
- Use the notebooks under `lib/` for exploratory analysis and model visualization.

## Contact

For questions or improvements, update the modular pipeline code under `Modular_code/src` and adjust the config paths as needed.
