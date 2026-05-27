# Moving Object Detection and Segmentation

A computer vision pipeline implementing and comparing static and dynamic background subtraction techniques to isolate and track moving objects in video streams.

## Overview
This project explores fundamental and advanced methods for moving object detection in video surveillance contexts. By developing two distinct versions—one utilizing a custom median-based background model with morphological operations, and another leveraging OpenCV's dynamic GSOC subtractor—this project demonstrates a structured evolution of robust foreground extraction algorithms.

## Project Structure
- `Version 1`:
  - `detect.py`: Version 1 implementation using manual median frame differencing and summing techniques.
  - `get_background.py`: Helper module for Version 1 to compute the static background model from randomly sampled frames.
  - `Report - Moving Object Detection using Median Background Modeling and Morphological Dilation.pdf`: Report of the Version 1 implementation.
- `Version 2`:
  - `detectV2.py`: Version 2 optimized implementation utilizing the dynamic GSOC background subtractor.
  - `Report - Robust Moving Object Detection using GSOC Background Subtraction.pdf`: Report of the Version 2 optimized implementation.

## Key Phases
1. **Background Initialization:** Implemented both a static median temporal filter across random initial frames (V1) and a dynamically updating background model (V2) to establish a reference scene.
2. **Foreground Extraction:** Applied absolute frame differencing paired with fixed thresholding (V1) and automated GSOC foreground masking (V2) to isolate dynamic pixels.
3. **Morphological Refinement:** Utilized OpenCV morphological dilation (5 iterations) in the base version to bridge spatial gaps and fill structural holes within the foreground masks.
4. **Contour Analysis & Filtering:** Extracted structural contours and filtered out transient noise by imposing a strict minimal spatial area threshold, drawing bounding boundaries around verified entities.

## Key Technologies
- **Python:** Core video processing loop and logic pipeline.
- **OpenCV (cv2):** Image processing, matrix operations, GSOC subtractor, and contour detection.
- **NumPy:** Mathematical array manipulations and temporal median background calculations.

## Key Parameters
| Parameter | Value |
| :--- | :--- |
| **Median Frame Sample Size (V1)** | 50 frames |
| **Binary Threshold Value (V1)** | 30 |
| **Dilation Iterations (V1)** | 5 |
| **Minimum Contour Area** | 500 pixels |

## Author
**Sepehr Barekati**
