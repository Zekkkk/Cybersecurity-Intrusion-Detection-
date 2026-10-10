# Network Intrusion Detection

A Python and Jupyter Notebook project that uses the NSL-KDD dataset to classify network connections as normal traffic or attacks.

## Project

The notebook walks through data preparation, exploratory visualization, and training and evaluation of Decision Tree and Random Forest classifiers. It also examines Random Forest feature importance and demonstrates a sample prediction.

The detailed project description and reported results are in the [project README](cybersecurity-intrusion-detection/README.md).

## Run the notebook

From the repository root:

```bash
cd cybersecurity-intrusion-detection
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab notebooks/intrusiondetection.ipynb
```

The notebook and NSL-KDD data files are in [`cybersecurity-intrusion-detection/`](cybersecurity-intrusion-detection/).
