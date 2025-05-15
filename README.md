# AI-Powered Q&A Bot with Google Gemini (RAG)

This project implements a Retrieval Augmented Generation (RAG) system that allows you to chat with your own documents (PDFs and TXT files). It uses Google Gemini for both embedding generation and language understanding, orchestrated by the LangChain library.

## Features

*   Loads text from local PDF and TXT files.
*   Splits documents into manageable chunks.
*   Generates embeddings for document chunks using Google Gemini's `models/embedding-001`.
*   Stores embeddings in a local FAISS vector store for efficient retrieval.
*   Uses a Google Gemini chat model (e.g., `models/gemini-1.5-flash-latest` or `models/gemini-1.5-pro-latest`) to answer questions based on retrieved document context.
*   Interactive command-line interface for asking questions.

## Prerequisites

*   Python 3.8 or newer
*   A Google Cloud Project with billing enabled (or sufficient free trial credits for the Generative Language API).
*   A Google AI Studio API Key (or a Google Cloud API key with the "Generative Language API" or "Vertex AI API" enabled).

## Setup

1.  **Clone the Repository (or Create Project Folder):**
    If this were a git repository:
    ```bash
    git clone <your-repo-url>
    cd my_rag_bot
    ```
    Otherwise, ensure you have the project files in a directory named `my_rag_bot`.

2.  **Create and Activate a Virtual Environment:**
    ```bash
    python -m venv venv
    ```
    *   On Windows:
        ```bash
        venv\Scripts\activate
        ```
    *   On macOS/Linux:
        ```bash
        source venv/bin/activate
        ```

3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    (You'll need to create a `requirements.txt` file. See section below.)

4.  **Set Up API Key:**
    *   Create a file named `.env` in the project root (`my_rag_bot/`).
    *   Add your Google API key to it:
        ```env
        GOOGLE_API_KEY="YOUR_GOOGLE_API_KEY_HERE"
        ```
    *   Replace `"YOUR_GOOGLE_API_KEY_HERE"` with your actual API key.

5.  **Prepare Your Documents:**
    *   Create a subfolder named `data` inside your `my_rag_bot` project directory.
    *   Place the PDF (`.pdf`) or Text (`.txt`) files you want to query into this `data/` folder.

## `requirements.txt`

Create a `requirements.txt` file in the project root with the following content:

```txt
langchain
langchain-google-genai
faiss-cpu
pypdf
python-dotenv
google-generativeai
