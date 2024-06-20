# Automative-Identification-Of-Objects (Colored Pencils Dataset) README

## Introduction

This dataset contains images of colored pencils organized by color. The images are captured using a webcam and stored in respective folders based on their colors. This dataset is intended for use in various computer vision tasks, such as color detection, classification, and image segmentation.

## Dataset Structure

The dataset is organized into folders, each corresponding to a specific color. Each folder contains a number of images captured using a webcam. The dataset includes the following colors:

- Red
- Blue
- Green
- Yellow
- Purple
- Orange

The structure of the dataset is as follows:

```
colored_pencils_dataset/
│
├── red/
│   ├── red_1.jpg
│   ├── red_2.jpg
│   ├── red_3.jpg
│   ├── red_4.jpg
│   ├── red_5.jpg
│
├── blue/
│   ├── blue_1.jpg
│   ├── blue_2.jpg
│   ├── blue_3.jpg
│   ├── blue_4.jpg
│   ├── blue_5.jpg
│
├── green/
│   ├── green_1.jpg
│   ├── green_2.jpg
│   ├── green_3.jpg
│   ├── green_4.jpg
│   ├── green_5.jpg
│
├── yellow/
│   ├── yellow_1.jpg
│   ├── yellow_2.jpg
│   ├── yellow_3.jpg
│   ├── yellow_4.jpg
│   ├── yellow_5.jpg
│
├── purple/
│   ├── purple_1.jpg
│   ├── purple_2.jpg
│   ├── purple_3.jpg
│   ├── purple_4.jpg
│   ├── purple_5.jpg
│
└── orange/
    ├── orange_1.jpg
    ├── orange_2.jpg
    ├── orange_3.jpg
    ├── orange_4.jpg
    ├── orange_5.jpg
```

## Usage

To use this dataset, simply download or clone the repository and access the images in the respective color folders.

## Image Capture Process

The images in this dataset were captured using a Python script with OpenCV. The script captures a specified number of images for each color and saves them in the corresponding folder. Below is a summary of the image capture process:

1. A webcam is used to capture images.
2. Images are stored in folders named after their respective colors.
3. Each folder contains 5 images for its respective color.

### Script

The following Python script was used to capture and save the images:

```python
import os
import cv2

# Specify the path to store the dataset
dataset_path = "colored_pencils_dataset"

# Create folders for each color
colors = ["red", "blue", "green", "yellow", "purple", "orange"]
for color in colors:
    os.makedirs(os.path.join(dataset_path, color), exist_ok=True)

# Capture images and save them in the respective color folders
def capture_images(color, num_images=5):
    cap = cv2.VideoCapture(0)  # Use 0 for the default camera

    if not cap.isOpened():
        print("Error: Could not open camera.")
        return

    for i in range(num_images):
        ret, frame = cap.read()

        if not ret:
            print(f"Error: Failed to capture image {i+1}")
            continue

        image_path = os.path.join(dataset_path, color, f"{color}_{i+1}.jpg")
        cv2.imwrite(image_path, frame)
        print(f"Image {i+1} captured for color {color}")

    cap.release()

# Capture 5 images for each color
for color in colors:
    capture_images(color)
```

## Contributing

If you would like to contribute to this dataset by adding more images or colors, please follow the structure and guidelines provided above. Feel free to submit a pull request with your additions.

---

Thank you for using the Colored Pencils Dataset!
