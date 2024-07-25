# PDF Conversational Retrieval Application

This application processes PDF files to enable conversational retrieval using large language models (LLMs). The implementation leverages LangChain and Chainlit libraries to provide an interactive chatbot that can answer questions based on the content of the uploaded PDF.

## Features

- **PDF Processing**: Extracts text from uploaded PDF files.
- **Text Splitting**: Splits extracted text into manageable chunks.
- **Embeddings**: Uses Ollama embeddings for text representation.
- **Vector Store**: Utilizes Chroma as a vector store for efficient retrieval.
- **Conversational Retrieval**: Implements a conversational chain with memory to provide context-aware answers.
- **Asynchronous Handling**: Handles file uploads and message processing asynchronously.

## Prerequisites

- Python 3.8 or higher
- Necessary Python packages (listed in `requirements.txt`)

## Installation

1. **Clone the Repository**:
   - Clone the repository from GitHub and navigate into the project directory.

2. **Install the Required Packages**:
   - Install all the necessary Python packages listed in the `requirements.txt` file.

## Configuration

- **Environment Variables**:
  - Ensure your `.env` file contains the necessary API keys and other environment variables required by the application.

## Usage

1. **Start the Application**:
   - Run the application using Chainlit. Ensure your `.env` file is correctly configured.

2. **Upload a PDF File**:
   - Upon starting the application, you will be prompted to upload a PDF file.
   - Make sure the file size is less than 100 MB.

3. **Ask Questions**:
   - Once the PDF is processed, you can interact with the chatbot by asking questions related to the content of the PDF.
   - The chatbot will provide answers along with references to the relevant sections of the PDF.

## Code Workflow

1. **Import Libraries**:
   - The necessary libraries and modules such as PyPDF2, LangChain components, and Chainlit are imported.

2. **Initialize the Language Model**:
   - The application initializes the LLM using the ChatOllama model. An alternative model, ChatGroq, can be configured if needed.

3. **Chat Start Handler**:
   - Upon starting a chat session, the application waits for the user to upload a PDF file.
   - Once a file is uploaded, the application processes the PDF by extracting text from its pages.

4. **Text Splitting**:
   - The extracted text is split into manageable chunks for better processing and retrieval.

5. **Create Metadata**:
   - Metadata is created for each text chunk to facilitate efficient retrieval.

6. **Create a Vector Store**:
   - A Chroma vector store is created using the Ollama embeddings model to store the text chunks and their metadata.

7. **Initialize Message History**:
   - A message history is maintained to keep track of the conversation context.

8. **Set Up Conversational Chain**:
   - A conversational retrieval chain is set up using the initialized LLM and the Chroma vector store, with memory to provide context-aware responses.

9. **Handle User Messages**:
   - When the user sends a message, the application processes it through the conversational chain to generate a response.
   - The response includes the answer and references to the source documents from the PDF.

## Additional Notes

- **Environment Variables**:
  - The application loads environment variables automatically using a `.env` file. Ensure this file contains all the necessary API keys and configurations.
  
- **PDF Processing**:
  - The application is designed to handle PDF files and extract their textual content for further processing.

- **Model Configuration**:
  - The default model used is ChatOllama with the "mistral" configuration. An alternative configuration using ChatGroq can be enabled if needed.

- **File Size Limit**:
  - The application imposes a file size limit of 100 MB for uploaded PDFs.

## Authors

Best regards from the authors.
yassine.gannoune@usmba.ac.ma
