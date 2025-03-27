# Resume Paser Using BERT

This project provides a tool to assess the compatibility of a resume with a given job description using a BERT-based model. The tool calculates a compatibility score based on semantic similarity between the resume and job description. It features a simple GUI for ease of use.

## Features

- **Resume Compatibility**: Matches a resume against a job description using a pre-trained BERT model.
- **GUI Interface**: Built with Tkinter for user-friendly interactions, allowing users to upload resumes and enter job descriptions.
- **Text Extraction**: Extracts text from resumes in various formats, including `.pdf`, `.txt`, `.jpg`, `.jpeg`, `.png`.
- **BERT Embeddings**: Uses BERT to compute text embeddings for semantic similarity.

## Requirements

- Python 3.7+
- Libraries:
  - `torch`
  - `transformers`
  - `textract`
  - `pytesseract`
  - `PIL`
  - `tkinter`
  
Install the required libraries with the following command:

```bash
pip install torch transformers textract pytesseract Pillow
```

If you're running this code in Google Colab, use the following commands to install the necessary dependencies:

!pip install transformers torch pytesseract textract Pillow

 # Files

 - main_model.py
 -> Contains the core functionality for:

**Preprocessing Text**: Converts text to lowercase, removes extra spaces, and non-alphanumeric characters.

**Text Extraction**: Extracts text from .pdf, .txt, and image formats (.jpg, .png).

**BERT Embedding**: Uses the pre-trained bert-base-uncased model to generate embeddings for the resume and job description.

**Compatibility Scoring**: Calculates cosine similarity between the embeddings of the resume and job description to generate a compatibility score.

 - gui.py
 -> Provides a simple graphical interface for:

Uploading resume files.

Entering job descriptions.

Displaying the calculated compatibility score between the resume and job description.

# Usage

**Step 1: Launch the GUI**

To run the tool, execute the gui.py script. It will open a window where you can:

Select a Resume File: Upload a resume file (supports .pdf, .txt, .jpg, .jpeg, .png).

Enter Job Description: Paste or type the job description in the provided text box.

Calculate Compatibility: Click the "Calculate Score" button to compute the compatibility score between the resume and job description.
The compatibility score will be displayed as a percentage.

**Step 2: Running in Colab**
If you're running the code in Google Colab:

Upload the parser_main_.py file to Colab.

Run the following in a code cell:

import sys

sys.path.append('/content')

import main_model

Alternatively, use the %run magic command to execute the parser_main.py file:

```bash
%run parser_main.py as main_model
```

Then you can call functions from parser_main within your Colab environment.

**Example**

Select Resume File: Upload resume.pdf or any supported format.

Enter Job Description: Paste a job description like:

We are looking for a software engineer with experience in Python, machine learning, and natural language processing.

Calculate Score: After clicking the button, the compatibility score will be displayed, showing how well the resume matches the job description.

**Contributions**

Feel free to fork this repository, open issues, or submit pull requests. Contributions are welcome!

**License**

This project is licensed under the Apache License 2 - see the LICENSE file for details.

**Acknowledgements**

The BERT model and tokenizer are provided by the Transformers library by Hugging Face.
pytesseract for OCR (Optical Character Recognition) to extract text from image files.
textract for extracting text from PDF and text files.
