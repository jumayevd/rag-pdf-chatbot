PDF Chat with Gemini
A simple and powerful RAG (Retrieval-Augmented Generation) application that lets you chat with your PDF documents using Google Gemini AI.

Features

Upload PDF documents and ask questions about their content
Powered by Google Gemini AI (free tier)
Local embeddings using HuggingFace (no API quotas)
Clean and intuitive web interface built with Gradio
Fast document processing and retrieval
No complex authentication or setup required

Quick Start
1. Clone the repository
bashgit clone https://github.com/yourusername/pdf-chat-gemini.git
cd pdf-chat-gemini
2. Install dependencies
bashpip install -r requirements.txt
3. Get your Google API Key

Go to Google AI Studio
Sign in with your Google account
Click "Create API Key"
Copy the API key

4. Configure API Key
Replace "YOUR_API_KEY_HERE" in app.py with your actual Google API key:
pythonGOOGLE_API_KEY = "your_actual_api_key_here"
5. Run the application
bashpython app.py
The application will start and provide you with a local URL and a public Gradio link.
How It Works

Document Upload: Upload a PDF file through the web interface
Document Processing: The PDF is split into chunks and converted to embeddings using a local HuggingFace model
Vector Storage: Document chunks are stored in a Chroma vector database
Question Answering: Your questions are processed using retrieval-augmented generation with Google Gemini
Response: Get accurate answers based on your document content

Technology Stack

AI Model: Google Gemini 1.5 Flash
Embeddings: sentence-transformers/all-MiniLM-L6-v2 (local)
Vector Database: ChromaDB
Framework: LangChain
Interface: Gradio
PDF Processing: PyPDF

Configuration
Customizable Parameters
You can modify these settings in app.py:
python# Text splitting
chunk_size=1000          # Size of text chunks
chunk_overlap=200        # Overlap between chunks

# Retrieval
search_kwargs={"k": 3}   # Number of relevant chunks to retrieve

# LLM
temperature=0.3          # Response creativity (0-1)
max_tokens=512          # Maximum response length
API Costs

Gemini API: Free tier includes generous limits for text generation
Embeddings: Completely free (runs locally)
Vector Storage: Free (local ChromaDB)

Limitations

PDF files only (for now)
Requires internet connection for Gemini API calls
Local embeddings require ~80MB download on first run

Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
Development Setup

Fork the repository
Create a feature branch: git checkout -b feature-name
Make your changes and test
Submit a pull request

Roadmap

 Support for more document formats (DOCX, TXT)
 Conversation history
 Multiple document support
 Docker deployment option
 Batch processing capabilities

