# multispectral_datasets

Some processed multispectral datasets for detection/semantic/instance segmentation tasks.

## Datasets

### spectrum500-detect

**Task**: Object Detection

| Item | Description |
|------|-------------|
| Dataset Name | spectrum500-detect |
| Task Type | Object Detection |
| Number of Images | TBD |
| Number of Classes | TBD |
| Image Resolution | TBD |
| Annotation Format | TBD |
| Train/Val/Test Split | TBD |

### spectrum500-semantic-seg

**Task**: Semantic Segmentation

| Item | Description |
|------|-------------|
| Dataset Name | spectrum500-semantic-seg |
| Task Type | Semantic Segmentation |
| Number of Images | TBD |
| Number of Classes | TBD |
| Image Resolution | TBD |
| Annotation Format | TBD |
| Train/Val/Test Split | TBD |

---

## Dataset Template

Below is the standard template for describing each dataset:

```markdown
### [Dataset Name]

**Task**: [Task Type]

| Item | Description |
|------|-------------|
| Dataset Name | [Name] |
| Task Type | [Detection/Semantic Segmentation/Instance Segmentation] |
| Number of Images | [Total count] |
| Number of Classes | [Class count] |
| Image Resolution | [Width x Height] |
| Annotation Format | [COCO/VOC/Custom] |
| Train/Val/Test Split | [Train/Val/Test counts or ratios] |

#### Directory Structure

```text
[dataset-name]/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
├── annotations/
│   ├── train/
│   ├── val/
│   └── test/
└── README.md
```

#### Classes

| Class ID | Class Name |
|----------|------------|
| 0 | [class_0] |
| 1 | [class_1] |
| ... | ... |

#### Usage

[Instructions for using this dataset]

#### Citation

[Citation information if applicable]
```
