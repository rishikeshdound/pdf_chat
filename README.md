# RAG Q&A App

## Overview
The **RAG Q&A App** is a Retrieval-Augmented Generation (RAG) system that allows users to ask questions based on provided documents, PDFs, text files, DOCX files, or web links. It utilizes **FAISS** for efficient vector-based search, **Hugging Face Transformers** for text embeddings, and **Meta LLaMA 3** as the large language model (LLM) to generate responses.

## Features
- Supports multiple input types: **Web links, PDFs, Text files, DOCX, and Plain Text**.
- Uses **FAISS** to store and retrieve vectorized document embeddings efficiently.
- Employs **Meta-LLaMA 3 (8B-Instruct)** model for generating answers.
- Leverages **Hugging Face Embeddings** for text processing.
- Built with **Streamlit** for an interactive and user-friendly interface.

## Installation
To run the project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate  
   venv\Scripts\activate 
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Add your **Hugging Face API key** in a `secret_api_keys.py` file:
   ```python
   HUGGINGFACE_API_KEY = "your_huggingface_api_key"
   ```

## Usage
To start the application, run:
```bash
streamlit run app.py
```

### Steps to Use the App:
1. Select the input type (**Link, PDF, Text, DOCX, TXT**).
2. Provide the required input (upload a file, enter a URL, or type text).
3. Click on **Proceed** to process the document and create a vectorstore.
4. Enter a query in the question box and click **Submit**.
5. The app will generate an answer using the retrieved document chunks and LLaMA-3.

## How It Works
1. **Document Processing:**
   - Based on the selected input type, the app reads and extracts text from different sources.
   - It splits the text into chunks of **1000 characters** with a **100-character overlap** for better context retrieval.
   - Uses `HuggingFaceEmbeddings` to generate vector representations of the text.
   
2. **Vector Storage & Retrieval:**
   - FAISS (Facebook AI Similarity Search) stores the text embeddings for fast retrieval.
   - The system retrieves the most relevant document chunks based on the user query.

3. **Question Answering:**
   - Uses **Meta-LLaMA 3** via Hugging Face API to process the retrieved text and generate an answer.
   - The temperature parameter is set to **0.6** for balanced responses.

## Dependencies
- `streamlit`
- `faiss`
- `numpy`
- `PyPDF2`
- `python-docx`
- `langchain`
- `Hugging Face Transformers`

## Future Improvements
- Support for more document formats (e.g., CSV, JSON).
- Implement a local LLM option for offline use.
- USE Better model for fast retrival and Processing
- Improve UI/UX with better file management.

## License
This project is licensed under the **MIT License**.

## Author
Developed by **Rishikesh Dound**.

