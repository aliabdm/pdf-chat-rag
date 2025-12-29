📄 Chat with Your PDF - RAG Application
Transform any PDF into an interactive conversation! Upload your documents and ask questions in natural language powered by cutting-edge AI technology.
Show Image
Show Image
Show Image
Show Image
🌟 Live Demo
Try it here! (Add your Streamlit Cloud link after deployment)
✨ Features

📤 Upload Any PDF - Research papers, books, reports, manuals
💬 Natural Conversations - Ask questions like you're talking to a human
⚡ Lightning Fast - Powered by Groq's ultra-fast LLM inference
🎯 Accurate Answers - RAG ensures responses are grounded in your document
🎨 Beautiful Interface - Clean, intuitive design built with Streamlit
🔒 Privacy First - Process documents locally, no data stored

🛠️ Tech Stack
TechnologyPurposeWhy We Chose ItLangChainRAG FrameworkIndustry-standard for building LLM apps with document retrievalGroqLLM Inference10x faster than traditional inference, free tier availableFAISSVector SearchFacebook's efficient similarity search libraryStreamlitUI FrameworkRapid prototyping with beautiful Python-based interfacesHuggingFaceEmbeddingsOpen-source sentence transformers for text vectorization
🚀 Quick Start
Prerequisites

Python 3.8 or higher
Groq API key (Get one free here)

Installation

Clone the repository

bashgit clone https://github.com/aliabdm/pdf-chat-rag.git
cd pdf-chat-rag

Create virtual environment

bashpython -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate

Install dependencies

bashpip install -r requirements.txt

Run the application

bashstreamlit run app.py

Open your browser
Navigate to http://localhost:8501

📖 How It Works
The RAG Pipeline
PDF Upload → Text Extraction → Chunking → Embedding → Vector Store
                                                            ↓
User Question → Embedding → Similarity Search → Context Retrieval
                                                            ↓
                                        Context + Question → LLM → Answer
Step-by-Step Process

Document Processing

Extract text from PDF using PyPDF2
Split into manageable chunks (1000 chars with 200 overlap)
Convert chunks to vector embeddings using HuggingFace


Vector Storage

Store embeddings in FAISS for fast similarity search
Enable quick retrieval of relevant document sections


Query Processing

Convert user question to embedding
Find top-3 most similar document chunks
Pass context to LLM with original question


Answer Generation

Groq's LLM generates contextual response
Answers grounded in document content
Fast inference (typically under 2 seconds)



💡 Example Use Cases
Academic Research
"What are the main findings of this research paper?"
Legal Documents
"What does section 5 say about liability?"
Technical Manuals
"How do I troubleshoot error code E404?"
Business Reports
"Summarize Q3 financial performance"
🔧 Configuration
Customize Chunk Size
pythontext_splitter = RecursiveCharacterTextSplitter(
    chunk_size=1000,  # Adjust based on your documents
    chunk_overlap=200  # Balance between context and uniqueness
)
Change LLM Model
pythonllm = ChatGroq(
    model_name="llama-3.3-70b-versatile",  # Try other Groq models
    temperature=0  # 0 for factual, higher for creative
)
Adjust Retrieval
pythondocs = vector_store.similarity_search(
    question, 
    k=3  # Number of chunks to retrieve
)
📊 Performance

Processing Time: ~10-30 seconds for typical PDFs
Query Response: ~1-3 seconds per question
Memory Usage: Scales with document size
Accuracy: High for factual questions, context-dependent

🎯 Roadmap

 Support for multiple file formats (DOCX, TXT, etc.)
 Conversation history persistence
 Multi-document chat
 Export chat transcripts
 Advanced filtering options
 API endpoint for integration

🤝 Contributing
Contributions are welcome! Feel free to:

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

LangChain for the powerful RAG framework
Groq for ultra-fast LLM inference
Streamlit for the amazing UI framework
Facebook AI for FAISS vector search
HuggingFace for open-source embeddings

📧 Contact
Mohammad Ali Abdul Wahed

⭐ If you find this project helpful, please give it a star! ⭐
Built with ❤️ using Python, LangChain, and Groq