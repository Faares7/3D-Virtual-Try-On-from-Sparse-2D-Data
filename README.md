# 3D Virtual Try-On from Preprocessed 2D Data  
*Optimized pipeline for garment fitting with ready-to-use or raw datasets*

## Project Overview  
This repository provides:  
1. **Main Model**: Complete 3D virtual try-on pipeline including:
   - Body reconstruction from 2D keypoints
   - Garment warping with UV Mapping on SMPL-X meshes
   - Physics-based clothing simulation
2. **Optional Script**: Preprocessing utility for raw datasets  


### Key Features  
✅ **End-to-End Pipeline**: From 2D data to dressed 3D avatars  
✅ **Advanced Garment Warping**: Precise clothing deformation on body meshes  
✅ **Visual Samples**: Includes output videos and images (see `samples/`)  
✅ **Flexible Input**: Works with both preprocessed and raw datasets  

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
```bash
# SMPL-X and Body Model  
pip install smplx human-body-prior  

# Mesh Processing & Garment Warping  
pip install trimesh vedo pyrender warp-lang  

# Numerical Operations  
pip install numpy scipy chumpy  

# Visualization  
pip install opencv-python matplotlib
```
#### For GPU support (recommended):
```bash
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu113
```
## Usage
### For Preprocessed Data (Recommended)
```bash
python run_model.py \
    --input_dir ./preprocessed_data/ \
    --output_dir ./results/ \
    --warp_garments True
```
### For Raw Datasets
```bash
python scripts/preprocessing.py \
    --raw_data ./input_images/ \
    --output ./preprocessed_output/
```
## Visualizing Results
### Check the samples/ directory for:

   - Output videos (samples/videos/)

   - Before Warping (samples/images/)

   - After Warping (samples/images/)

## Technical Pipeline
1. Body Reconstruction: SMPL-X mesh from 2D keypoints

2. Garment Warping:
    - UV mapping of clothing textures

    - Physics-based deformation on body mesh

3. Final Rendering:
   - Dressed avatar generation

## Repository Structure:
 images (results/images/)
```bash
3D-Virtual-Try-On/
├── model/                          
│   ├── SMPLifyx Pipeline.ipynp  # SMPL-X estimation
├── scripts/                                    
│   ├── data_preprocessing.py  # Data preparation
├── samples/                  
│   ├── videos/               # Demo videos
│   └── images/               # Rendered results
├── requirements.txt          # Dependencies
├── report.doc                # Technical documentation
└── ppt.pdf                   # Project summary
```

## Full Report:
- Detailed methodology including garment warping

## Presentation: 
- Visual walkthrough of the pipeline

## Acknowledgements
### This project builds upon:
   - SMPLify-X Perfect Implementation

   - M3D-VTON Dataset

   - Garment warping techniques using UV Mapping
