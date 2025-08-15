# Protein 2D Structure Prediction Using Deep Learning

Predict per-residue secondary structure (H = helix, C = coil, B = beta) from amino-acid sequence using a Conv1D deep neural network. The project includes data preprocessing from FASTA and `.ss2` files, model training, evaluation, and automatically generated visualizations: loss and accuracy curves, a confusion matrix, and animated GIFs of weight dynamics for each Conv1D layer.

---

## Contents

1. [Project structure](#project-structure)  
2. [Requirements](#requirements)  
3. [Data format](#data-format)  
4. [Quick start](#quick-start)  
5. [Scripts](#scripts)  
6. [Visualizations and outputs](#visualizations-and-outputs)  
7. [Reproduce the full pipeline](#reproduce-the-full-pipeline)  
8. [Troubleshooting](#troubleshooting)  
9. [License](#license)

---

## Project structure

protein-2d-structure/
├─ data/
│ ├─ raw/ # FASTA + .ss2 inputs (not committed)
│ └─ processed/ # Optional: cached numpy arrays
├─ outputs/
│ ├─ figures/ # loss.png, accuracy.png, confusion_matrix.png
│ ├─ metrics/ # history.csv, classification_report.txt
│ ├─ models/ # protein_cnn.h5
│ └─ weights_viz/ # GIFs and PNG frames per Conv1D layer
├─ src/
│ ├─ preprocess.py # Load FASTA + SS2, encode, save arrays
│ ├─ train.py # Build model, train, save model and plots
│ ├─ evaluate.py # Test set evaluation, confusion matrix, report
│ └─ callbacks.py # Conv1DFilterLinesCallback for weight GIFs
├─ sequences.fasta # Example FASTA (place your file here or in data/raw/)
├─ requirements.txt
├─ README.md
└─ .gitignore
