# **P**DF-RAG: A PDF-based Q&A System

## Overview

PDF-RAG is a retrieval-augmented generation (RAG) system designed for querying PDFs using OpenAI embeddings and FAISS. Users can input questions, and the system will retrieve relevant text from PDFs, highlight the corresponding sections, and display the results in a frontend.

## Features

- Extract and index text from PDF documents.
- Compute text embeddings using OpenAI API.
- Perform semantic search with FAISS to retrieve relevant text.
- Highlight the matched sentences in the frontend PDF viewer.



### Prerequisites

Ensure you have the following installed:

- Python 3.8+: [Download here](https://www.python.org/downloads/)
- Node.js (for frontend): [Download here](https://nodejs.org/en/download/)

### Backend Setup

1. Clone the repository:
   ```sh
   git clone https://github.com/micos-tfyxz/pdf-RAG.git
   cd pdf-RAG
   ```
2. Install required Python packages:
   ```sh
   pip install -r pip install numpy faiss openai nltk PyPDF2
   ```
3. Set up OpenAI API key:
   **For Linux/macOS (Bash):**
   ```sh
   export OPENAI_API_KEY="your-api-key-here"
   ```
   **For Windows (PowerShell):**
   ```powershell
   $env:OPENAI_API_KEY="your-api-key-here"
   ```
   **For Windows (CMD):**
   ```cmd
   set OPENAI_API_KEY=your-api-key-here
   ```
4. Run the backend:
   ```sh
   python pdfqa.py
   ```

### Frontend Setup

The frontend is provided as a static HTML file (`pdfqa.html`) that utilizes PDF.js. No additional installation is required.

1. Open the `pdfqa.html` file in a modern web browser:
   - Simply double-click the file

## Usage

### Querying PDFs

1. Open the frontend and upload a PDF.
2. Enter a query in the search bar.
3. The system retrieves relevant text and highlights the matched sections.

### Example

#### Load a PDF:

Here’s an example of how to use the tool:

Download a PDF file:

url:https://web.p.ebscohost.com/ehost/detail/detail?vid=0&sid=05c353a6-c3ec-49ed-bc47-81890ed1f59c%40redis&bdata=JkF1dGhUeXBlPWlwLHVpZCZzaXRlPWVob3N0LWxpdmU%3d#AN=160402029&db=keh

title: An investigation of the relationship between smartphone addiction and job performance of healthcare employees.

```python
bot.load_pdf("example.pdf") 
```

#### Query the document:

```python
results = bot.query_with_context("smartphone addicted harmful", top_k=2, 
                                     similarity_ratio=0.85, min_return_threshold=0.60)
```

#### Example Output:

```
Similarity Score: 0.644
"It is also reported that smartphone addiction causes accidents at home, workplace, and traffic..."
--------------------------------------------------
Similarity Score: 0.605
"One of the leading problems is smartphone addiction (nomophobia), which is associated with..."
--------------------------------------------------
```

## Project Structure

```
pdf-RAG/
│── backend/          # Backend code (Python, FastAPI)
│── frontend/         # Frontend code (React, pdf.js)
│── data/             # Sample PDFs
│── README.md         # Documentation
│── requirements.txt  # Python dependencies
│── .env.example      # Example environment variables
```

## Contributors

- **Youwei Wang**
- **Jie Ding** ([dingj@umn.edu](mailto\:dingj@umn.edu), GitHub: JieGroup)




