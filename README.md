# Generative AI Engineering & Production Cookbook 🚀

A comprehensive, production-oriented repository of Generative AI patterns, architectures, and practical implementations. This workspace serves as a reference hub for building scalable GenAI applications—ranging from simple LLM calls and conversational RAG pipelines to multi-agent swarms, cloud deployments (AWS Bedrock & SageMaker), fine-tuning, and enterprise database assistants.

---

## 📌 Repository Structure & Modules

The repository is organized into progressive modules from core fundamentals to production-grade systems:

### 1. Foundational LLMs & Inference
* **`1.1-openai/`**: OpenAI API integration, prompt templates, and basic LLM chain orchestration.
* **`1.2-ollama/`**: Running local LLMs privately (Llama 3, Mistral) with Ollama and LangChain.
* **`Codellam/`**: Local coding assistant using Meta's CodeLlama.
* **`9-Huggingfacewith Langchain/`**: Open-source models and inference pipelines via HuggingFace Hub and local pipelines.

### 2. Chatbots & User Interfaces
* **`2-OpenAI Chatbot/`**: Interactive chat interface powered by OpenAI models and Streamlit.
* **`3-Ollama Chatbot/`**: Privacy-first, offline-capable chatbot using local Ollama models with Streamlit.

### 3. Data Processing & Vector Search (RAG Pipeline)
* **`3.2-DataIngestion/`**: Ingestion pipelines for PDFs, text files, web pages, and research papers.
* **`3.3-Data Trnasformer/`**: Document chunking strategies (`RecursiveCharacterTextSplitter`, `CharacterTextSplitter`, `HTMLHeaderTextSplitter`, `RecursiveJsonSplitter`).
* **`4-Embeddings/`**: Embedding generation with OpenAI, HuggingFace, and Ollama.
* **`5-VectorStore/`**: Vector index storage, retrieval, and similarity search with FAISS and ChromaDB.

### 4. Production RAG (Retrieval-Augmented Generation)
* **`4-RAG Document Q&A/`**: End-to-end document question-answering with HuggingFace embeddings and vector retrieval.
* **`4.1-RAG Q&A Conversation/`**: Conversational RAG with conversation memory, chat history, and context-aware query rephrasing.
* **`Q&A Project/QARAGPDF/`**: Production Streamlit application for multi-PDF conversational question-answering.
* **`Q&A Project/RagDocumWithGroq/`**: Ultra-low-latency RAG system powered by Groq LPUs (`llama-3` / `mixtral`).
* **`Q&A Project/nvidia_LLm/`**: Enterprise RAG with NVIDIA NIM (NVIDIA Inference Microservices) and AI Foundation models.
* **`Q&A Project/Hybrid_search/`**: Dense + sparse hybrid search (BM25 + vector embeddings) for improved retrieval accuracy.
* **`Q&A Project/Knowledge_graph/`**: Graph-augmented generation (Graph RAG) and advanced prompt engineering strategies.

### 5. Autonomous Agents & Tool Use
* **`5-Search Engine/`**: Tool-calling agents equipped with DuckDuckGo, Arxiv, and Wikipedia search tools.
* **`6-Chat SQL/` & `Q&A Project/Chat_Sql/`**: Enterprise Text-to-SQL assistant querying relational databases (SQLite / MySQL) via natural language.
* **`8-MathsGPT/` & `Q&A Project/Math_solver/`**: Reasoning agents capable of solving mathematical problems with custom symbolic tools and calculators.
* **`Agentic-LanggraphCrash-course-main/` & `LANGGRAPHTOOLS/`**: Stateful multi-agent workflows using **LangGraph** (cycles, state graphs, human-in-the-loop, debugging, and multimodal reasoning).
* **`Q&A Project/MultiAgent/`**: Collaborative multi-agent teams using **CrewAI** (autonomous researcher and writer agents).

### 6. Cloud Deployment & Enterprise Architecture
* **`Q&A Project/Aws_project/`**: Enterprise AWS Bedrock integration with Anthropic Claude, Meta Llama 2, and Stable Diffusion.
* **`Q&A Project/Generative-AI-With-Cloud-main/`**: Cloud model deployment with AWS SageMaker (Falcon 40B) and serverless blog generation pipelines.

### 7. Fine-Tuning & Model Optimization
* **`2-finetuning/`**: Instruction fine-tuning workflows and custom dataset training.
* **`Q&A Project/fineTunning/`**: Parameter-Efficient Fine-Tuning (PEFT), LoRA/QLoRA on Gemma, and model quantization techniques.

### 8. Framework Guides & Deep Dives
* **`Intro_Langchain/` & `LANGCHAIN/`**: Modern LangChain LCEL (LangChain Expression Language), Structured Output (Pydantic), tool definitions, and middleware.
* **`langchain-crash-course/`**: Modular deep dive into Chat Models, Prompt Templates, Chains (sequential, parallel, branching), RAG, and ReAct Agents.

---

## ⚙️ Quick Start & Setup

### 1. Prerequisites
* Python 3.10 or 3.11 installed.
* [Ollama](https://ollama.com/) (optional, if you want to run models locally).

### 2. Create and Activate a Virtual Environment

```bash
# Windows (PowerShell)
python -m venv venv
.\venv\Scripts\Activate.ps1

# Linux / macOS
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

You can install the core dependencies using the requirement file in `Q&A Project/requirements.txt`:

```bash
pip install -r "Q&A Project/requirements.txt"
```

Or install common production packages directly:

```bash
pip install langchain langchain-community langchain-core langchain-text-splitters \
    langchain-openai langchain-groq langchain-huggingface \
    faiss-cpu chromadb sentence-transformers \
    streamlit python-dotenv pypdf duckduckgo-search sqlalchemy
```

### 4. Configure Environment Variables

Create a `.env` file in the root or in the respective project subfolder with your API keys:

```env
# Core LLM Providers
OPENAI_API_KEY=your_openai_api_key_here
GROQ_API_KEY=your_groq_api_key_here
ANTHROPIC_API_KEY=your_anthropic_api_key_here
NVIDIA_API_KEY=your_nvidia_api_key_here
HUGGINGFACEHUB_API_TOKEN=your_hf_token_here

# Search & Tools
TAVILY_API_KEY=your_tavily_key_here

# AWS (for Bedrock and SageMaker projects)
AWS_ACCESS_KEY_ID=your_aws_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_DEFAULT_REGION=us-east-1

# Optional: Tracing & Observability
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langsmith_api_key_here
LANGCHAIN_PROJECT=GenAI-Production
```

---

## 🏃 Running Applications

Most applications in this repository include a Streamlit web interface or interactive Jupyter notebooks.

### Run a Streamlit Application
Navigate to the directory of the app you want to run:

```bash
# Example 1: Run Conversational RAG with PDF
cd "4.1-RAG Q&A Conversation"
streamlit run app.py

# Example 2: Run Text-to-SQL Database Assistant
cd "../6-Chat SQL"
streamlit run app.py

# Example 3: Run Fast Groq RAG
cd "../Q&A Project/RagDocumWithGroq"
streamlit run app1.py
```

### Run Multi-Agent Workflows
For CrewAI or LangGraph workflows:

```bash
# Run CrewAI Agents
cd "Q&A Project/MultiAgent"
python crew.py
```

---

## 🛠️ Production Decision Cheat Sheet

| Use Case | Recommended Architecture | Files to Reference |
| :--- | :--- | :--- |
| **Document Search / Support Bot** | Conversational RAG with FAISS/Chroma & History Rephrasing | `4.1-RAG Q&A Conversation/app.py`, `Q&A Project/QARAGPDF/app.py` |
| **Low Latency & High Speed** | Groq LPU inference with Llama 3 / Mixtral | `Q&A Project/RagDocumWithGroq/app1.py` |
| **Enterprise Data Querying** | Natural Language Text-to-SQL with SQLDatabaseChain | `6-Chat SQL/app.py` |
| **Complex Multi-Step Tasks** | Stateful Multi-Agent graphs (LangGraph) or Swarms (CrewAI) | `Agentic-LanggraphCrash-course-main/`, `Q&A Project/MultiAgent/crew.py` |
| **Strict Data Privacy / Offline** | Local LLMs (Ollama) + Local Vector Store (Chroma) | `1.2-ollama/app.py`, `3-Ollama Chatbot/app.py` |
| **Domain Adaptation** | Parameter-Efficient Fine-Tuning (PEFT / LoRA / QLoRA) | `2-finetuning/finetune.py`, `Q&A Project/fineTunning/` |
| **Enterprise Cloud Infrastructure** | AWS Bedrock (Claude, Titan) & AWS SageMaker | `Q&A Project/Aws_project/app.py`, `Q&A Project/Generative-AI-With-Cloud-main/` |

---

## 🛡️ Production Best Practices Checklist

1. **Chunking Strategy**: Avoid arbitrary splitting. Tune chunk sizes (e.g., 500-1000 tokens) and overlap (10-20%) according to your embedding model's context window.
2. **Context-Aware Query Rewriting**: In conversational RAG, always pass user follow-ups through a prompt that condenses chat history and the latest query into a standalone question.
3. **Structured Outputs**: Use Pydantic or LangChain's `.with_structured_output()` when chaining LLM results into backend APIs or databases to avoid parsing failures.
4. **Observability**: Enable LangSmith (`LANGCHAIN_TRACING_V2=true`) to monitor latency, token usage, and identify bottlenecks in chains and agents.
5. **Guardrails & Fallbacks**: Provide fallback LLMs or degraded responses when primary API quotas or timeouts are reached.
