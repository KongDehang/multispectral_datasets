[中文](README.zh-CN.md)

# multispectral_datasets
This repository contains processed multispectral datasets designed for various computer vision tasks including Object Detection, Semantic Segmentation, and Instance Segmentation. The datasets are focused on bottle and container classification based on material and shape.

## Datasets Overview

### 1. bottle500-IS (Instance Segmentation)
*   **Task:** Instance Segmentation
*   **Data Format:** YOLO Segmentation (Polygon coordinates in `.txt` files)
*   **Channels:** 1
*   **Classes (4):**
    *   0: metal
    *   1: glass
    *   2: plastic
    *   3: paper
*   **Structure:**
    *   `train/`, `valid/`, `test/` folders containing `images/` and `labels/`.

### 2. bottle500-OD (Object Detection)
*   **Task:** Object Detection (Supports Multi-label detection and Instance Segmentation)
*   **Data Format:** YOLO Detection & Segmentation
    *   `det_labels/`: Standard YOLO format (`class x_center y_center width height`)
    *   `labels/`: Multi-label format (`class1 class2 x_center y_center width height`)
    *   `seg_labels/`: YOLO Segmentation format (Polygon coordinates)
*   **Channels:** 1
*   **Classes:**
    *   **Shape Classes (nc=4):**
        *   0: bottle
        *   1: round can
        *   2: round cup
        *   3: square box
    *   **Material Classes (nc2=5):**
        *   0: cr plastic
        *   1: metal
        *   2: paper
        *   3: glass
        *   4: w plastic
*   **Structure:**
    *   `train/`, `valid/`, `test/` folders containing `images/`, `labels/`, `det_labels/`, and `seg_labels/`.

### 3. bottle500-SS (Semantic Segmentation)
*   **Task:** Semantic Segmentation
*   **Data Format:** Image and Mask pairs
*   **Channels:** 1
*   **Classes (5):**
    *   0: background
    *   1: metal
    *   2: glass
    *   3: plastic
    *   4: paper
*   **Structure:**
    *   `train/`, `valid/`, `test/` folders containing `images/` and `masks/`.

## Usage
Each dataset folder contains a `data.yaml` file compatible with YOLO training frameworks (e.g., Ultralytics YOLOv8/v5).

```bash
# Example: Training YOLOv8 on bottle500-IS
yolo segment train data=bottle500-IS/data.yaml model=yolov8n-seg.pt epochs=100 imgsz=640
```
