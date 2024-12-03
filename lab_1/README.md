# Chromakey Implementation

This project provides two approaches to implementing the chromakey effect (commonly referred to as "green screen"):  
1. A manual implementation using pixel-by-pixel processing.  
2. An optimized implementation using OpenCV.  

Both methods replace a specific color in a foreground image with pixels from a background image.

---

## 📋 Features

- **Manual Chromakey**:
  - Implements pixel-by-pixel processing.
  - Utilizes Euclidean distance in RGB color space to detect and replace the key color.
- **OpenCV Chromakey**:
  - Efficient image processing with optimized algorithms.
  - Utilizes masking with color thresholds to identify and replace the key color.

---

## 🛠 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/chromakey-project.git
   cd chromakey-project
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## 🚀 Usage

1. Place your **foreground** and **background** images in the `images/` directory.
2. Update `foreground_path`, `background_path`, and `key_color` in the script if necessary.

3. Run python notebook:

4. Output images will be saved in the `results/` directory:
   - `manual.png` — result from the manual implementation.
   - `openCV.png` — result from the OpenCV implementation.

---

## 📊 Results

- **Performance Comparison**:
  - Manual method: ~0.6 seconds*.
  - OpenCV method: ~0.01 seconds*.
    * Depends on pc configuration

- **Output Quality**:
  Both methods produce comparable visual results.
  - FOREGROUND IMAGE
    
    ![Foreground](images/foreground.jpg)
  - BACKGROUND IMAGE
    
    ![Background](images/background.jpg)
  - MANUAL RESULT
    
    ![Manual result](results/manual.png)
  - OPENCV RESULT
    
    ![OpenCV result](results/openCV.png)

---

## 🧠 Theory

The chromakey process works as follows:
1. Identify a specific key color in the foreground image (e.g., green or white).
2. Replace pixels matching the key color with corresponding pixels from the background.
3. Composite the two images to create a seamless output.

### Algorithms:
- **Manual Implementation**:
  - Iterate over each pixel in the foreground.
  - Calculate the Euclidean distance between the pixel's color and the key color.
  - Replace pixels with a distance greater than the threshold.

- **OpenCV Implementation**:
  - Define color thresholds for the key color.
  - Create a binary mask to identify regions to replace.
  - Combine masked foreground and background using bitwise operations.

---

## 📁 Project Structure

```
lab_1/
│
├── images/
│   ├── foreground.jpg       # Foreground image
│   ├── background.jpg       # Background image
│
├── results/
│   ├── manual.png           # Output from the manual method
│   ├── openCV.png           # Output from the OpenCV method
│
├── chromakey.ipynb             # Main script
├── requirements.txt         # Dependencies
└── README.md                # Documentation
```

---

## 📚 References

- [OpenCV Documentation](https://opencv.org)
- [Pillow Documentation](https://python-pillow.org)
