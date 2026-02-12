# EfficientDet

This notebook documents the attempt at training and evaluation of **EfficientDet** as a suitable design for the project.

## Context

EfficientDet was one of the **three initial model designs** considered for the system:

- YOLOv8  
- Faster R-CNN  
- EfficientDet  

## Overview of Model Evaluation

Prior to this attempt, I successfully trained and evaluated **EfficientDet D0 to D3** models. Although the model size increased with each version, the **Average Precision (AP) did not consistently improve**. And all the variants produced **lower AP** compared to smaller models.

This notebook was intended to be an attempt at evaluating an **EfficientDet D4** model.

## Process in the Notebook

The general workflow in this notebook includes:

1. **Dataset Preparation**
   - Loading images and annotations
   - Applying preprocessing compatible with EfficientDet

2. **Model Configuration**
   - Setting up the EfficientDet architecture
   - Configuring parameters for the D4 variant

3. **Training Setup**
   - Defining hyperparameters
   - Initializing the optimizer and loss functions

4. **Performance Assessment**
   - Measuring performance using Average Precision (AP)
   - Comparing results with previous EfficientDet variants (D0–D3)

## Why the D4 Evaluation Was Cancelled

The EfficientDet D4 evaluation was **cancelled before completion**. My decision was influenced by the following factors:

- Prior EfficientDet evaluations (D0–D3) showed **unsatisfactory performance**
- Larger model size did not translate to better detection accuracy
- The D4 model required **significantly longer training time**
- I assumed that the results would be similarly underwhelming and not worth the additional computational cost

## Outcome

Due to the overall performance limitations observed during EfficientDet evaluation, the model was **eventually removed from the final system design** and replaced with **RT-DETR**, which demonstrated better suitability for the project requirements.

This notebook is retained for **documentation and transparency**, showing the model assessment process and the rationale behind architectural decisions.
