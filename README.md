# 3D Reconstruction, Gaussian Splatting, and NeRF

## Project Overview
This project implements different techniques for 3D reconstruction, including **Classical Linear Algebra-based approaches**, **Gaussian Splatting**, and **Neural Radiance Fields (NeRF)**. Below, you'll find instructions to run the various notebooks and details about the datasets and output.

---

### **Input Datasets**
You can download the required datasets for each of the notebooks from the following links:

#### 1. **3D Reconstruction and Gaussian Splatting**:
   - **Dataset (Raw Images)**:  
     [Download Dataset](https://drive.google.com/drive/folders/1TbdaAgl1JUMnI40lDh9wkbY0QbIzMqFC?usp=sharing)

#### 2. **Camera Calibration**:
   - **Checkerboard Images**:  
     [Download Checkerboard Images](https://drive.google.com/drive/folders/1yWo7p490DPzUXQvoyZLQLH4GHCnNWQYh?usp=sharing)

#### 3. **NeRF (Neural Radiance Fields)**:
   - [Download NeRF Dataset](https://drive.google.com/drive/u/2/folders/1oGS2biV2ec0nSUgIfG6A6bvU7TlG2wa2)

---

### **Achieved Output**
Once the code is run successfully, the output will be stored in the following directory:

- [Download Achieved Output](https://drive.google.com/drive/folders/1f_XtbQ4nPKVW7ScprS7jAGta3mPN8t8F?usp=sharing)

---

## **Numerical Linear Algebra for 3D Reconstruction**
In the **Linear Algebra-based approach** for 3D reconstruction, we employ classical methods to create dense point clouds of the object.

### How to Reproduce the Code:
The full code is implemented and tested on **Google Colab** using Python CPU runtime.

1. **Prepare Datasets**:  
   - Download the datasets from the links provided above.
   - Place them into respective folders in your **Google Drive**:
     - Parent Directory: `'DSC 210 Final Project'`
     - Checkerboard image folder: `'checkerboard_imgs'`
     - Dataset folder: `'Dataset'`

2. **Mount Google Drive**:  
   - Mount the Drive in the Colab notebook (instructions included in the notebook).
   
3. **Run the Notebook**:  
   - Open the notebook and run each code block sequentially.
   - Output files will be generated in newly created folders.

---

### **Gaussian Splatting for 3D Reconstruction**
This section implements **Gaussian Splatting**, a technique for processing 3D point clouds by mapping them to voxel grids and applying Gaussian filters to represent density.

#### Features:
- **Feature Extraction**: Detects keypoints and descriptors using **SIFT**.
- **3D Reconstruction**: Triangulates points from image pairs using essential matrices.
- **Gaussian Splatting**: Maps 3D points to voxel grids and applies Gaussian smoothing.
- **Visualization**: Exports splatted 3D point clouds and generates visualizations.

#### Requirements:
- Python 3.8+
- Required Libraries:
  - OpenCV
  - NumPy
  - Matplotlib
  - SciPy
  - Open3D
  - Scikit-learn

To install the dependencies, run:

```bash
pip install -r requirements.txt
