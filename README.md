# DDoS Detection with Machine Learning

## Project Overview

This project compares three machine-learning classifiers with a packet-rate threshold baseline for detecting Distributed Denial-of-Service (DDoS) traffic.

The goal is to compare the approaches using three evaluation measures:

- **Precision:** How often traffic predicted as DDoS is actually DDoS.
- **Recall:** How much of the actual DDoS traffic is detected.
- **Inference time:** The time required to make a prediction for one network flow.

The project uses the CICIDS2017 network traffic dataset and evaluates the approaches on a held-out testing set.

## Project Files

- `ddos_detection.ipynb` — Contains the data preparation, model training, testing, and evaluation code.
- `README.md` — Provides project information and instructions for running and reproducing the experiment.

## Dataset

This project uses the `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv` file from the CICIDS2017 dataset, which can downloaded from the zip file in the data folder.

The notebook expects the dataset at:

`ddos-project/Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`

## How to Run the Project

The easiest way to run the project is with Google Colab.

1. Open [`ddos_detection.ipynb`](https://github.com/MoonlitTech/ddos-detection/blob/main/ddos_detection.ipynb) in the repository.
2. Open the notebook in Google Colab.
3. Obtain the dataset and make sure its path matches the notebook's expected location.
5. Select **Runtime → Run all**.
6. Wait for all tests to finish running.
7. Review the final results in the results folder.

## Data Preparation

The notebook prepares the data before training and testing the models.

The preparation steps include:

- Removing exact duplicate rows.
- Removing rows with invalid or non-finite `Flow Packets/s` values.
- Converting traffic labels into binary classes: DDoS (1) and non-DDoS (0).
- Handling missing numeric feature values through median imputation.
- Using a fixed random seed of 42.
- Splitting the usable flows into 70% training data and 30% testing data.

### Results Summary

The machine-learning classifiers achieved substantially higher precision than the threshold baseline.

Random Forest achieved the highest measured precision and recall, but it also had the slowest inference time among the three machine-learning models. Decision Tree achieved similar classification performance with lower measured inference time.

These findings apply to the dataset, data split, model settings, and computing environment used in this experiment. They do not guarantee the same performance on other datasets or live network traffic.

## Reproducibility Instructions

To reproduce the evaluation:

1. Obtain the same CICIDS2017 CSV file.
2. Use the specified dependency versions where possible.
3. Keep the random seed set to 42.
4. Use the documented model settings and training-only threshold selection.
5. Run the complete notebook.
6. Compare the resulting precision, recall, and inference-time measurements with the reported results.

Small differences in timing may occur because of hardware, system load, and runtime conditions. If classification results differ, verify the dataset version, data path, preprocessing steps, model settings, and library versions.

## Recorded Demo

**Demo video:** 

The demonstration explains the project goal, dataset, compared approaches, evaluation results, and reproducibility process.

## AI Assistance Disclosure

AI assistance was used minimally for cleanup and polishing of the project's testing and reproducibility materials. 

## Links
- Demo video: https://drive.google.com/file/d/1FjqhRyHQXnn6gpo_PqxiZEJ7jYuDzYvJ/view?usp=sharing 
- Paper: [file:///C:/Users/breew/Downloads/C365_ACM_Research_Paper%20(1).pdf](https://drive.google.com/file/d/1s3F2eZeA5qRBIhYcEvtJaTYfuaOH10FF/view?usp=sharing)
