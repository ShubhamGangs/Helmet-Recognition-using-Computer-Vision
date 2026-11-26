HelmNet: Automated Workplace Safety Helmet Detection
HelmNet is an end-to-end deep learning project designed to automate safety compliance monitoring in hazardous work environments (such as construction sites, factories, and industrial plants). Using computer vision, HelmNet classifies images of workers to identify whether they are wearing safety helmets, providing an efficient, scalable, and automated safety oversight solution.

📌 Project Overview
Objective: Classify industrial images into "With Helmet" (Class 1) and "Without Helmet" (Class 0).
Primary Metric: High Precision (focusing on reducing False Positives, where a worker is predicted to be wearing a helmet but is not).
Frameworks & Tools: TensorFlow, Keras, OpenCV, Scikit-learn, Seaborn, Matplotlib.
📊 Dataset
Total Images: 4,125 images in RGB color space ($200 \times 200 \times 3$$200 \times 200 \times 3$).
Class Imbalance:
With Helmet (Class 1): 3,161 images (~76.6%)
Without Helmet (Class 0): 964 images (~23.4%)
Split: 80% Training (3,300 images), 10% Validation (412 images), 10% Testing (413 images).
🛠️ Model Architectures Evaluated
Simple CNN (From Scratch):
Failed to learn discriminative features for the minority class due to severe class imbalance (predicted only Class 1).
Transfer Learning with VGG-16 (Base):
Used frozen VGG-16 convolutional features and added a basic classification layer. Improved Class 0 precision significantly to 82%.
VGG-16 + Custom Feed-Forward Neural Network (FFNN):
Added dense layers (256 and 32 units) with a 40% Dropout rate. This was selected as the final model, achieving 95.15% validation accuracy and a balanced macro precision of 96%.
VGG-16 + FFNN + Data Augmentation:
Added real-time image transformations to reduce memorization. Enhanced generalization but slightly dropped peak validation precision.
📈 Key Results (Selected Model 3)
Test Accuracy: ~93.22%
Test Precision / Recall / F1-Score: ~0.93
Successfully resolved minority class failure, offering a stable architecture suitable for deployment.
🚀 Key Recommendations
Utilize class weights or focal loss to further mitigate minority class bias.
Rely on transfer learning architectures (like VGG-16) for industrial safety datasets of this scale.
Keep classification heads regularized using Dropout and early stopping to prevent overfitting.
