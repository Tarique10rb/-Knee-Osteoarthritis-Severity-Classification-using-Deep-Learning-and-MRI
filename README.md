# Knee Osteoarthritis Severity Classification using Deep Learning and MRI

## Overview

This project applies deep learning techniques to classify knee osteoarthritis (OA) severity using MRI images. The objective was to distinguish between healthy knees (KL0) and severe osteoarthritis cases (KL3/4) using convolutional neural networks (CNNs) and transfer learning approaches.

Using pretrained ResNet architectures, the project evaluates how different model configurations impact classification performance and generalization on a small medical imaging dataset.

---

## Background & Significance

Knee osteoarthritis is one of the leading causes of pain and disability worldwide. Accurate assessment of OA severity is important for early diagnosis, treatment planning, and monitoring disease progression.

MRI imaging provides detailed visualization of joint structures and cartilage degeneration, making it valuable for OA assessment. However, manual interpretation is time-consuming and subject to variability. Deep learning approaches may help automate and support imaging-based OA classification.

---

## Dataset

- Total Cases: 92 MRI studies  
- Classes:
  - 46 Healthy knees (KL0)
  - 46 Severe OA knees (KL3/4)

### Image Selection
For each case, the **middle MRI slice** was selected because it captures the most relevant joint structures while simplifying the task into a 2D image classification problem suitable for smaller datasets and pretrained CNN models.

---

## Methodology

### Deep Learning Architectures
The following pretrained CNN models were evaluated:

- ResNet18
- ResNet50

### Training Parameters Tested
- Different epoch values
- Different batch sizes

### Experimental Setup
- Binary classification task:
  - KL0 = Healthy
  - KL3/4 = Severe OA
- Transfer learning approach using pretrained CNNs
- Validation and test performance comparison used to assess generalization

---

## Model Performance

### ResNet50
- Epochs: 10
- Batch Size: 8
- Validation Accuracy: 85.7%
- Test Accuracy: 42.9%

Although ResNet50 achieved high validation accuracy, its poor test performance indicated significant overfitting.

---

### ResNet18 (Best Generalization)
- Epochs: 10
- Batch Size: 16
- Validation Accuracy: 64.3%
- Test Accuracy: 57.1%

ResNet18 demonstrated more stable and generalizable performance across validation and test datasets.

---

## Confusion Matrix Analysis

For the best-performing ResNet18 model:

- Correctly classified all 7 healthy (KL0) cases
- Correctly identified only 1 of 7 severe OA (KL3/4) cases
- Misclassified 6 severe OA cases as healthy

These results indicate that the model favored the healthy class and struggled to reliably detect severe OA.

---

## Key Findings

- ResNet50 showed signs of overfitting despite high validation accuracy
- ResNet18 generalized better on unseen data
- Small dataset size limited model learning capability
- MRI slice simplification reduced computational complexity but lost important 3D information

---

## Limitations

Several limitations affected model performance:

- Small dataset size (92 MRI images)
- Use of only a single middle MRI slice
- Loss of 3D structural information
- Overfitting in deeper models
- Limited generalization to unseen data

The model is not yet suitable for clinical implementation due to false positives and false negatives that could impact patient care.

---

## Future Improvements

Potential improvements include:

- Larger and more diverse datasets
- Full 3D MRI volume analysis
- Improved validation techniques
- Advanced architectures and regularization methods
- Multi-center imaging datasets for stronger generalization

---

## Tools & Technologies

- Python
- PyTorch
- ResNet18 / ResNet50
- NumPy
- Matplotlib
- Jupyter Notebook

---

## Use Case

This project demonstrates the potential application of AI in medical imaging and automated osteoarthritis assessment. It also highlights challenges associated with limited datasets and model generalization in healthcare AI systems.

---

## Key Highlights

- Deep learning for medical imaging
- MRI-based osteoarthritis classification
- Transfer learning using pretrained CNNs
- Model comparison and evaluation
- Confusion matrix analysis
- Clinical interpretation of AI limitations

---

## 👤 Author

Tarique Bagalkot, Rachael Millay, and Swetha Gade
