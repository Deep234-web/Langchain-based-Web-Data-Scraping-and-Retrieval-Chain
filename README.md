# Langchain-based-Web-Data-Scraping-and-Retrieval-Chain

# 1) OPENAI - Langchain-based Web Data Scraping and Retrieval Chain

## Project Overview

This project demonstrates a web data scraping pipeline using Langchain, followed by document chunking, vector embeddings, and retrieval for generating responses based on contextual information from scraped web data.

Key features include:
- Web scraping using Langchain document loaders.
- Text splitting and chunking for processing large documents.
- Embedding generation using OpenAI's GPT-4 model.
- Vector store setup for efficient information retrieval.
- Retrieval chain to generate LLM responses based on context.

## Key Components

1. **Environment Setup**:
   - Uses environment variables for managing API keys and LangSmith tracing:
     - `OPENAI_API_KEY`
     - `LANGCHAIN_API_KEY`
     - `LANGCHAIN_PROJECT`
   - LangSmith tracing is enabled to track the API usage.

2. **Web Scraping**:
   - Scrapes data from a webpage using `WebBaseLoader`:
     - Example: `https://docs.smith.langchain.com/tutorials/Administrators/manage_spend`
   - Loads the data into documents.

3. **Text Chunking**:
   - Uses `RecursiveCharacterTextSplitter` to split large documents into smaller chunks.
   - This enables efficient processing for embedding and retrieval.

4. **Embedding Generation**:
   - Generates embeddings using OpenAI's `ChatOpenAI` (GPT-4) model for vectorizing text chunks.

5. **Document Chain**:
   - Constructs a document chain using `create_stuff_documents_chain` to handle questions and generate responses based on document context.
   - A custom prompt template is used to ensure the LLM answers based only on the provided context.

6. **Vector Store**:
   - Retrieves information using a vector store that serves as a retriever for the LLM.

7. **Retrieval Chain**:
   - Combines the retriever and document chain to form a retrieval chain that takes user input and generates context-based answers.
  

# 2) Langchain Ollama Llama2 Model (Gemma)

## Project Overview

This project is a simple demonstration of using Langchain with the Ollama model `gemma:2b` within a Streamlit interface. It allows users to ask questions, and the app responds with answers generated by the Llama2 model using a custom prompt template.

## Key Features

1. **Langchain Integration**:
   - Uses Langchain to create a prompt template and manage the interaction between the user input and the LLM.
   - Includes LangSmith tracking for API usage and tracing.

2. **Ollama Model**:
   - Leverages the `gemma:2b` model from Ollama for generating responses to user questions.

3. **Streamlit Interface**:
   - Provides a simple and interactive UI where users can input their questions and see the generated responses in real-time.

## Key Components

1. **Environment Setup**:
   - Uses environment variables to configure LangSmith tracking:
     - `LANGCHAIN_API_KEY`
     - `LANGCHAIN_PROJECT`
   - These keys enable tracing and usage tracking for the Langchain API.

2. **Prompt Template**:
   - Constructs a conversational prompt template using `ChatPromptTemplate`:
     - The system message sets the context: "You are a helpful assistant."
     - The user message is dynamically filled with the question entered in the Streamlit input box.

3. **LLM (Ollama - Gemma)**:
   - Uses the Ollama model `gemma:2b` to generate answers based on the user's question.
   - The LLM is integrated into the Langchain workflow using a pipe (`|`) to handle chaining of prompt, LLM, and output parsing.

4. **Streamlit UI**:
   - A minimal web application built using the Streamlit framework:
     - The user enters their question into a text input field.
     - The app processes the question and generates an answer using the LLM.
     - The response is displayed on the webpage.

