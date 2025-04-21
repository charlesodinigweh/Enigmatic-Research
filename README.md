# Enigmatic-Research
Multimodal Document Retrieval and Question Answering using Nomal Embedding and Vector Embedding

Project Summary
This project demonstrates how to build a retrieval-augmented generation (RAG) system using Google Gemini's embedding and generation APIs. It extracts text from various file formats (PDFs, Word, Excel, and Images), stores them in a vector database (ChromaDB), generates embeddings using Gemini's text-embedding-004 model, and finally enables question answering using a conversational prompt with Gemini.

Key Features
- Multimodal File Handling: Extracts content from .docx, .pdf, .xlsx, and image files.

- Semantic Search: Uses Gemini's embeddings to convert content into dense vector representations.

- Vector Database Integration: Stores embeddings in a ChromaDB collection and allows semantic querying.

- Conversational Answer Generation: Uses Gemini to return friendly and informative answers based on the retrieved content.

Technologies Used
- Google GenAI API – For embedding and generation (Gemini models)

- ChromaDB – Lightweight local vector database for document search

- pdfplumber, docx, pytesseract, Pillow – For reading from PDFs, Word, images

- pandas – Reading Excel files

- IPython.display.Markdown – For cleaner answer display in notebooks or REPL


Setup

Install Dependencies:
pip install 
- google-generativeai 
- chromadb 
- pdfplumber 
- python-docx
- pytesseract 
- pandas 
- openpyxl 
- Pillow

Set up Gemini API: Replace the placeholder with your actual Google GenAI API key:

GOOGLE_API_KEY = 'YOUR_API_KEY'


Prepare Data: 
Ensure you have a .zip file (X_Files.zip) with various documents stored in it. The script will unzip this into EnigmaticDatasets.

Supported File Formats

Format	Tool Used
.pdf	pdfplumber
.docx	python-docx
.xlsx	pandas.read_excel
.jpg/.png	pytesseract


How It Works
- Step 1: Unzipping and Extracting Documents
All files inside X_Files.zip are extracted and processed by type. Their text contents are stored in a Python dictionary.

- Step 2: Embedding with Gemini
Each document is passed through GeminiEmbeddingFunction, generating embeddings via text-embedding-004. These are stored in ChromaDB with unique IDs.

- Step 3: Querying with Natural Language
A query like "Please give an example of loan analysis" is vectorized and used to search ChromaDB. Top-matching documents are retrieved.

- Step 4: Answer Generation
The retrieved documents are appended to a contextual prompt, and Gemini generates a complete, user-friendly answer.


Example Query
query = "Please give an example of loan analysis"
Expected Output: A detailed answer using relevant documents retrieved from your dataset.

Important Notes
- Avoid using your Google API key in public repositories.

- Ensure Tesseract is installed and configured for OCR (pytesseract requires it).


Future Enhancements
- Add web UI using Streamlit or Gradio

- Support for audio and video file transcripts

- Connect to cloud-hosted vector databases (e.g., Pinecone, Weaviate)


