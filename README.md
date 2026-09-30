# FYP Solar Panel Segmentation Dataset

Multi-temporal (2021–2025) solar panel satellite segmentation pipeline, datasets, and Google Colab training notebooks.

## Repository Structure

```text
├── Dataset/
│   ├── COCO/                     # COCO format segmentation annotations (2021–2025)
│   │   ├── 2021 .. 2025/
│   │   │   ├── train/ (images, _annotations.coco.json)
│   │   │   ├── valid/
│   │   │   └── test/
│   ├── YOLO/                     # YOLO format segmentation labels & images (2021–2025)
│   │   ├── data.yaml
│   │   └── 2021 .. 2025/
│   │       ├── train/ (images, labels)
│   │       ├── valid/
│   │       └── test/
│   └── download_datasets.py      # Dataset sync & download utility
├── Note books/
│   ├── cnn.ipynb                 # CNN U-Net (ResNet-34) training notebook
│   ├── rcnn.ipynb                # Mask R-CNN (Detectron2) training notebook
│   ├── yolo11.ipynb              # YOLO11m-seg training & temporal analysis
├── Training results/
│   ├── weights/
│   │   ├── yolo11m_best.pt       # YOLO11m-seg best model weights
│   │   ├── mask_rcnn_final.pth   # Mask R-CNN final model weights
│   │   └── best_cnn_unet.pth     # CNN U-Net best model weights
│   ├── cnn_unet_results.zip      # CNN U-Net training plots & metrics
│   ├── mask_rcnn_evaluation_results.zip # Mask R-CNN evaluation logs & metrics
│   └── yolo11m_solar_complete_results.zip # YOLO complete training runs
├── .gitattributes                # Git LFS configuration
├── .gitignore
└── README.md
```

## Dataset Usage in Notebooks

All notebooks automatically clone and load the dataset directly from this GitHub repository:
```bash
git clone https://github.com/Hinarashid220/FYP.git
```
- **CNN U-Net**: Reads from `FYP/Dataset/YOLO` (or local `Dataset/YOLO`)
- **Mask R-CNN**: Reads from `FYP/Dataset/COCO` (or local `Dataset/COCO`)
- **YOLO11m-seg**: Reads from `FYP/Dataset/YOLO` (or local `Dataset/YOLO`)
- **Test Notebook**: Automatically locates test samples from `FYP/Dataset/YOLO/2025/test/images` or `Dataset/YOLO/2025/test/images`
