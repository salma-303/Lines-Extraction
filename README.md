# ID Card Detection and Line Extraction

## Overview
This project involves detecting ID cards from images, aligning them correctly, and extracting key text information using OCR (Optical Character Recognition). The primary aim is to automate text extraction from ID cards for various applications such as data entry, verification, and analysis.

## Features
- **ID Card Detection:** Identifies the rectangular region corresponding to the ID card in the image.
- **Alignment Correction:** Ensures the ID card is properly oriented for text extraction.
- **Text Extraction:** Extracts specific details such as name, address, and ID number using Tesseract OCR with support for Arabic.
- **Visualization:** Displays various stages of processing including edges, contours, and extracted text regions.

## Prerequisites
Ensure you have the following dependencies installed:
- Python 3.x
- OpenCV
- NumPy
- Matplotlib
- Tesseract OCR and its Arabic language support

Install required Python libraries using pip:
```bash
pip install opencv-python-headless numpy imutils matplotlib pytesseract
```

For Tesseract OCR:
```bash
sudo apt-get install tesseract-ocr
sudo apt-get install tesseract-ocr-ara
sudo apt install libtesseract-dev
```

## Setup
1. Clone the repository or download the script.
2. Ensure the image you want to process is in the same directory as the script and named `test.jpeg`. Alternatively, modify the `image_path` variable to point to your image file.
3. Place the required Tesseract `.traineddata` files in the appropriate directory:
   ```bash
   sudo mv "/content/ara.traineddata" "/usr/share/tesseract-ocr/4.00/tessdata"
   sudo mv "/content/ara_combined.traineddata" "/usr/share/tesseract-ocr/4.00/tessdata"
   sudo mv "/content/ara_number.traineddata" "/usr/share/tesseract-ocr/4.00/tessdata"
   ```

## Usage
1. Run the script:
   ```bash
   python lines_extraction.py
   ```
2. The script will process the image through several stages:
   - Resize the image for processing.
   - Detect edges and contours to locate the ID card.
   - Align the ID card to correct its orientation.
   - Extract text from specific regions of the aligned image.

## Outputs
The script generates the following visualizations:
- **Original Image**: The input image as it is.
- **Edged Image**: The detected edges for contour extraction.
- **Image with Contour**: The original image annotated with the detected contour of the ID card.
- **Transformed Image**: The aligned image of the ID card.
- **Gray Transformed Image**: A grayscale version of the aligned image.
- **Binary Image**: A thresholded version of the image for OCR processing.

Extracted text is displayed in the terminal:
- Name
- Address
- National ID (NID)

## Reproducing Results
1. Replace `test.jpeg` with your own image of an ID card.
2. Ensure the image quality is high enough for edge and text detection.
3. Modify the text extraction logic in the `extract_Text` function to customize text regions or language settings.

## Troubleshooting
- **Cannot detect ID card edges:** Ensure the image is well-lit and has a clear view of the ID card.
- **Text extraction issues:** Verify that Tesseract OCR and the required language packs are properly installed.
- **Missing libraries:** Reinstall the prerequisites listed above.

## Additional Notes
- This script is designed for experimentation and may need fine-tuning for specific use cases.
- The default settings are optimized for ID cards with Arabic text but can be adapted for other languages.

---
