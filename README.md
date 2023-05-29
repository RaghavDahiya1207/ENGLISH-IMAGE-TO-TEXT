# ENGLISH-IMAGE-TO-TEXT
In this code we extract the ENGLISH text from the image.
!apt-get install tesseract-ocr
!pip install pytesseract

from google.colab import files

# Prompt the user to upload the image file
uploaded = files.upload()

# Get the file name
image_path = list(uploaded.keys())[0]

import pytesseract
from PIL import Image

# Open the image using PIL
image = Image.open(image_path)

# Set the path to the Tesseract executable (adjust according to your Colab environment)
pytesseract.pytesseract.tesseract_cmd = '/usr/bin/tesseract'
#custom_config = r'--oem 3 --psm 6 -l hin'
# Extract text from the image
extracted_text = pytesseract.image_to_string(image)

# Print the extracted text
print(extracted_text)
