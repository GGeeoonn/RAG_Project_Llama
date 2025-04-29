# RAG-Based Application with LLaMA 3.1

This repository contains a Retrieval-Augmented Generation (RAG) application built using LLaMA 3.1 and Ollama. The application processes PDFs, creates a FAISS index for efficient document retrieval, and uses LLaMA 3.1 to generate answers based on the retrieved information.

## Features

- Converts PDF documents into text format.
- Creates a FAISS index from the text files.
- Uses the LLaMA 3.1 model via Ollama to answer questions based on retrieved documents.
- Allows querying in real-time through the terminal.

## Prerequisites

- Python 3.11 or later
- Ollama installed on your machine
- Required Python packages (see Installation section)

## Installation

1. Install the required Python packages:

    ```bash
    pip install -r total_requirements.txt
    ```

2. Install Ollama from [official Ollama website](https://ollama.com/).

3. Pull the LLaMA 3.1 model using Ollama:

    ```bash
    ollama pull llama3.1
    ```

## PDF to Text Conversion

To convert your PDFs into text files, run the `pdf_to_text.py` script. Make sure your PDF files are placed in the `Data/` folder.

Usage:

```bash
python pdf_to_text.py
```

This will convert all PDF files in the `Data/` folder and store the text files in the `DataTxt/` folder.

## Creating the FAISS Index

Run the `txt_to_index.py` script to generate the FAISS index from the text files in the `DataTxt/` folder.

Usage:

```bash
python txt_to_index.py
```

This will create a FAISS index and save it in the `DataIndex/` folder.

## Running the LLaMA 3.1 Model with Ollama

To use the LLaMA 3.1 model for question answering, you need to run Ollama with the LLaMA model. You can either directly run:

```bash
ollama run llama3.1
```

## Running the RAG System

The main script for running the RAG-based question-answering system is `main.py`. This script retrieves relevant documents using the FAISS index and generates answers using LLaMA 3.1.

Usage:

```bash
python main.py
```

The system will prompt you to ask a question. You can type your questions in the terminal and get answers based on the documents in the FAISS index. To exit, type `exit`.
