# Entertainment Video Title Generator using LSTM

This project demonstrates how to build a text generation model using an LSTM network in TensorFlow/Keras. It leverages YouTube video data from multiple regions and focuses on generating new entertainment video titles based on existing patterns.

## Overview

### Data Loading
- The project loads video data from CSV files (`USvideos.csv`, `CAvideos.csv`, `GBvideos.csv`) and their corresponding category mappings from JSON files (`US_category_id.json`, `CA_category_id.json`, `GB_category_id.json`).

### Data Preparation
- Extracts category names from JSON files and maps them to the video datasets.
- Concatenates data from different regions and removes duplicate videos.
- Filters the dataset to include only videos from the "Entertainment" category.
- Cleans video titles by removing punctuation and converting text to lowercase.

### Sequence Generation
- Tokenizes the cleaned text using Keras' `Tokenizer`.
- Creates n-gram sequences from each title.
- Pads the sequences to ensure uniform input length for the LSTM model.

### Model Building and Training
- Builds an LSTM model with an Embedding layer, LSTM layer, Dropout, and Dense output layer with softmax activation.
- Compiles the model using `sparse_categorical_crossentropy` as the loss function and `adam` as the optimizer.
- Trains the model for 20 epochs on the prepared sequences.

### Text Generation
- A helper function (`generate_text`) is provided to generate new video titles from a given seed word (e.g., "SpiderMan") by predicting subsequent words.

## How to Run

1. **Prepare the Data:**  
   Ensure that the CSV and JSON files are in the same directory as your script.

2. **Install Dependencies:**  
   Install the required packages using:
   ```bash
   pip install tensorflow pandas numpy
   ```
3. **Run the script with:**
   ```bash
   python your_script.py
   ```
