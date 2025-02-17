# Protein-Drug Affinity Prediction

## Overview

This project investigates the use of **K-Nearest Neighbors (KNN) regression** for predicting **affinities** between proteins and drug molecules. The goal is to assist in the identification of small organic compounds that strongly bind to specific proteins and could serve as drug candidates.

## Problem Statement

A scientist has conducted **400 laboratory measurements** of affinities between **77 proteins** and **59 drug molecules**. They trained a **KNN regressor (K=10)** using this data and estimated generalization performance with **leave-one-out cross-validation (LOO-CV)**, obtaining a high **C-index (~90%)**. However, real-world validation of top predictions revealed significantly lower affinities, indicating a **flawed estimation method**.

## Objective

- Investigate **why the leave-one-out cross-validation (LOO-CV) failed**.
- Implement a **corrected LOO-CV strategy**.
- Evaluate whether the current model is **suitable for prioritizing new drug-protein pairs**.

## Data Description

The dataset consists of three files:

- **input.data**: Contains the **features** of the protein-drug pairs.
- **output.data**: Contains the **measured affinities**.
- **pairs.data**: Contains the **identifiers** of the drug and protein molecules.

Each row in these files corresponds to the same protein-drug pair.

## Methodology

1. **Analyze the problem in the original leave-one-out cross-validation (LOO-CV)**  
   - Identify potential **data leakage** or **bias** in the estimation process.

2. **Implement a Corrected Leave-One-Out Cross-Validation Strategy**  
   - Ensure that when leaving out a sample, all pairs **containing the same protein or drug molecule** are excluded from training.

3. **Re-evaluate Model Performance**  
   - Compute the corrected **C-index**.
   - Compare results to the original estimate.
   - Assess whether the model is **useful for future predictions**.

## Requirements

- Python 3.x
- Jupyter Notebook
- NumPy, Pandas, Scikit-Learn

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/junaidraz1/leave-one-out-validation.git
