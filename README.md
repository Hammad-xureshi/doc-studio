AI DOCUMENT STUDIO
Technical Documentation & Architecture Report
Version:	3.0 LUXE
Developer:	Hammad Naeem
Technology:	Python, Streamlit, Google Gemini AI
Date:	November 2025
Status:	Production Ready
EXECUTIVE SUMMARY
AI Document Studio is an intelligent document processing and analysis platform that combines cutting-edge artificial intelligence with multi-format document support. The system leverages Google's Gemini AI to provide semantic search, automated summarization, study material generation, and interactive Q&A; capabilities. Designed for both enterprise and educational use cases, it supports bilingual operations (English and Roman Hinglish) and offers a comprehensive suite of tools for document intelligence.
Key Features
•	Multi-format document processing (PDF, DOCX, XLSX, PPTX, TXT)
•	AI-powered semantic search using vector embeddings
•	Automated content summarization and note generation
•	MCQ and flashcard creation for study purposes
•	Interactive chat interface with context-aware responses
•	Bilingual support (English and Roman Hinglish)
•	Real-time analytics and visualization
•	Secure session management and data handling
TECHNOLOGY STACK OVERVIEW
Category	Technology	Version/Type	Purpose
Framework	Streamlit	Latest	Web Application UI
AI Engine	Google Gemini	1.5 Flash/Pro	Text Generation & Embeddings
Vector DB	ChromaDB	Latest	Semantic Search
Document Processing	PyPDF2, python-docx, openpy	xl, python-pptxLatest	Multi-format Support
Visualization	Plotly	Latest	Interactive Charts
Data Processing	Pandas	Latest	Data Manipulation
Security	python-dotenv	Latest	Environment Management
 
DETAILED LIBRARY ANALYSIS
1. Streamlit - Web Application Framework
Purpose: Provides the entire web application interface and user interaction layer.
Why Chosen: Enables rapid development of data applications without requiring frontend expertise. Offers built-in widgets, session state management, and responsive layouts. Key Functions: st.set_page_config(), st.markdown(), st.file_uploader(), st.session_state, st.tabs()
Alternative Rejected: Flask/Django (too complex for rapid prototyping), Gradio (limited customization)
2. Google Generative AI (Gemini) - AI Engine
Purpose: Core intelligence layer for text generation, Q&A;, summarization, and content creation.
Why Chosen: Free tier with generous limits, superior multilingual support (especially for Hinglish), context-aware responses up to 32K tokens, built-in safety filters, and no credit card required for API access.
Key Functions: genai.GenerativeModel(), genai.embed_content(), generate_content() Alternative Rejected: OpenAI GPT-4 (paid only, no free tier), Anthropic Claude (limited availability), Hugging Face (complex deployment)
3. ChromaDB - Vector Database
Purpose: Enables semantic search across documents using vector embeddings for intelligent retrieval.
Why Chosen: Embedded database requiring no separate server, persistent storage across sessions, fast similarity search using cosine distance, simple Python API, and handles thousands of documents efficiently.
Key Functions: PersistentClient(), get_or_create_collection(), add(), query()
Alternative Rejected: Pinecone (cloud-dependent, paid tiers), FAISS (complex setup, no persistence layer), Weaviate (resource-heavy)
4. Document Processing Suite
4.1 PyPDF2 - PDF Processing
Purpose: Extracts text content from PDF documents while preserving page structure. Why Chosen: Lightweight (no external dependencies), fast processing, handles encrypted PDFs, reliable for standard PDF formats.
Alternative Rejected: pdfplumber (slower processing), PyMuPDF (larger binary size)
 
4.2 python-docx - Word Document Processing
Purpose: Reads Microsoft Word .docx files and extracts text with structure.
Why Chosen: Official library for modern Word format, preserves paragraph structure, well-maintained and reliable.
Alternative Rejected: python-docx2txt (limited functionality, no structure preservation)
4.3 openpyxl - Excel Processing
Purpose: Processes Excel spreadsheets (.xlsx) including multiple sheets and formulas. Why Chosen: Handles modern Excel format, reads both formulas and computed values, supports multiple worksheets.
Alternative Rejected: pandas (overkill for simple extraction), xlrd (outdated, no .xlsx support)
4.4 python-pptx - PowerPoint Processing
Purpose: Extracts content from PowerPoint presentations (.pptx).
Why Chosen: Only reliable library for modern PowerPoint format, extracts text from shapes and slides.
Alternative Rejected: None available (monopoly library for .pptx format) 
