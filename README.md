# Vehicle Detection, Tracking, and Speed Estimation

## Overview

This project implements a real-time computer vision system to detect, track, and estimate the speed of vehicles on a highway using deep learning models. The system processes video input, tracks moving vehicles over time, and estimates their speeds in kilometers per hour (km/h). When a vehicle exceeds a predefined speed limit, it is visually flagged with a red bounding box as an alert.

---

## Project Objectives

- Detect and track cars in highway video footage
- Estimate vehicle speed using pixel displacement over time
- Flag vehicles exceeding a configurable speed limit (e.g. 100 km/h)
- Compare the performance of three state-of-the-art object detection models:
  - **YOLOv8**
  - **SSD with MobileNetV3**
  - **Faster R-CNN with ResNet-50 + FPN**
- Evaluate models based on speed, detection consistency, and real-world usability
- Demonstrate the results via annotated output videos
  
---
## Dataset

The project uses an unlabeled, real-world highway traffic video recorded from a fixed overhead camera. The footage was sourced from the M6 motorway in the United Kingdom and features multi-lane, high-speed traffic—ideal for testing vehicle detection and speed estimation models.

- **Source**: [YouTube – M6 Motorway Traffic Video](https://www.youtube.com/watch?v=PNCJQkvALVc)
- **Clip Duration for Project**: 1-minute segment manually trimmed

Since the dataset does not include labels, the system is evaluated using internal metrics such as detection count, average tracking length, and average speed, as well as qualitative inspection of annotated output videos.

---

## Evaluation Metrics

- Average FPS (frames per second)
- Total runtime (seconds)
- Number of detections
- Average track length (frames)
- Average estimated speed (km/h)

Output videos were also reviewed for bounding box stability and correct alert behavior.

---

##  Sample Results

| Model        | FPS   | Detections | Avg. Track Length | Avg. Speed (km/h) | Runtime (s) |
|--------------|-------|------------|-------------------|-------------------|-------------|
| YOLOv8       | 53.00 | 22,092     | 279.65            | 48.85             | 33.27       |
| SSD          | 13.93 | 1,842      | 54.18             | 72.95             | 124.59      |
| Faster R-CNN | 0.58  | 36,652     | 407.24            | 31.30             | 2953.15     |

---

##  Results Summary

The system was tested on a one-minute highway video using three object detection models: YOLOv8, SSD, and Faster R-CNN. YOLOv8 offered the best real-time performance with stable tracking and realistic speed estimates. SSD performed moderately but suffered from inconsistent detections and unstable speed values. Faster R-CNN delivered the most accurate results but was too slow for real-time use. Overall, the system successfully demonstrated its ability to detect, track, and estimate vehicle speeds, and to flag speed violations reliably in real-world video footage.

