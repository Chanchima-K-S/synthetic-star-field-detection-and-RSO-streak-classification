# Synthetic Star Field Detection and RSO Streak Classification

## Project Description

This project demonstrates a pipeline for generating a synthetic star field image, detecting stars and streaks (representing Resident Space Objects, RSOs), and classifying these features using computer vision and machine learning techniques.

The synthetic image consists of 100 Gaussian-like star points generated with `photutils`. After normalizing and denoising the image, stars are detected using the Laplacian of Gaussian (LoG) blob detection method. Synthetic streaks (simulating RSOs) are added manually using OpenCV line drawing functions. These streaks are then detected via the Probabilistic Hough Transform. 

Finally, a simple classification model (Random Forest) is trained on basic geometric features to distinguish between stars (blobs) and streaks (lines). Sub-pixel centroid refinement is applied on star detections using Gaussian centroiding, and approximate orientation estimation of streaks is demonstrated.

## Skills and Techniques Used

- **Synthetic Image Generation:** Using `photutils.datasets.make_100gaussians_image` to create star-like Gaussian blobs.
- **Image Preprocessing:** Normalization and Gaussian smoothing with OpenCV to reduce noise and prepare for feature detection.
- **Blob Detection:** Detecting star-like features with `skimage.feature.blob_log` (Laplacian of Gaussian).
- **Synthetic Data Augmentation:** Adding simulated streaks (RSOs) using OpenCV's line drawing.
- **Edge Detection:** Using Canny edge detection for highlighting streak edges.
- **Line Detection:** Detecting streaks via `skimage.transform.probabilistic_hough_line` (Probabilistic Hough Transform).
- **Feature Extraction:** Computing geometric features (blob radius, line length) for classification.
- **Classification:** Training a Random Forest classifier to distinguish stars from streaks.
- **Sub-pixel Accuracy:** Refining star centroids using `scipy.ndimage.center_of_mass` for higher localization precision.
- **Orientation Estimation:** Estimating streak orientation by calculating average angle of detected lines.
- **Visualization:** Using Matplotlib to plot images, detected features, and classification results.
- **Saving Outputs:** Exporting annotated images with OpenCV.

## Requirements

- Python 3.x
- photutils
- matplotlib
- numpy
- opencv-python
- scikit-image
- scipy
- scikit-learn

## Usage

1. Run the notebook or script to generate a synthetic star field.
2. The pipeline normalizes and denoises the image, detects stars and streaks, and classifies detected features.
3. Visualizations are displayed throughout, including star detection, streak detection, and classification results.
4. The annotated image with streaks is saved as `output_with_detections.png`.
5. Sub-pixel refined star centroids and estimated RSO orientation are printed in the console.

## Future Improvements

- Implement a full Bayesian inference model for robust orientation estimation.
- Use more advanced feature sets for classification to improve accuracy.
- Extend to real astronomical or satellite imagery for practical application.
- Incorporate temporal data for tracking moving RSOs across frames.

*This project demonstrates foundational computer vision and machine learning techniques in synthetic astronomical imaging and space object detection.*

