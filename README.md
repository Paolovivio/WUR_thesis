# WUR Thesis

This project contains Jupyter notebooks developed for my Wageningen University & Research (WUR) thesis.  
It focuses on image-based cucumber width measurement and machine learning analysis to detect infections.  
The workflow covers everything from raw image cropping to feature extraction, data labeling, visualization, and model evaluation.

---

## Project Structure & Workflow

### Step 1 — Crop Images
Use **`save_image_cropped.ipynb`** to crop the images coming directly from the camera.  
Set your desired output folder inside the notebook.

---

### Step 2 — Extract Width Measurements
Use **`image_width_extraction_skeleton_on_distance_transform_on_20140520_and_20140415.ipynb`** to extract cucumber widths from cropped images and save the results as `.txt` files.

If you used **SAM (Segment Anything Model)** for image segmentation beforehand, instead use:

- `Width_extraction_after_SAM_2005.ipynb`
- `Width_extraction_after_SAM_2014.ipynb`
- `Width_extraction_after_SAM_2025.ipynb`

⚠ **Note:** Pay attention to the orientation of the cucumber, as the code is sensitive to it.

---

### Step 3 — Merge Width Data
Use **`merge_file_txt.ipynb`** to combine all generated `.txt` files into a single dataset.

---

### Step 4 — Label Data
Manually label the cucumbers in the dataset:

- `1` = infected  
- `0` = not infected  

Add this label column to the **last row** of the merged CSV file.

---

### Step 5 — Visualize Data
Use **`plot_width.ipynb`** to visualize the width data and inspect trends.

---

### Step 6 — Train & Test Machine Learning Models
- **`test_AI_models_single_df.ipynb`** → Test the model using a single DataFrame.  
- **`test_AI_models_3_df.ipynb`** → Test the model using three DataFrames for improved accuracy.

---

### Step 7 — Compare Processing Speeds (SAM vs. Non-SAM)
If you want to check the difference in processing time between the SAM-based and non-SAM approaches, use:

- `Width_extraction_after_SAM_2014_time_mesured.ipynb`
- `image_width_extraction_skeleton_on_distance_transform_on_20140520_and_20140415_time_processed_mesured.ipynb`
- This code `t.test_on_time_processing.ipynb` for a t-student analysis of the results.
---
