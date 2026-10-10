# Network Intrusion Detection Using Data Mining

This project applies data mining techniques to a cybersecurity business problem: detecting malicious network traffic before it can damage company systems. The goal is to classify network connections as either normal traffic or attack traffic.

The project is implemented in Python with a Jupyter Notebook and uses the NSL-KDD dataset.

## Business Need

Companies receive large amounts of network traffic every day. Security teams need automated tools that can help identify attacks quickly, reduce manual investigation time, and prioritize suspicious traffic. This project demonstrates how classification can support intrusion detection by learning patterns from historical network connection data.

## Dataset

The dataset used is NSL-KDD, a cleaned version of the KDD intrusion detection dataset.

- Training file: `data/KDDTrain+.txt`
- Testing file: `data/KDDTest+.txt`
- Training records: `125,973`
- Testing records: `22,544`
- Features: network connection attributes such as protocol type, service, flag, source bytes, destination bytes, login status, error rates, and host traffic statistics
- Target: original attack labels are converted into a binary class
  - `0` = normal traffic
  - `1` = attack traffic

## Data Mining Task

This project focuses on **Classification**.

Classification is appropriate for this project because the dataset contains labeled examples of normal and attack traffic. The models learn from these labeled records and predict whether new network connections are normal or malicious.

## Methods Used

1. Load the NSL-KDD train and test files.
2. Convert the original attack labels into a binary target.
3. Visualize the normal vs attack class distribution.
4. Remove non-feature columns from the model input.
5. One-hot encode categorical columns: `protocol_type`, `service`, and `flag`.
6. Train and evaluate a Decision Tree classifier.
7. Train and evaluate a Random Forest classifier.
8. Analyze the most important Random Forest features.
9. Demonstrate a sample prediction on one test record.

## Results Summary

| Method | Data Mining Task | Accuracy | Notes |
| --- | --- | ---: | --- |
| Decision Tree | Classification | ~78.5% | Simple model that learns decision rules from the traffic data. |
| Random Forest | Classification | ~76.6% | Comparison model that also provides feature importance. |

For intrusion detection, attack recall is especially important because missed attacks can create security risk. A model with high attack recall is useful because it catches more malicious traffic, even if some normal traffic is also flagged for review.

## Visualizations

The notebook includes:

- Normal vs attack class distribution
- Decision Tree confusion matrix
- Random Forest confusion matrix
- Random Forest feature importance chart

## Demo

The notebook itself is the demo. It shows the full workflow from loading the data to training models, evaluating results, visualizing performance, and predicting whether a sample network connection is normal or an attack.

Open:

```text
notebooks/intrusiondetection.ipynb
```

## How To Run

From the `cybersecurity-intrusion-detection` folder:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab notebooks/intrusiondetection.ipynb
```

Alternatively, start Jupyter Lab and open:

```text
jupyter lab
```

Notes:

- If Jupyter prints a `localhost` link with a token, open that full link in your browser.

## Tools And Libraries

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
