# Project Title: Soccer Players Tracking and Team Classification

## Table of Contents
- [Introduction](#introduction)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Future Enhancements](#future-enhancements)
- [How to Run](#how-to-run)

---

## Introduction
This project aims to track and classify elements in football games. The system detects:
- Players of both teams
- Goalkeepers
- Referee and linemen
- The ball

The tracked elements are annotated with bounding boxes and classified based on their roles and teams.

---

## Problem Statement
Tracking and team classification in football matches are challenging due to:
1. High player density.
2. Frequent occlusions.
3. Fast player movements and changes in camera angles.

The goal is to create an accurate and efficient solution for these challenges.

---

## Dataset
### Primary Dataset: SoccerNet Tracking
- **Videos**: 57 clips, 30 seconds each, 24 FPS.
- **Labels**: Players, goalkeepers, referees, ball, and bounding boxes with IDs.
- **Resolution**: 1920 × 1080 pixels.

### Secondary Dataset: Roboflow
- **Training Samples**: 204 images with augmentation.
- **Validation Samples**: 38 images.
- **Test Samples**: 13 images.

---

## Methodology
1. **Detection**: YOLO models (YOLOv5, YOLOv8, YOLOv10) trained on SoccerNet and Roboflow datasets.
2. **Team Assignment**:
   - **First Approach**: K-means clustering on RGB shirt colors.
   - **Improved Approach**: SigLIP Vision Transformer for embeddings and UMAP for dimensionality reduction.
3. **Tracking**: ByteTrack algorithm combined with Kalman filters.
4. **Goalkeeper Classification**:
   - Using K-Nearest Neighbors (KNN) for player proximity analysis.
5. **Inference Optimization**:
   - Reduced processing time by analyzing every 10th frame and leveraging tracking IDs.

---

## Future Enhancements
- Implement spatial attention mechanisms.
- Optimize for real-time processing.
- Utilize advanced architectures like Vision Transformers.

---

## How to Run
### Clone the Repository
```bash
git clone https://github.com/yourusername/soccer-tracking-classification.git
cd soccer-tracking-classification
