
-----

# PyQt5 Printed Text Scanner (OCR)

This is a GUI application built using Python, PyQt5, OpenCV, and PyTesseract. It allows users to capture an image from a live camera feed or load an image file, select a Region of Interest (ROI), and perform Optical Character Recognition (OCR) to extract text.

## ✨ Features

  * **Live Camera Input:** Real-time video display.
  * **Image Capture/Load:** Capture frames from the camera or load images from disk.
  * **ROI Selection:** Draw a rectangle directly on the image to specify the area for OCR.
  * **PyTesseract Integration:** Uses the powerful Tesseract engine for text extraction.
  * **Overlay Preview:** Displays bounding boxes around detected text on the original image.
  * **Non-blocking Camera:** Uses PyQt5's `QTimer` for smooth video display.

## 🛠️ Prerequisites

You must have the **Tesseract OCR Engine** installed on your operating system, as this is an external dependency required by the `pytesseract` Python library.

### 1\. Install Tesseract OCR

Download and install the Tesseract executable for your operating system (e.g., from the [Tesseract GitHub](https://github.com/tesseract-ocr/tesseract)).

**❗️ CRITICAL STEP FOR WINDOWS USERS:**

Since the provided code uses a specific path, the Tesseract executable must be installed here:

```
C:\Program Files\Tesseract-OCR\tesseract.exe
```

If you installed Tesseract to a different location, you **MUST** update the following line in the `ocr_scanner.py` script:

```python
# Change this path if your installation location is different!
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
```

## 📦 Installation (Python Dependencies)

Based on your provided `pip list`, the required dependencies are:

### 1\. Create a Virtual Environment (Recommended)

```bash
# Create a new environment
python -m venv venv

# Activate the environment
# Windows:
.\venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate
```

### 2\. Install Dependencies

You can install all necessary Python packages using the following command:

```bash
pip install opencv-python PyQt5 pillow pytesseract numpy
```

*(Note: `packaging`, `pip`, `PyQt5-Qt5`, and `PyQt5_sip` are automatically managed or installed alongside these main packages.)*

## ▶️ How to Run the Application

1.  **Save the Code:** Save the provided Python script as `ocr_scanner.py` (or any name you prefer).

2.  **Ensure Configuration:** Verify that the Tesseract path inside the script is correct for your system.

3.  **Execute:** Run the script from your terminal:

    ```bash
    python ocr_scanner.py
    ```

### Usage Steps:

1.  **Start Camera:** Click the **"Start Camera"** button to view the live video feed.
2.  **Capture Frame:** Click **"Capture Frame"** to freeze the image. *(Alternatively, use **"Load Image"** to open a file).*
3.  **Select ROI (Optional but Recommended):** Click and drag the mouse over the text region you want to scan. A red dashed box indicates the selected ROI.
4.  **Run OCR:** Click the **"Run OCR"** button.
      * The extracted text will appear in the right-hand text area.
      * The image display will update to show green bounding boxes around the detected words.
5.  **Save Overlay:** Click **"Save Overlay"** to save the image with the detection boxes drawn on it.
6.  **Reset:** Click **"Clear ROI"** to remove the selection box, or **"Start Camera"** again to refresh the image source.