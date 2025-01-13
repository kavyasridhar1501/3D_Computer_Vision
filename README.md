# 3D Reconstruction Project: README

## Input Files
### Datasets
- **3D Reconstruction (raw images)**: [Dataset Link](https://drive.google.com/drive/folders/1TbdaAgl1JUMnI40lDh9wkbY0QbIzMqFC?usp=sharing)
- **Camera Calibration (checkerboard images)**: [Checkerboard Images Link](https://drive.google.com/drive/folders/1yWo7p490DPzUXQvoyZLQLH4GHCnNWQYh?usp=sharing)
- **NeRF Dataset**: [NeRF Dataset Link](https://drive.google.com/drive/u/2/folders/1oGS2biV2ec0nSUgIfG6A6bvU7TlG2wa2)

### Output Directory
- [Output Achieved](https://drive.google.com/drive/folders/1f_XtbQ4nPKVW7ScprS7jAGta3mPN8t8F?usp=sharing)

---

## Numerical Linear Algebra
### Steps to Reproduce
1. Use **Google Colab** with Python CPU runtime.
2. Create the following folder structure in your Google Drive:
    - Parent Directory: `DSC 210 Final Project`
        - `checkerboard_imgs` (Download from [here](https://drive.google.com/drive/folders/1yWo7p490DPzUXQvoyZLQLH4GHCnNWQYh?usp=sharing))
        - `Dataset` (Download from [here](https://drive.google.com/drive/folders/1TbdaAgl1JUMnI40lDh9wkbY0QbIzMqFC?usp=sharing))
3. Mount your Google Drive in the Colab notebook.
4. Execute code blocks one at a time.
5. Output files will be stored in newly created folders within the parent directory.

---

## Gaussian Splatting for 3D Reconstruction
### Features
- **Feature Extraction**: Detects keypoints and descriptors using SIFT.
- **3D Reconstruction**: Triangulates points from image pairs using essential matrices.
- **Gaussian Splatting**: Maps 3D points to voxel grids and applies Gaussian smoothing.
- **Visualization**: Exports splatted 3D point clouds and generates visualizations.

### Requirements
- Python 3.8+
- Required Libraries:
  ```
  pip install -r requirements.txt
  ```

### Usage
1. Prepare Images: Place your images in a folder (e.g., `input_images`).
2. Open the notebook:
   ```
   jupyter notebook
   ```
3. Open `gaussian_splatting.ipynb` in the Jupyter Notebook interface.
4. Execute all cells in order.

### Outputs
- **Splatted Point Cloud**: Saved as `.ply` file in the output directory.
- **Visualizations**: Displayed inline and saved as `.png` files in the output directory.
- **Generated Files**:
  - Splatted Point Cloud: `output/gaussian_splatted_point_cloud.ply`
  - Feature Files: `.npz` files for each image
  - Visualizations:
    - Feature Matching Output: `feature_matching.png`
    - Static Point Cloud: `static_point_cloud.png`
    - 3D Point Cloud: `3d_point_cloud.jpeg`

### Code Snippet
```python
def process_point_cloud(points_3d):
    grid_size = 1024
    grid = np.zeros((grid_size, grid_size, grid_size))
    voxel_coords = (points_3d * (grid_size - 1)).astype(int)
    for point in voxel_coords:
        grid[point[0], point[1], point[2]] += 1
    return gaussian_filter(grid, sigma=1.0)
```

---

## NeRF: Neural Radiance Fields
### Folder Structure
1. `images_folder`: Contains the stereo images dataset.
2. `sparse`: Includes pre-computed COLMAP bin files and `.ini` file for 3D scene geometry.
3. `README.md`: Instructions for running the project.
4. `NeRF_3D_CV.ipynb`: Google Colab notebook containing the full implementation.

### Prerequisites
- Python 3.7+
- Required Libraries:
  ```
  pip install opencv-python opencv-contrib-python matplotlib numpy
  ```
- If using Google Colab, modules are pre-installed.

### COLMAP: Extracting Camera Parameters
- Pre-computed camera parameters are included in the `sparse` folder to avoid installation hassle.

### Execution Steps
1. Open `NeRF_3D_CV.ipynb` in Google Colab.
2. Execute the notebook block by block.

---
