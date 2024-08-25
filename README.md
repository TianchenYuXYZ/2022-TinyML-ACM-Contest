TinyML Design Contest 2022: Winning Solution
This repository contains the winning design from the 2022 TinyML Design Contest, which tasked participants with developing a binary classification model to discriminate life-threatening ventricular arrhythmias (VAs) from non-VAs using single-lead IEGM recordings. The model needed to excel in detection precision, memory occupation, and inference latency, making it suitable for deployment on resource-constrained microcontrollers.

Project Overview
The core challenge was to classify ventricular arrhythmias like Ventricular Tachycardia (VT), Ventricular Fibrillation (VF), and Ventricular Flutter (VFt) from IEGM signals. The dataset comprised 24,000 training samples and 5,000 test samples, each representing a 5-second IEGM recording.

Key Features
Signal Processing and Feature Extraction: Utilized techniques like QRS complex detection using morphological filtering, wavelet transforms, and principal component analysis (PCA) to enhance feature extraction from the ECG signals.
Model Development: Explored various models including Convolutional Neural Networks (CNNs), Autoencoders, and traditional classifiers like Logistic Regression and Support Vector Machines (SVM). The CNN-based models, enhanced by Neural Architecture Search (NAS), provided promising results.
Hardware Deployment: The models were deployed on an STM32 NUCLEO-L432KC board, which features an ARM Cortex-M4 core. The deployment pipeline included optimization techniques to reduce memory footprint and improve latency.
Results
Accuracy and Precision: The optimized Autoencoder model achieved a test accuracy of 94.898%, while the IEGMNet model from the organizers reached 96.391% training accuracy. Further optimizations led to models surpassing 96% accuracy with minimal resource usage.
Latency: The best-performing models demonstrated an inference latency of approximately 0.252 seconds on the target hardware, a significant improvement over earlier versions.
Model Compression: The use of model quantization reduced the model size by over 40%, enabling deployment on the microcontroller with minimal loss in accuracy.
Deployment Success: The logistic regression model with peak extraction was successfully deployed with an F1-β score of 0.9628, showcasing the balance between precision and recall in real-time execution on the hardware.
Repository Contents
Model Implementations: Python scripts and ONNX models used for training and deployment.
Deployment Scripts: Code for deploying the models onto the STM32 board, including memory optimization and execution instructions.
Experimental Results: Detailed logs and performance metrics from various models tested during the contest, with insights into the trade-offs made between accuracy, latency, and memory usage.
