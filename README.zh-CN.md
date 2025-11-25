# multispectral_datasets
本仓库包含处理后的多光谱数据集，专为目标检测、语义分割和实例分割等各种计算机视觉任务设计。数据集主要关注基于材质和形状的瓶子及容器分类。

## 数据集概览

### 1. bottle500-IS (实例分割)
*   **任务：** 实例分割 (Instance Segmentation)
*   **数据格式：** YOLO 分割（`.txt` 文件中的多边形坐标）
*   **通道数：** 1
*   **类别 (4):**
    *   0: metal (金属)
    *   1: glass (玻璃)
    *   2: plastic (塑料)
    *   3: paper (纸)
*   **结构：**
    *   包含 `images/` 和 `labels/` 的 `train/`、`valid/`、`test/` 文件夹。

### 2. bottle500-OD (目标检测)
*   **任务：** 目标检测 (Object Detection)（支持多标签检测和实例分割）
*   **数据格式：** YOLO 检测与分割
    *   `det_labels/`：标准 YOLO 格式 (`class x_center y_center width height`)
    *   `labels/`：多标签格式 (`class1 class2 x_center y_center width height`)
    *   `seg_labels/`：YOLO 分割格式（多边形坐标）
*   **通道数：** 1
*   **类别：**
    *   **形状类别 (nc=4):**
        *   0: bottle (瓶子)
        *   1: round can (圆罐)
        *   2: round cup (圆杯)
        *   3: square box (方盒)
    *   **材质类别 (nc2=5):**
        *   0: cr plastic (透明塑料)
        *   1: metal (金属)
        *   2: paper (纸)
        *   3: glass (玻璃)
        *   4: w plastic (白色塑料)
*   **结构：**
    *   包含 `images/`、`labels/`、`det_labels/` 和 `seg_labels/` 的 `train/`、`valid/`、`test/` 文件夹。

### 3. bottle500-SS (语义分割)
*   **任务：** 语义分割 (Semantic Segmentation)
*   **数据格式：** 图像和掩码对 (Image and Mask pairs)
*   **通道数：** 1
*   **类别 (5):**
    *   0: background (背景)
    *   1: metal (金属)
    *   2: glass (玻璃)
    *   3: plastic (塑料)
    *   4: paper (纸)
*   **结构：**
    *   包含 `images/` 和 `masks/` 的 `train/`、`valid/`、`test/` 文件夹。

## 使用方法
每个数据集文件夹都包含一个与 YOLO 训练框架（例如 Ultralytics YOLOv8/v5）兼容的 `data.yaml` 文件。

```bash
# 示例：在 bottle500-IS 上训练 YOLOv8
yolo segment train data=bottle500-IS/data.yaml model=yolov8n-seg.pt epochs=100 imgsz=640
```
