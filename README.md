## Text Reader (GUI OCR with ROI & Camera Support)

A graphical OCR application built using Tkinter, OpenCV, and PyTesseract. It provides:

- Opening images from your computer
- Live video capture with start/stop controls
- Click-and-drag region-of-interest (ROI) selection
- OCR processing on either the whole frame or the chosen ROI
- Visual overlay showing detected text bounding boxes
- A scrollable panel to display extracted text

### Requirements

- Python 3.12+ (matches the project’s virtual environment)
- Tesseract OCR installed and accessible via the system PATH (`tesseract`)
- Tkinter (typically bundled with standard Python installations)
- Python packages: `opencv-python`, `pytesseract`, `Pillow`, `numpy`

  - These are already included in the provided `venv`. If installing manually:

    ```bash
    pip install opencv-python pytesseract Pillow numpy
    ```

### Running the Program

```bash
python text-reader.py
```

### How to Use

1. Start the application.
2. Pick a source:

   - **Load Image** to open an existing file, or
   - **Start/Resume Camera** to use your webcam (stop it with **Stop Camera**).

3. (Optional) Select an ROI by dragging on the image. Use **Clear ROI** to remove it.
4. Press **Run OCR** to extract text.

   - Detected regions are outlined in green and labeled.
   - The recognized text appears in the bottom panel.

5. If nothing is detected, try better lighting, move closer, or choose a larger ROI.

### Additional Notes

- Uses bilateral filtering and adaptive thresholding before OCR; Tesseract runs with `--psm 6`.
- The overlay is drawn on the most recent frame. After OCR, the live view is paused—click **Start/Resume Camera** to continue streaming.
