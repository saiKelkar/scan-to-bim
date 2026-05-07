# Scan-to-BIM: Automated 3D Reconstruction Pipeline

## Project Overview
Manual Building Information Modeling (BIM) generation for existing environments is a labor-intensive, error-prone, and expensive process. This creates a significant bottleneck for the digital transformation of the real estate industry, hindering efficient facility management and the scalability of PropTech solutions.

This project aims to develop a custom computational pipeline that utilizes 3D Deep Learning to segment unstructured 3D point cloud data into semantically rich, structured 3D BIM models.

## Core Objectives
* **Automate Reconstruction:** Bridge the gap between physical site conditions and digital twin environments.
* **Data Utilization:** Leverage the **S3DIS (Stanford Large-Scale 3D Indoor Spaces)** dataset to train and test segmentation pipelines.
* **Reduce Barriers:** Lower the technical and financial barriers to digitizing existing undocumented building stock.

## Tech Stack & Tools
* **Deep Learning:** RandLA-Net (Transitioned from PointNet)
* **Data Processing:** Open3D, NumPy, Pandas
* **Programming Language:** Python
* **BIM Interoperability:** IFC (Industry Foundation Classes) Export
* **Evaluation:** Confusion Matrix, mIoU (Mean Intersection over Union)
* **Core Concepts:** 3D Deep Learning, Computer Vision, Spatial Data Analysis, Photogrammetry

## Technical Evolution & Current Bottlenecks
### 1. Model Pivot: PointNet -> RandLA-Net
The project initially utilized **PointNet**, which proved insufficient for architectural-scale environments.
* **The Problem:** PointNet struggles with large-scale scenes and requires heavy downsampling, leading to the loss of critical geometric features and spatial context.
* **The Solution:** Shifted to **RandLA-Net**. By leveraging **Local Feature Aggregation**, the pipeline can now process massive point clouds efficiently without sacrificing the local geometric details necessary for accurate architectural element identification.

### 2. Data Strategy: Custom Scans & Manual Annotation
While the **S3DIS (Stanford Large-Scale 3D Indoor Spaces)** dataset provides a strong foundation, real-world spatial morphologies often contain noise not captured in academic datasets.
* **Current Effort:** Training on the 6 areas of the S3DIS dataset to establish baseline semantic accuracy.
* **Handling Sparsity:** Developing filtering algorithms to manage noise and varying point densities typical of real-world 3D acquisition, ensuring the model generalizes beyond academic datasets.

### 3. Evaluation & Actionable Output
The focus has shifted from simple segmentation to professional-grade interoperability:
* **Validation:** Implementing a **Confusion Matrix** to analyze classification errors between similar architectural classes (e.g., walls vs. columns).
* **BIM Integration:** Developing an export module to translate segmented point clusters into the **IFC format**, allowing for direct integration into professional BIM workflows such as **Revit** and **ArchiCAD**.


## Projected Impact
Once fully operational, this framework will enable faster property valuations, streamline renovation workflows, and provide a scalable foundation for AI-driven spatial analysis in the real estate and urban analytics sectors.

## Future Roadmap: End-to-End Acquisition
The current pipeline assumes high-density 3D data. The next phase focuses on Metric Scale Recovery from standard 2D imagery to democratize BIM creation for undocumented building stock:
* **Metric-Depth Estimation:** Exploring the integration of Monocular Depth Estimation models to predict spatial geometry from single-view Android imagery.
* **Structure from Motion (SfM) Integration:** Utilizing SfM pipelines to generate sparse point clouds from unordered image collections, followed by Visual-Inertial Odometry (VIO) data to recover absolute metric scale.
* **Monocular to Semantic:** Bridging the gap between 2D pixel-wise segmentation and 3D semantic labels, allowing for the generation of lod-100 (level of development) BIM models from basic site walk-throughs. 
