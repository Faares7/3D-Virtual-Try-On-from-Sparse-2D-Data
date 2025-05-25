# 3D Virtual Try-On from Preprocessed 2D Data  
*Optimized pipeline for garment fitting with ready-to-use datasets*

## Project Overview  
This repository provides:  
1. **Main Model**: 3D virtual try-on pipeline working directly with preprocessed garment data (extracted garments + masks)  
2. **Optional Script**: Preprocessing utility for raw datasets (if needed)  

Inspired by: [SMPLify-X Perfect Implementation](https://github.com/KyujinHan/Smplify-X-Perfect-Implementation.git)  

### Key Features  
✅ **Works with preprocessed data** - Skips expensive OpenPose stage  
✅ **Flexible input** - Compatible with both ready-to-use and raw datasets  
✅ **Optimized pipeline** - Focused on garment-body alignment  

---

## Dataset Information  
### Recommended Prepared Dataset  
We use the **M3D-VTON dataset** ([GitHub](https://github.com/fyviezhao/M3D-VTON)) which includes:  
- Pre-extracted garment textures  
- Segmentation masks  
- Body keypoints  

**Download**: [Google Drive](https://drive.google.com/file/d/1qcynpXZ9eSlzTV-RDCr-Yip3GcuU314h/view?usp=sharing)  

*Note: For custom datasets, use the included preprocessing script.*

---

## Installation  

### 1. Clone Repository  
```bash  
git clone https://github.com/your-username/3D-Virtual-Try-On.git  
cd 3D-Virtual-Try-On
```
### 2. Install Dependencies
#### Core Requirements:
```bash
pip install -r requirements.txt
``` 
#### Essential Dependencies:
```
bash
# SMPL-X and Body Model  
pip install smplx human-body-prior  

# Mesh Processing  
pip install trimesh vedo pyrender  

# Numerical Operations  
pip install numpy scipy chumpy  

# Optional for Preprocessing  
pip install opencv-python matplotlib
```  
#### For GPU support (recommended):
```
bash
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu113
```  
Usage
For Preprocessed Data (Recommended)
bash
python run_model.py \
    --input_dir ./preprocessed_data/ \
    --output_dir ./results/
For Raw Datasets
bash
python scripts/preprocessing.py \
    --raw_data ./input_images/ \
    --output ./preprocessed_output/
Repository Structure
3D-Virtual-Try-On/
├── model/                    # Main model implementation
├── scripts/
│   ├── preprocessing.py      # Dataset preparation utility
│   └── utils.py              # Helper functions
├── requirements.txt          # Core dependencies
├── report.pdf                # Technical documentation
└── presentation.pdf          # Project summary
Documentation
Full Report

Presentation Slides
