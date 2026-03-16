# 🎬 MovieBot: AI-Powered Movie Trivia Chatbot

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                                                                            ║
║                    🎥 WELCOME TO MOVIEBOT 🎥                               ║
║                                                                            ║
║          Your AI-Powered Movie Trivia Expert & Chat Companion             ║
║                                                                            ║
║          🎬 Ask about films, directors, actors, and awards! 🎬            ║
║                                                                            ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

> *Built with LangChain, Ollama, and Gradio for an immersive movie experience*

A sophisticated Retrieval-Augmented Generation (RAG) chatbot that answers movie trivia questions using local AI models and document-based knowledge retrieval. Built with LangChain, Ollama, and Gradio for an interactive web interface.

## 🌟 Features

- **Intelligent Q&A**: Ask questions about movies, directors, actors, awards, and more
- **Local AI Models**: Uses Ollama for privacy-focused, offline AI processing
- **Document-Based Knowledge**: Retrieves answers from a curated movie trivia PDF
- **Conversational Memory**: Maintains chat history for context-aware responses
- **Web Interface**: Clean, user-friendly Gradio UI
- **Tracing Support**: Optional LangSmith integration for debugging and monitoring
- **Modular Architecture**: Easy to extend with new data sources or models

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- [Ollama](https://ollama.ai/) installed and running
- Required Ollama models: `mistral` (or your preferred model) and `granite-embedding:latest`

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Souchik/gen-ai-assessment.git
   cd gen-ai-assessment
   ```

2. **Set up virtual environment**:
   ```bash
   python -m venv .venv
   # On Windows:
   .venv\Scripts\activate
   # On macOS/Linux:
   source .venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Install Ollama models**:
   ```bash
   ollama pull mistral
   ollama pull granite-embedding:latest
   ```

5. **Configure environment** (optional):
   Create a `.env` file in the project root:
   ```env
   # LangSmith Tracing (optional)
   LANGSMITH_API_KEY=your_api_key_here
   LANGSMITH_PROJECT=movie-trivia
   LANGCHAIN_TRACING_V2=true

   # Custom PDF path (optional)
   PDF_PATH=./movies_trivia.pdf

   # LLM Model (optional, defaults to mistral)
   LLM_MODEL=mistral
   ```

### Running the Application

```bash
python movie_chatbot.py
```

The app will launch in your browser at `http://localhost:7860`.

## 📖 Usage

1. Open the web interface
2. Type your movie-related question (e.g., "Who directed Inception?")
3. Get AI-powered answers based on the trivia database
4. Continue the conversation with follow-up questions
5. Clear history anytime to start fresh

### Example Questions

- "What awards did The Shawshank Redemption win?"
- "Who played the Joker in The Dark Knight?"
- "Tell me about Christopher Nolan's filmography"
- "What is the highest-grossing film of all time?"

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   User Query    │───▶│   Gradio UI     │───▶│  LangChain RAG  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                                       │
┌─────────────────┐    ┌─────────────────┐             │
│  Movie Trivia   │───▶│   PDF Loader    │───▶│  Text Splitter  │
│     PDF         │    └─────────────────┘    └─────────────────┘
└─────────────────┘                                     │
┌─────────────────┐    ┌─────────────────┐             │
│   Ollama        │───▶│  Embeddings     │───▶│   Chroma DB     │
│ Embeddings      │    └─────────────────┘    └─────────────────┘
└─────────────────┘                                     │
┌─────────────────┐    ┌─────────────────┐             │
│   Ollama LLM    │───▶│   RetrievalQA   │◀────────────┘
│   (Mistral)     │    └─────────────────┘
└─────────────────┘
```

### Key Components

- **Document Loading**: PyPDFLoader processes the movie trivia PDF
- **Text Splitting**: CharacterTextSplitter creates manageable chunks
- **Embeddings**: Ollama's granite-embedding model vectorizes text
- **Vector Store**: ChromaDB stores and retrieves relevant documents
- **LLM**: Ollama's Mistral model generates responses
- **Prompt Engineering**: Custom prompts ensure accurate, context-based answers
- **Chat History**: In-memory session management for conversational flow

## ⚙️ Configuration

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `PDF_PATH` | Path to movie trivia PDF | `./movies_trivia.pdf` |
| `LLM_MODEL` | Ollama model name | `mistral` |
| `LANGSMITH_API_KEY` | LangSmith API key | None |
| `LANGSMITH_PROJECT` | LangSmith project name | None |
| `LANGCHAIN_TRACING_V2` | Enable tracing | `true` if API key set |

### Customizing the Knowledge Base

1. Replace `movies_trivia.pdf` with your own movie data
2. Adjust text splitting parameters in `load_and_split_pdf()`
3. Modify the prompt template in `build_prompt()`
4. Change embedding or LLM models via environment variables

## 📋 Requirements

- Python 3.8+
- Ollama with compatible models
- Dependencies listed in `requirements.txt`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [LangChain](https://langchain.com/) for the RAG framework
- [Ollama](https://ollama.ai/) for local AI model hosting
- [Gradio](https://gradio.app/) for the web interface
- [ChromaDB](https://www.trychroma.com/) for vector storage

## 📞 Support

If you encounter issues or have questions:

1. Check the [Issues](https://github.com/Souchik/gen-ai-assessment/issues) page
2. Ensure Ollama is running and models are installed
3. Verify your Python environment and dependencies

---

*Built with ❤️ for movie enthusiasts and AI developers*</content>
<parameter name="filePath">d:\gen-ai assessment\README.md