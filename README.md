# Lake Level Monitoring Using YOLO & Image Regression

This project leverages YOLOv8, a state-of-the-art object detection algorithm, to accurately identify water level markers from images captured at different timestamps. Detected regions are cropped, augmented using Albumentations, and aligned with structured water level data from Excel sheets. The resulting dataset forms the foundation for machine learning models aimed at predicting and analyzing water levels over time.



## ✅ Features

- **Object Detection with YOLOv8**: Detects water level markings in lake images with high accuracy.
- **Image Cropping**: Extracts relevant marker regions for regression.
- **Data Augmentation**: Uses `Albumentations` for robust image transformations such as flips, brightness shifts, and rotations.
- **Time-Series Alignment**: Matches cropped images with nearest timestamps from Excel data using `pandas`.
- **Dataset Creation**: Generates a structured dataset for supervised regression models.
- **End-to-End Pipeline**: From raw image data collection to labeled datasets ready for machine learning models.

---

## 📋 How It Works

1. **Data Collection & Annotation**
   - Images are labeled using tools like `LabelImg` in YOLO format.
   - Labels define the bounding box around water level markers.

2. **Dataset Preparation**
   - Data is split into training and validation sets.
   - A `data.yaml` file configures the dataset.

3. **Data Augmentation**
   - Using `Albumentations`, the dataset is artificially expanded to include various lighting, rotations, and shifts.
   - Augmentations ensure the model generalizes across conditions.

4. **YOLO Training**
   - The `YOLOv8` model is trained on labeled images to detect water level markers.

5. **Inference & Cropping**
   - The model is used to predict regions in new images.
   - Detected regions are cropped and saved with timestamp filenames.

6. **Linking Images with Water Levels**
   - Excel sheets with timestamps and water level measurements are processed using `pandas`.
   - Each cropped image is matched with the nearest timestamp’s measurement.

7. **Final Dataset**
   - The output is a CSV containing image paths and corresponding water level readings.
   - This dataset can be used to train regression models or other ML pipelines.

---

## 📦 Dependencies

```bash
pip install -r requirements.txt
Key libraries:

ultralytics – YOLOv8 implementation

opencv-python – Image processing

pandas – Excel and data manipulation

albumentations – Image augmentations

matplotlib – Data visualization (optional)
```

## 📂 Dataset

The dataset includes:

Annotated lake images in YOLO format.

Excel sheets with water level readings (timestamped).

Cropped images of detected water markers.

A CSV file mapping images to ground truth water levels.

## 📊 Results

The trained YOLO model achieves high precision in detecting water markers.

Cropped images are accurately aligned with corresponding water level data.

The dataset is ready for advanced ML tasks like regression or forecasting.

Future Improvements

Explore deep regression models to predict water level directly from images.

Add video frame extraction and real-time monitoring.

Improve augmentation pipelines for diverse environmental conditions.

Deploy the pipeline on edge devices for on-site monitoring.

## 📂 Related Projects / Skills

Object Detection

Data Augmentation

Time-Series Alignment

Supervised Learning

Environmental Monitoring

Python, YOLO, OpenCV, Pandas, Albumentations

