# 🚗 Vehicle Detector & Counter

This project detects and counts vehicles from a video feed using **OpenCV** and **Background Subtraction (MOG)**.  
It tracks vehicles as they cross a predefined line and maintains a running total in real-time.


## 📌 Features
- Detects moving vehicles from video footage.
- Counts vehicles crossing a specific line.
- Displays results using both OpenCV and Matplotlib.
- Assigns unique IDs to detected vehicles for tracking.
- Configurable detection parameters (minimum size, line position, tolerance).

## 📂 Project Structure


Vehicle-Detector-/
│── vehicle.py          # Main Python script
│── vehicle counter/
│   └── video.mp4        # Sample video file for detection
│── README.md            # Project documentation


## 🛠️ Requirements
Install dependencies:
```bash
pip install opencv-python opencv-contrib-python matplotlib numpy


**Note:** `opencv-contrib-python` is needed for `cv2.bgsegm` (BackgroundSubtractorMOG).


## ▶️ Usage

1. Clone the repository:

```bash
git clone https://github.com/Aaronrao989/Vehicle-Detector-.git
cd Vehicle-Detector-
```

2. Place your video file in the `vehicle counter/` folder
   (or update `file_path` in `vehicle.py` to match your video location).

3. Run the script:

```bash
python vehicle.py
```

4. Controls:

   * Press **`q`** in the OpenCV window to exit.
   * Click anywhere in the Matplotlib window to stop.

---

## ⚙️ Configuration

You can tweak these variables in `vehicle.py`:

```python
min_width_react = 80    # Minimum vehicle width
min_height_react = 80   # Minimum vehicle height
count_line_position = 550  # Position of counting line
offset = 6              # Error margin for line crossing detection
```

---

## 📸 Example Output

**Vehicle detection with counting line and bounding boxes:**

*(Add a screenshot here once you run the script and capture an example)*

---

## 📖 How It Works

1. **Video Capture** – Loads video file using OpenCV.
2. **Background Subtraction** – Uses `cv2.bgsegm.createBackgroundSubtractorMOG()` to detect moving objects.
3. **Morphological Operations** – Cleans up noise with dilation and closing.
4. **Contour Detection** – Finds bounding boxes for moving objects.
5. **Line Crossing Logic** – Increments counter when an object’s center crosses the counting line.
6. **Display** – Shows live video feed and counter using OpenCV + Matplotlib.

---

## 🏗️ Future Improvements

* Replace background subtraction with **YOLOv8** or **DeepSORT** for more accurate detection and tracking.
* Add speed estimation for each vehicle.
* Integrate into a **Streamlit** web app for easy deployment.
