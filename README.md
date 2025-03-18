# Morphology and Color

## Overview
This assignment focuses on implementing image processing techniques to identify regions of interest (ROIs) using morphological operations and color heatmaps. The goal is to process medical images (chest X-rays and skin lesions) by converting them to grayscale, applying Otsu's thresholding, performing morphological operations (erosion and dilation), and creating a heatmap to highlight ROIs. The final output is compared with a reference image using Root Mean Squared Error (RMSE).

## Requirements
- **Python 3**
- **Libraries**: `imageio`, `numpy`

## Installation
Install the required libraries using pip:

```bash
pip install numpy matplotlib gdown scikit-learn
```

## Code Structure

### Functions

1. **`otsu(img: np.ndarray, c=0)`**:
   - Applies Otsu's thresholding to binarize the image.
   - Parameters: `img` (input image), `c` (optional parameter, default is 0).

2. **`erosion(img, M, N)`**:
   - Applies the erosion morphological operation to the binary image.
   - Parameters: `img` (binary image), `M`, `N` (dimensions of the image).

3. **`dilation(img, M, N)`**:
   - Applies the dilation morphological operation to the binary image.
   - Parameters: `img` (binary image), `M`, `N` (dimensions of the image).

4. **`filter_gaussian(P, Q)`**:
   - Creates a Gaussian low-pass filter for heatmap generation.
   - Parameters: `P`, `Q` (dimensions of the image).

5. **`map_value_to_color(value, min_val, max_val, colormap)`**:
   - Maps a value to a color in the heatmap.
   - Parameters: `value`, `min_val`, `max_val`, `colormap`.

6. **`rms_error(img, out)`**:
   - Computes the Root Mean Squared Error (RMSE) between two images.
   - Parameters: `img` (reference image), `out` (output image).

### Main Script

- Loads the input image and reference image.
- Converts the input image to grayscale.
- Applies Otsu's thresholding to binarize the image.
- Applies a sequence of morphological operations (erosion and dilation) to refine the binary mask.
- Generates a heatmap using a Gaussian filter and maps it to colors.
- Combines the grayscale image with the heatmap to create the final output image.
- Computes and prints the RMSE between the final output image and the reference image.

## Usage

### Input Parameters
- `input_image`: Filename of the input image (e.g., `chest_xray.png`).
- `reference_image`: Filename of the reference image (e.g., `chest_xray_ref.png`).
- `indexes`: Sequence of morphological operations to be performed (e.g., `1 1 1 2 2 2 2`).
  - `1`: Erosion.
  - `2`: Dilation.

### Running the Code
Modify the input parameters in the script as needed and run the script to perform the morphological operations, heatmap generation, and RMSE calculation.

## Author
- Gustavo Lelli Guirao
- NUSP: 11918182
- SCC0251 - Image Processing and Analysis (1º/2024)