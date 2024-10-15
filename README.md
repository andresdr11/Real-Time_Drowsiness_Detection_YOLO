# Real-Time Drowsiness Detection using YOLOv11
### Overview
This project implements a real-time drowsiness detection system using a custom-trained YOLOv11 model. The primary goal is to accurately distinguish between drowsy and alert driver states, providing a foundation for future integration into driver safety systems. The system is designed to enhance road safety by detecting signs of drowsiness and triggering timely alerts to prevent accidents.

### Features
* Real-time detection of driver drowsiness from live video feeds
* High accuracy with 95.63% test accuracy
* Custom YOLOv11 model, trained for robustness and efficiency in detecting drowsy and alert states

### Dataset
The custom dataset contains approximately 8,900 labeled images, including additional data from 12 individuals (friends and relatives) in drowsy and alert conditions to enhance the model’s generalization. Images were annotated using RoboFlow and split into training, validation, and test sets.

* Classes: Drowsy, Alert, No Detection
* Dataset Size: ~8,900 images
* Annotation Tool: RoboFlow

### Data Splits:
* Training Set: 7,316 images (82%)
* Validation Set: 1,032 images (12%)
* Test Set: 552 images (6%)

### Model Training
The YOLOv11 model was trained using the AdamW optimizer for 30 epochs, with early stopping at epoch 28 to prevent overfitting. Training was performed on Google Colab using GPU acceleration. Data augmentation techniques were applied during training to improve generalization, and the model’s performance was evaluated through precision, recall, and mean Average Precision (mAP) metrics.

#### Key Performance Metrics:
* Precision: 99.7%
* Recall: 99.8%
* mAP@50: 99.4%
* mAP@50-95: 77.8%

### Confusion Matrix Analysis
The confusion matrix provides a breakdown of the model's performance across the key classes: "Drowsy," "Alert," and "No Detection."

* Correct Classifications: 503 out of 526 total predictions (95.63% accuracy)
* False Negatives (Drowsy misclassified as Alert): 16 instances
* False Positives (Alert misclassified as Drowsy): 1 instance
* Missed Detections: 6 instances where drowsiness was present but not detected

### Drowsy Class:
* Precision: 93.79% (Low false positives)
* Recall: 91.63% (Some missed detections)



The confusion matrix reveals that the model is highly reliable in distinguishing between drowsy and alert states, with only minor misclassifications and missed detections, especially in cases where drowsiness signs were subtle or ambiguous.
