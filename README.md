# Event-Driven Agentic Document Workflows

A sophisticated AI-powered system that automates the process of filling out job application forms using resume data, with interactive voice feedback capabilities.

> **Note**: This project is based on the [Event-Driven Agentic Document Workflows course](https://learn.deeplearning.ai/courses/event-driven-agentic-document-workflows) from DeepLearning.AI, taught by Laurie Voss (VP of Developer Relations at LlamaIndex).

## 🎯 Project Overview

This project demonstrates advanced document workflow automation using LlamaIndex's event-driven architecture. It processes resumes and job application forms, automatically extracting relevant information and filling out forms with human-in-the-loop feedback - including voice input capabilities.

## 🏗️ Architecture

The system is built around a **RAG (Retrieval-Augmented Generation) Workflow** that follows an event-driven pattern:

- **Document Ingestion**: Parses resumes and application forms using LlamaParse
- **Vector Indexing**: Creates searchable embeddings using OpenAI's embedding models
- **Intelligent Querying**: Generates context-aware responses for form fields
- **Human Feedback Loop**: Integrates human validation with voice transcription
- **Iterative Refinement**: Continuously improves responses based on feedback

## 🚀 Key Features

- **Automated Form Filling**: Extracts relevant information from resumes to populate job application forms
- **Voice Feedback Integration**: Uses OpenAI Whisper for speech-to-text transcription
- **Interactive Workflow Visualization**: Generates HTML visualizations of workflow paths
- **Persistent Storage**: Maintains document indexes and vector stores for efficient retrieval
- **Asynchronous Processing**: Built with async/await patterns for scalable performance

## 📁 Project Structure

```
├── L6.ipynb                 # Main workflow implementation notebook
├── helper.py                # Utility functions for API keys and file operations
├── requirements.txt         # Python dependencies
├── workflows/              # Generated workflow visualizations
├── storage/                # Persistent storage for indexes and vector stores
│   ├── default__vector_store.json
│   ├── docstore.json
│   ├── graph_store.json
│   └── index_store.json
└── data/                   # Sample documents for testing
    ├── fake_resume.pdf
    └── fake_application_form.pdf
```

## 🛠️ Technology Stack

- **LlamaIndex Core**: Document processing and workflow orchestration
- **OpenAI GPT-4o-mini**: Large language model for intelligent responses
- **OpenAI Whisper**: Speech-to-text transcription
- **OpenAI Embeddings**: Vector embeddings for semantic search
- **LlamaParse**: Advanced document parsing with structured output
- **Gradio**: Web interface for voice input and transcription
- **Python Async**: Asynchronous programming for workflow management

## 🔧 Setup & Installation

### Prerequisites

- Python 3.9.6+
- OpenAI API key
- LlamaCloud API key

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd event-driven-agentic-document-workflows
```

2. Create and activate a virtual environment:
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

3. Install dependencies (make sure your virtual environment is activated):
```bash
# Verify virtual environment is active (you should see (venv) in your terminal prompt)
pip install -r requirements.txt
```

4. Set up environment variables:
```bash
# Create .env file in the project directory
OPENAI_API_KEY=your_openai_api_key_here
LLAMA_CLOUD_API_KEY=your_llama_cloud_api_key_here
```

## 🎮 Usage

### Running the Workflow

#### Option 1: Launch Jupyter Notebook (Recommended)

1. **Activate your virtual environment**:
   ```bash
   source venv/bin/activate  # On Linux/macOS
   # or
   venv\Scripts\activate     # On Windows
   ```

2. **Start Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

3. **Access Jupyter in your browser**:
   - The terminal will display a URL like: `http://localhost:8888/?token=abc123...`
   - Copy and paste this URL into your web browser
   - Navigate to `L6.ipynb` in the Jupyter file browser

4. **Execute Cells Sequentially**: Follow the notebook step-by-step to:
   - Set up the workflow
   - Process resume and application form
   - Generate workflow visualization
   - Test voice feedback capabilities

5. **Voice Input**: Use the Gradio interface to provide voice feedback during the workflow execution

#### Option 2: Direct Notebook Launch

```bash
# Activate virtual environment
source venv/bin/activate

# Launch specific notebook directly
jupyter notebook L6.ipynb
```

#### Option 3: Jupyter Lab (Alternative Interface)

```bash
# Install JupyterLab if you prefer it
pip install jupyterlab

# Launch JupyterLab
jupyter lab
```

### Workflow Steps

1. **Setup**: Initialize LLM and create vector index from resume
2. **Form Parsing**: Extract form fields using LlamaParse
3. **Question Generation**: Create queries for each form field
4. **RAG Querying**: Retrieve relevant information from resume
5. **Form Filling**: Combine responses into structured form data
6. **Human Feedback**: Collect voice/text feedback for validation
7. **Iterative Refinement**: Improve responses based on feedback

## 🔍 Workflow Visualization

The system automatically generates HTML visualizations of workflow paths, showing:
- Event flow between steps
- Decision points and feedback loops
- Complete workflow execution paths

Visualizations are saved in the `workflows/` directory.

## 📊 Sample Data

The project includes sample documents for testing:
- `fake_resume.pdf`: Sample resume for processing
- `fake_application_form.pdf`: Sample job application form

## 🔐 Configuration

The system supports multiple configuration approaches:
- **Environment Variables**: For API keys and service endpoints
- **File-based Discovery**: Automatic configuration loading
- **Runtime Overrides**: Dynamic configuration during execution

## 🚨 Important Notes

- **Cell Execution**: Run notebook cells sequentially to avoid conflicts
- **Voice Recording**: Ensure microphone permissions are granted for voice feedback
- **API Limits**: Be mindful of OpenAI API usage and rate limits
- **Storage Persistence**: Document indexes are automatically persisted for reuse

## 🔧 Troubleshooting

### Common Jupyter Issues

1. **Jupyter not found**: Ensure you're in the virtual environment and have installed requirements
   ```bash
   source venv/bin/activate
   pip install -r requirements.txt
   ```

2. **Port already in use**: Jupyter will automatically find the next available port
   - Check the terminal output for the actual URL being used
   - Or specify a custom port: `jupyter notebook --port=8889`

3. **Kernel not starting**: 
   - Restart the kernel: Kernel → Restart
   - Check if all dependencies are installed: `pip list | grep jupyter`

4. **Display not working**: Ensure you're using the correct kernel
   - Go to Kernel → Change Kernel
   - Select the kernel that matches your virtual environment

### Environment Variable Issues

- **API keys not found**: Ensure your `.env` file is in the project directory (not parent directory)
- **Connection errors**: The system now uses default LlamaCloud endpoints automatically

## 🔄 Extending the Workflow

The modular architecture makes it easy to extend:

- **New Event Types**: Add custom events for additional workflow steps
- **Additional Steps**: Implement new processing steps with the `@step` decorator
- **Custom Parsers**: Integrate different document parsing strategies
- **Alternative LLMs**: Swap out OpenAI models for other providers

## 📚 Resources

This project is based on the [Event-Driven Agentic Document Workflows course](https://learn.deeplearning.ai/courses/event-driven-agentic-document-workflows) from DeepLearning.AI, taught by Laurie Voss (VP of Developer Relations at LlamaIndex).

### Additional Resources
- [LlamaIndex Agentic Document Workflows](https://www.llamaindex.ai/blog/introducing-agentic-document-workflows)
- [Example Implementations](https://github.com/run-llama/llamacloud-demo/tree/main/examples/document_workflows)
- [LlamaIndex Documentation](https://docs.llamaindex.ai/)
- [OpenAI API Documentation](https://platform.openai.com/docs)

## 🤝 Contributing

This project demonstrates advanced workflow automation patterns. Feel free to:
- Experiment with different document types
- Add new workflow steps
- Implement alternative feedback mechanisms
- Optimize performance and scalability

## 📄 License

This project is for educational and demonstration purposes. Please ensure compliance with the licenses of all included dependencies and APIs.

---

**Built with ❤️ using LlamaIndex and OpenAI technologies**
