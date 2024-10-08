# Indian Names Language Modelling using Character-level Models

This project is the implementation of **Language Modelling**. The goal is to model Indian first names using different character-level language models. The models include Feedforward Neural Networks (FNN) and Recurrent Neural Networks (RNN), both of which are trained to generate Indian first names based on character sequences.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architectures](#model-architectures)
- [Training Process](#training-process)
- [Evaluation](#evaluation)
- [How to Run](#how-to-run)
- [Files](#files)

## Introduction

This assignment aims to implement language models for generating Indian first names. The models are trained at the character level to predict the next character in a sequence, eventually generating entire names. The assignment uses two primary models:

1. **Feedforward Neural Networks (FNN)**
2. **Recurrent Neural Networks (RNN)**

## Dataset

The dataset used for training consists of a list of Indian first names, broken down into individual characters. The models are trained to predict the next character given a sequence of characters.

- **Input:** Sequences of characters from Indian names.
- **Output:** Predicted next character in the sequence, enabling the model to generate entire names.

## Model Architectures

### 1. Feedforward Neural Network (FNN)

The FNN model is a simple neural network that takes a sequence of characters as input, flattens it, and predicts the next character in the sequence. It consists of fully connected layers with activation functions to process the input.

- **Architecture:**
  - Input Layer: Character sequence (one-hot encoded or embedded)
  - Fully Connected Layers: Process the flattened input
  - Output Layer: Predicts the next character

### 2. Recurrent Neural Network (RNN)

The RNN model is designed for sequence data and processes one character at a time while maintaining a hidden state. It is more suited to modeling sequences like names since it can retain information about previously seen characters.

- **Architecture:**
  - RNN Layer: Processes sequences of characters one at a time
  - Hidden State: Maintains context across time steps in the sequence
  - Output Layer: Predicts the next character

## Training Process

The models are trained using a **character-level language modeling approach**. The training process involves:

1. Splitting the names into character sequences.
2. Feeding the sequences into the model.
3. Predicting the next character.
4. Computing the loss between the predicted and actual characters.
5. Updating the model using backpropagation.

## Evaluation

The model is evaluated using an automated process where specific print statements (`EVALUATION`) are used to generate results. The evaluation includes:

- **Accuracy:** Measures how often the model predicts the correct next character.
- **Loss:** Measures the difference between the predicted and actual characters.

You can monitor the evaluation metrics to determine the effectiveness of the FNN and RNN models.

## Results

### 1. **1-Gram Model**
   - **Validation Perplexity (without smoothing):** 13.6315
   - **Validation Perplexity (with smoothing):** 13.6321
   - **Generated Names:**
     - Prefix: `<s><s>sh`
     - Names: `peaenm</s>ccdji)nghlgar, <s>jhm)jye,uidf&ya</s>r&&, (slyulpfltrru0,l</s>b&a, skkt</s>chi,rim,aauo<s>i</s>, 0o,yap,g0&cftdiom</s>m0`
   
### 2. **2-Gram Model**
   - **Validation Perplexity (without smoothing):** 5.5944
   - **Validation Perplexity (with smoothing):** 6.0882
   - **Generated Names:**
     - Prefix: `<s><s>sh`
     - Names: `ha, ha, ha, ha, ha`

### 3. **3-Gram Model**
   - **Validation Perplexity (with smoothing):** 4.6436
   - **Generated Names:**
     - Prefix: `<s><s>sh`
     - Names: `shnanashal, shlanka, shish, sh, sheesakharadha`

### 4. **Feedforward Neural Network (FNN)**
   - **Validation Perplexity:** 7.3570
   - **Generated Names:**
     - Prefix: `<s><s>sh`
     - Names: `<s><s>shmtmdsfnmrmbjpcjm, <s><s>shbnmnahaskjaansks, <s><s>shykdbfayjansfmrsd, <s><s>shksmmlnrdspsmrsmf, <s><s>shkaspkbtasmsssjan`
   - **Generated Names (Prefix: `aash`):**
     - `aashb, aashdss, aashi, aashk, aashljmnr`

### 5. **Recurrent Neural Network (RNN)**
   - **Validation Perplexity:** 13.4957
   - **Generated Names:**
     - Prefix: `<s><s>sh`
     - Names: `shiikkss, sheellaa, sheemm, sheennaa, shpprrbb`
   - **Generated Names (Prefix: `aash`):**
     - `aashii, aashaa, aashaannee, aashaassaa, aash`
       
## Files

- **`PALLEKONDA_NAVEEN_KUMAR_22915_assignment2.py`**: Main Python script for training and evaluating the models.
- **`fnn/`**: Directory containing the FNN model files.
- **`rnn/`**: Directory containing the RNN model files.
- **`loss.json`**: JSON file containing the training loss history.

