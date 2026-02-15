# Can Detection

Circle detection in images using OpenCV. The program loads an image, preprocesses it through grayscale conversion, Gaussian blur, and Canny edge detection, then identifies circles using the Hough Circle Transform. Detected circles are drawn on the original image and saved as output.

## Features

- **Circle Detection:** Identifies circular shapes using the Hough Circle Transform.
- **Image Preprocessing:** Applies grayscale conversion, Gaussian blur, and Canny edge detection to prepare the image for circle detection.
- **Visual Output:** Draws detected circles and their center points on the original image, then displays and saves the result.

## Project Structure

```
CanDetection/
├── main.py      # Main script for image processing and circle detection
├── can.jpg      # Input image
└── img_4.png    # Output image with detected circles
```

## How It Works

1. **Load Image:** Reads `can.jpg` from the working directory.
2. **Grayscale Conversion:** Converts the image from BGR to grayscale.
3. **Gaussian Blur:** Applies a 15x15 Gaussian kernel to reduce noise.
4. **Edge Detection:** Uses Canny edge detection (thresholds: 20, 150) to find edges.
5. **Circle Detection:** Applies the Hough Circle Transform to detect circles in the edge-detected image.
6. **Draw Circles:** Draws a green circle outline and center dot for each detected circle.
7. **Output:** Displays the annotated image in a window and saves it as `img_4.png`.

## Usage

### Install Dependencies

```bash
pip install opencv-python numpy
```

### Run

```bash
python main.py
```

Place your input image as `can.jpg` in the same directory as `main.py`, or update the file path in the script.

Press any key to close the display window after viewing the result.

## Functions (main.py)

| Step | Function | Purpose | Parameters |
|------|----------|---------|------------|
| 1 | `cv2.cvtColor()` | Convert to grayscale | `COLOR_BGR2GRAY` |
| 2 | `cv2.GaussianBlur()` | Noise reduction | Kernel: `(15, 15)` |
| 3 | `cv2.Canny()` | Edge detection | Thresholds: `20, 150` |
| 4 | `cv2.HoughCircles()` | Circle detection | Method: `HOUGH_GRADIENT`, dp: `1.5`, minDist: `999`, param1: `120`, param2: `70` |
| 5 | `cv2.circle()` | Draw circle + center | Color: `(50, 255, 20)`, thickness: `15` (outline), `10` (center) |

## Requirements

- Python 3.x
- OpenCV (`cv2`)
- NumPy
