PDF Document OCR & Classification Tool:

This Python script extracts text from scanned PDF documents by converting them into images, preprocessing them for clarity, and using OCR (Optical Character Recognition) to extract and classify the content. It also identifies the type of document (e.g., Family Certificate, Nikahnama, etc.) and displays the extracted text in a readable table format. This was a personal project to identify and detect scanned documents; however there are issues with table detection so that will be added to a future to-do lisy.

🔧 Features

1. Convert PDF pages to images using Poppler

2. Detect and enhance blurry or low-contrast images

3. Apply image preprocessing for better OCR accuracy

4. Extract text using Tesseract OCR

5. Automatically classify document types (e.g., Family Certificate, Nikahnama in this case)

6. Display extracted text in a terminal-based table

7. Show the preprocessed image for visual confirmation

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

pdf_path = r"C:\Path\To\Your\PDF\file.pdf"
image_output_dir = r"C:\Path\To\Save\Images"

Then run the script:

python main.py

The script will:

1. Convert the first page of the PDF to an image

2. Preprocess the image for better OCR

3. Extract and display the text

4. Identify and print the document type

S5. how the preprocessed image in a popup window


📝 Notes

1. Only the first page of the PDF is processed. You can modify the loop to handle multiple pages.

2. Tune the blur_threshold and CLAHE values if results aren't accurate for your documents.

3. For non-English documents, change the Tesseract language using lang="eng" to another (e.g., "urd" for Urdu).
