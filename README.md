# Object_Detection_using_SSD-Mobilenet-V2

## Main Contributor
Pranav Balaji Balachandran


## 1. Introduction
This project evaluates the performance of the **DetectNet** model running on an **NVIDIA Jetson** platform with **SSD-Mobilenet-V2** as the backbone. The study includes an analysis of detection accuracy, precision, recall, and misclassification rates for key object categories such as **cars, traffic lights, persons, and plotted plants**.

## 2. Experimental Setup & Methodology
- **Hardware & Framework:** NVIDIA Jetson device optimized with the DNN library for real-time vision tasks.
- **Model:** DetectNet with SSD-Mobilenet-V2 for lightweight and efficient object detection.
- **Dataset:** 25 (each) images containing objects from the COCO dataset (91 classes). Evaluation focused on key objects.

## 3. Quantitative Analysis
### 3.1 Accuracy Measurements

#### Car Detection:
- **Average Accuracy:** 84.3%
- **Missed Cars:** 13 instances
- **Observation:** High accuracy with some detection variability.

#### Traffic Light Detection:
- **Average Accuracy:** 61.9%
- **Missed Traffic Lights:** 15 instances
- **Observation:** Least reliable class with a high failure rate.

#### Person Detection:
- **Average Accuracy:** 69.4%
- **Missed Persons:** 11 instances
- **Observation:** Moderate detection reliability but significant accuracy variation.

#### Plotted Plant Detection:
- **Average Accuracy:** 78.6%
- **Missed Plotted Plants:** 7 instances
- **Observation:** High but inconsistent accuracy.

### 3.2 Misclassification Analysis
- Foam Cube misclassified as Refrigerator (77.4% confidence)
- Car misclassified as Suitcase (86.3%, 68.2%, 62.2% confidence)
- Plotted Plant misclassified as Broccoli (61.2% confidence)
- **Key Observations:**
  - Feature overlap due to similar colors, textures, or shapes.
  - Partial views or unusual perspectives affecting detection.
  - Potential dataset biases leading to misclassification.

### 3.3 Precision and Recall Metrics 
| Object Class   | True Positives (TP) | Missed Detections (FN) | Recall (%) | Precision (%) |
|---------------|---------------------|------------------------|------------|---------------|
| Car           | 13                  | 13                     | 50%        | ~92%          |
| Traffic Light | 8                   | 15                     | 35%        | ~90%          |
| Person        | 16                  | 11                     | 59%        | ~91%          |
| Plotted Plant | 8                   | 7                      | 53%        | ~88%          |

## 4. Qualitative Analysis
- **Car Detection:** High median accuracy with consistent detections.
- **Traffic Light Detection:** Low accuracy and high variability.
- **Person Detection:** Moderate confidence but varying detection accuracy.
- **Plotted Plant Detection:** Generally strong performance but some inconsistencies.

## 5. Conclusion
### Key Findings:
- **Best Performance:** Car detection (high accuracy and consistency).
- **Least Reliable:** Traffic light detection (low recall and high failure rate).
- **Variable Performance:** Person detection (wide accuracy distribution).
- **Strong But Inconsistent:** Plotted plant detection.

### Future Recommendations:
- Fine Tuning using Transfer learning by training 50-100 images per class
- Enhance training with edge cases (e.g., hidden behind another object or dimly lit objects).
- Adjust confidence thresholds to balance recall and precision.

## 6. Final Remarks
This study provides a detailed analysis of **DetectNet with SSD-Mobilenet-V2** for object detection on an **NVIDIA Jetson** platform. Future work should focus on reducing detection errors and improving model robustness under diverse real-world conditions.



