# Talk to your Doc with TinyLlama and FAISS
## Overview
### This project implements a question-answering system using TinyLlama and FAISS (Facebook AI Similarity Search) to process and query information from PDF documents. The system is split into two main components:
Embedding Generation and FAISS Database Creation
Query Processing with TinyLlama
### System Components
1. Embedding Generation and FAISS Database Creation
This component is responsible for:
Loading PDF documents
Splitting the documents into manageable chunks
Generating embeddings for these chunks
Creating and saving a FAISS index for efficient similarity search
#### Key Features:
Uses PyPDFDirectoryLoader to load multiple PDF files
Implements RecursiveCharacterTextSplitter for text chunking
Utilizes OpenAI's embedding model for generating embeddings
Creates a FAISS index for storing and searching embeddings
#### Process:
Load PDFs from a specified directory
Split the documents into chunks
Generate embeddings for each chunk
Create a FAISS index with these embeddings
Save the FAISS index for later use
2. Query Processing with TinyLlama
This component focuses on:
Loading the pre-generated FAISS index
Using TinyLlama model for processing queries
Retrieving relevant information from the FAISS index
Generating responses based on the query and retrieved information
#### Key Features:
Loads a pre-existing FAISS index
Implements TinyLlama (1.1B parameters) for natural language processing
Uses a retrieval-augmented generation approach for answering queries
#### Process:
Load the saved FAISS index
Initialize the TinyLlama model
Process user queries:
Perform similarity search in the FAISS index
Retrieve relevant document chunks
Use TinyLlama to generate a response based on the query and retrieved chunks
### Setup and Usage
#### Prerequisites
Python 3.7+
PyTorch
Transformers library
LangChain
FAISS-gpu

### Running the System
#### Embedding Generation:
Place your PDF files in the designated directory
Run the embedding generation script
The FAISS index will be saved to a specified location
#### Query Processing:
Run the query processing script
Input your questions when prompted
The system will provide answers based on the content of the PDFs
### Important Notes
The system uses local processing and doesn't require an internet connection after initial setup
TinyLlama is used as the language model, offering a balance between performance and resource requirements
The FAISS index allows for efficient similarity search without needing to reprocess the PDFs for each query
### Limitations
The accuracy of answers depends on the content of the PDFs and the capabilities of TinyLlama
Large PDF collections may require significant memory and processing power
