# Design of Defective Solar Panel Module Detection Using Deep Learning

This repository documents the model design, evaluation, and selection process for our design project called "Design of Defective Module Detection for Solar Panel Thermography Analysis System using Deep Learning".

The project explores multiple object detection architectures to determine the most reliable solution under realistic engineering constraints. Each design is thoroughly documented with training workflows, configurations, and evaluation results to ensure transparency in the decision-making process.

## Project Overview

Solar panel defects such as hotspots, bypass diode failures, partial shading, open circuits, and short circuits can significantly reduce system efficiency and pose safety risks. Early and accurate detection is therefore critical for maintaining optimal performance.

This project aims to develop an intelligent detection system capable of:

- Identifying defects from thermal images  
- Providing precise localization through bounding boxes  
- Supporting real-time or near-real-time analysis  
- Maintaining robustness across varying operational constraints  

The selected model is integrated into the **Adlaw Mobile Application**, enabling users to capture thermal images, receive defect alerts, and view detailed diagnostic information.

> **Adlaw Repository:**  
https://github.com/qmjae/project-design

The mobile application is built using **React Native**, **FastAPI**, **Appwrite**, and **YOLO-based inference**, forming a complete end-to-end defect detection pipeline.

---

# Detection Model Designs

Three state-of-the-art object detection architectures were evaluated:

## **Design 1 — YOLOv8**
A single-stage detector optimized for speed and accuracy. YOLOv8 demonstrated strong multiscale detection capability and efficient inference, making it highly suitable for real-time applications.

> See `/Design 1 - YOLOv8` for full documentation.

---

## **Design 2 — Faster R-CNN**
A two-stage detector known for precise localization and high detection accuracy. While computationally intensive, it provides reliable predictions for small and subtle thermal defects.

> See `/Design 2 - Faster R-CNN` for full documentation.

---

## **Design 3 — RT-DETR**
A transformer-based architecture designed for real-time object detection. RT-DETR combines global context modeling with efficient feature encoding to achieve a balance between precision and speed.

> See `/Design 3 - RT-DETR` for full documentation.

---

# Sensitivity Analysis

Selecting the final architecture required more than comparing raw performance metrics. A **sensitivity analysis** was conducted to evaluate how each design performs when project priorities shift.

Using five engineering constraints, **120 unique weighting combinations** were generated to simulate varying operational requirements. The weighted scores were visualized using a polar chart to compare model adaptability across the design space.

![Sensitivity Analysis](sensitivity%20analysis.png)

## Results

- **YOLOv8:** 53 wins  
- **Faster R-CNN:** 31 wins  
- **RT-DETR:** 36 wins  

YOLOv8 achieved the highest number of peak scores, indicating superior robustness across changing constraint importance.

### Key Insights

- **YOLOv8** maintained the most consistent performance, demonstrating strong adaptability and engineering reliability.  
- **Faster R-CNN** showed higher sensitivity to constraint variations, excelling primarily when accuracy-related factors were heavily prioritized.  
- **RT-DETR** delivered competitive precision but was frequently penalized due to higher training time and computational cost.

Although some models outperformed others under specific conditions, the overall trend confirms that **YOLOv8 occupies the most stable region of the design space**, making it the most dependable choice when real-world priorities evolve. 

As a result, **YOLOv8 was selected as the primary detection model** for deployment within the Adlaw system.
