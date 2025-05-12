# Robust 3D-to-2D Registration via Inverse Perspective ICP

This project implements a robust 3D-to-2D registration algorithm using an extended Iterative Closest Point (ICP) framework. By leveraging inverse perspective matching and robust optimization techniques, we align a 3D CAD model with 2D image keypoints without requiring depth data or stereo vision.

> 📌 Main Goal: Accurately align a projected 3D model onto a 2D image by minimizing reprojection error through iterative geometric optimization.

## 📐 Key Features

- Perspective-based ray casting for model-to-image correspondence
- Robust estimation using **Huber M-estimators** to handle noise and outliers
- **SVD-based rigid transformation** (rotation & translation)
- Adaptive **scale estimation** for better calibration
- **Stochastic restarts** to escape local minima and improve convergence
- Visualization tools to inspect convergence and accuracy over time

---

## 📊 Method Overview

The algorithm follows these core steps:

1. **Feature Detection** – Detect 2D corners using Shi-Tomasi algorithm
2. **Projection Matching** – Map 3D model points to inverse perspective rays in image space
3. **Transformation Estimation** – Use weighted SVD to estimate optimal rotation, translation, and scale
4. **Robust Optimization** – Apply Huber loss to downweight outliers
5. **Stochastic Restarts** – Perturb solution space when convergence stalls
6. **Convergence Monitoring** – Track projection accuracy and residual errors

---

## 📸 Visual Results

### 🔻 Final Alignment of 3D Model

<a href="https://drive.google.com/file/d/1CoDUqav9gJyndGIWlyXlJq3_rqGWukT0/view?usp=sharing" target="_blank">
  <img src="https://drive.google.com/uc?id=1CoDUqav9gJyndGIWlyXlJq3_rqGWukT0" width="500"/>
</a>

**Description:**  
The red wireframe cube represents the projected 3D model aligned over the blue 2D image corners. This result reflects the convergence of rotation, translation, and scale to achieve accurate model-to-image registration.

---

### 🔄 Iterative Alignment Convergence

<a href="https://drive.google.com/file/d/17Q-jlstKz4hvFUAoVInLXACeJm8bL6KL/view?usp=sharing" target="_blank">
  <img src="https://drive.google.com/uc?id=17Q-jlstKz4hvFUAoVInLXACeJm8bL6KL" width="500"/>
</a>

**Description:**  
This panel shows the cube’s transformation over 80,000 iterations. From a randomly initialized pose (top-left), the model gradually aligns with the image keypoints. The final frame (bottom-right) shows the registered cube in green, accurately matching the detected corners.

---

### 📉 Residual Error Over Iterations

<a href="https://drive.google.com/file/d/1QOqkKoeBBYD1NbZHD5Ni-7SyBtBlDGlU/view?usp=sharing" target="_blank">
  <img src="https://drive.google.com/uc?id=1QOqkKoeBBYD1NbZHD5Ni-7SyBtBlDGlU" width="500"/>
</a>

**Description:**  
The error plot shows how the average residual error (Huber loss) decreases over time. A sharp initial drop is followed by steady refinement, confirming proper convergence.
 
---

## 🛠️ Technologies Used

- Python
- OpenCV
- NumPy
- Matplotlib
- Linear Algebra (SVD)
- Robust Statistics (Huber Loss)
- Optimization Techniques
- ICP & Inverse Perspective Matching

---

## 🔍 Skills Demonstrated

- Geometric computer vision  
- Rigid body transformation estimation  
- Algorithmic optimization and debugging  
- Robust outlier handling with M-estimators  
- Visual analytics for algorithm convergence  

---



