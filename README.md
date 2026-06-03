# SGHAPS: Sensitivity-Guided Hardware-Aware Precision Search for Robust Deployment of Multimodal Dermatological Models on Edge Devices

Official implementation of the paper: *"SGHAPS: Sensitivity-Guided Hardware-Aware Precision Search for Robust Deployment of Multimodal Dermatological Models on Edge Devices"* (IEEE ICDM 2026).

This repository provides the complete, end-to-end codebase for training, quantizing (PTQ/QAT), and evaluating multimodal deep learning models for dermatological diagnosis. The framework automatically handles training, block-wise sensitivity profiling, partial/full quantization, and metric evaluation.

## Dataset Preparation

To ensure full reproducibility, this repository includes the curated metadata for the 41,725 images used in our study. 

1. **Download Images**: Obtain the dermatoscopic images from the official [International Skin Imaging Collaboration (ISIC) Archive](https://www.isic-archive.com/).
2. **Organize Directory**: Create a folder named `data/images/` and place the downloaded `.jpg` files inside.
3. **Metadata Mapping**: The file `isic_dataset_metadata.csv` contains the exact ISIC image IDs, histologically confirmed diagnostic labels (10 classes), and patient metadata (gender, age group, anatomical location) used to form the 60:20:20 stratified splits. The scripts will automatically read this CSV to build the PyTorch `DataLoader`.

## Environment Setup

The code was developed and tested on **Python 3.11.11** with an NVIDIA GPU (e.g., RTX 4070 Ti SUPER, 16GB VRAM). 

Install the required dependencies using the provided `requirements.txt`:

# Create and activate a virtual environment (recommended)
python -m venv sghaps_env
source sghaps_env/bin/activate  # On Windows use: sghaps_env\Scripts\activate

# Install dependencies
pip install -r requirements.txt
