# Automatic Target Recognition using Deep Learning
Nate DiRenzo

## Abstract
The goal of this project was to evaluate the efficacy of using various deep learning methods to classify types of military vehicles in synthetic aperture radar (SAR) satellite imagery. I wanted to pursue this project because the Russian invasion of Ukraine has shown the importance of satellite imagery and its use by journalists, open-source intelligence analysts, human rights organizations, and most prominently, combatants. With the proliferation of such publicly-available imagery, I wanted to build a model that could serve as a proof of concept for detecting buildup, movement, strength, and deployment disposition using deep learning. 
## Design
This boiled down to an image-level classification algorithm, and so the design of this project was a bakeoff between various models to determine which performed best for my chosen evaluation metrics. I  started with a base model and used the validation metrics to inform further iterations. If a subsequent model performed better, it became my incumbent model and further iterations' validation metrics were evaluated against it. The stopping point for this project was when a point of diminishing returns was reached on my chosen model. 
## Data
The [dataset](https://www.kaggle.com/datasets/atreyamajumdar/mstar-dataset-8-classes) is taken from Kaggle, and was originally produced between 1995-1996 by Defense Advanced Research Projects Agency (DARPA). It contains roughly 1200 images of each of the 9 classes present in the dataset. 

## Algorithms

*Data Wrangling*
1. Image preprocessing
2. Image Augmentation
3. Dropout
4. Early Stopping
5. Learning Rate Reduction on Plateau

*Models*
- Multi-layer Perceptron
- Convolutional Neural Network
- Xception Architecture
- VGG19 Architecture

*Model Evaluation and Selection*

Dataset was split into 60/20/20 Train/Validation/Test split, and validation data was used to evaluate model performance and tune hyperparameters. Once final model selection had been made based on validation scores, final model was tested against test data. Model selection was driven by F2, Categorical Accuracy, and Matthews Correlation coefficient scores. Because we were working with fine margins, detailed confusion matrices for each model were also produced. As a final evaluation step, models produced a prediction given a satellite image of a Iraqi T-72 tank taken from the First Gulf War.

**Final Convolutional Neural Network**

**Validation:**
   - F2: .9705
   - Categorical Accuracy: .9706
   - MCC: .9669

**Test**   
   - F2: .975  
   - Categorical Accuracy: .9759
   - MCC: .9728

## Tools
- **Tensorflow**, **Keras**, and **NumPy** for data ingestion & manipulation.
- **Tensorflow**, **Keras**, and **sklearn** for modeling and evaluation
- **Matplotlib** and **Seaborn** for visualization

## Communication
See [PDF]() of slides.
