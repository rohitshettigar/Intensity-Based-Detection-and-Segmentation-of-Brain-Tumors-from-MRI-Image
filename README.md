# Intensity-Based Detection and Segmentation of Brain Tumors from MRI Image

---

##  Abstract

This project presents an intensity-based method for detecting and segmenting brain tumors using MRI images. Implemented in MATLAB, the algorithm uses contrast enhancement, thresholding, morphological operations, and edge detection to isolate tumor regions with an achieved accuracy of **73.57%**. This technique simplifies the traditional, manual MRI evaluation by automating the segmentation process.

---

##  Introduction

Brain tumors, when not detected early, can be life-threatening. MRI (Magnetic Resonance Imaging) is a powerful imaging technique widely used in brain analysis. However, manual interpretation of MRIs is time-consuming and error-prone. This project addresses the need for **automated brain tumor detection** and **segmentation** using intensity-based image processing in MATLAB.

---

##  Literature Review

Previous works on tumor segmentation involved complex models requiring advanced computational tools. This project focuses on **intensity thresholding and morphological operations**, offering a simpler approach for clear tumor region extraction, especially suitable for early-stage research and prototyping.

---

## Methodology

The following steps are used in the segmentation pipeline:

1. Load MRI Image  
2. Apply Contrast Enhancement  
3. Convert to Binary Image  
4. Apply Thresholding  
5. Perform Morphological Operations  
6. Detect Edges  
7. Apply Block-Wise Analysis  
8. Visualize and Highlight Tumor Region  
9. Calculate Accuracy

---

##  Implementation

Implemented in MATLAB using the following logic:

```matlab
% Load image and convert to grayscale
img = imread('brain_mri.jpg');
gray = rgb2gray(img);
% Enhance contrast and threshold
adjusted = imadjust(gray);
bw = imbinarize(adjusted);
% Morphological filtering
bw = imopen(bw, strel('disk', 5));
bw = imclose(bw, strel('disk', 3));
% Display tumor region
imshow(bw);
