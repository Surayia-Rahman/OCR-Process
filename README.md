PDF Document OCR & Classification Tool
This Python script extracts text from scanned PDF documents by converting them into images, preprocessing them for clarity, and using OCR (Optical Character Recognition) to extract and classify the content. It also identifies the type of document (e.g., Family Certificate, Nikahnama, etc.) and displays the extracted text in a readable table format.

🔧 Features
Convert PDF pages to images using Poppler

Detect and enhance blurry or low-contrast images

Apply image preprocessing for better OCR accuracy

Extract text using Tesseract OCR

Automatically classify document types (e.g., Family Certificate, Nikahnama)

Display extracted text in a terminal-based table

Show the preprocessed image for visual confirmation

📁 Project Structure
bash
Copy
Edit
project/
│
├── main.py                  # Main script (the one you're reading about)
├── README.md                # This file
├── requirements.txt         # Dependencies (optional)
└── images_output/           # Folder to store converted images from PDF
🛠️ Setup Instructions
1. Install Dependencies
First, ensure Python 3 is installed. Then, install the required packages:

bash
Copy
Edit
pip install opencv-python pytesseract pdf2image pillow tabulate numpy
2. Install Tesseract OCR
Download from: https://github.com/tesseract-ocr/tesseract

Add Tesseract's path to your system's environment variables

3. Install Poppler for Windows
Download from: https://github.com/oschwartz10612/poppler-windows/releases/

Extract it and note the path (e.g., C:\Program Files\poppler-xx\Library\bin)

Replace this path in the script under poppler_path

🧪 How to Run
Update the following paths in the script:

python
Copy
Edit
pdf_path = r"C:\Path\To\Your\PDF\file.pdf"
image_output_dir = r"C:\Path\To\Save\Images"
Then run the script:

bash
Copy
Edit
python main.py
The script will:

Convert the first page of the PDF to an image

Preprocess the image for better OCR

Extract and display the text

Identify and print the document type

Show the preprocessed image in a popup window

📄 Example Output
sql
Copy
Edit
Processing the first image: page_1.png
Image is blurry, enhancing sharpness...
Applying denoising...
Enhancing contrast...
Applying adaptive thresholding...
Identified Document Type: MARRIAGE CERTIFICATE

Extracted Text Table:
+------------------------+
| Extracted Text         |
+------------------------+
| Name: John Doe         |
| Date: 01/01/2020       |
| ...                    |
+------------------------+
📝 Notes
Only the first page of the PDF is processed. You can modify the loop to handle multiple pages.

Tune the blur_threshold and CLAHE values if results aren't accurate for your documents.

For non-English documents, change the Tesseract language using lang="eng" to another (e.g., "urd" for Urdu).
