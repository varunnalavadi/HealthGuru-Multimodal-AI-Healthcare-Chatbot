# 🏥 HealthGuru – Multimodal AI Healthcare Chatbot

**HealthGuru** is a **multimodal AI chatbot** designed to provide accurate, contextual health assistance. It supports **text, voice, and image inputs**, leveraging a **multi-agent RAG framework** for reliable information retrieval and response generation.

---

## ✨ Key Features

* **💬 Multimodal Input:** Handles **text, voice, and medical image queries**.
* **🤖 Multi-Agent System:** Specialized agents refine queries, classify topics, retrieve data, and generate responses.
* **📚 Retrieval-Augmented Generation (RAG):** Reduces hallucinations by grounding responses in trusted medical data.
* **🔍 Semantic Search:** Uses a **vector database** to find the most relevant documents quickly.
* **🌐 Real-Time Information:** Fetches up-to-date content via web search fallback.

---

## 🏗️ System Architecture

1. **Input Processing:** Accepts text, voice, or images.
2. **Query Refinement:** Cleans and reformulates ambiguous queries.
3. **Classification:** Determines if the input is health-related.
4. **Information Retrieval:** Searches the **Pinecone vector database**; fallback via **Tavily API**.
5. **Response Generation:** Uses **Google Gemini 2.0 LLM** to generate coherent and contextually accurate responses.
6. **Output Delivery:** Returns results to the user via web interface.

```
User Input (Text/Voice/Image)
          ↓
Query Refinement Agent
          ↓
Query Categorization Agent
          ↓
Retrieval Agent → Pinecone DB
          ↓
Web Search Agent (Fallback)
          ↓
Generator Agent → LLM
          ↓
User Output
```

---

## 🛠️ Technology Stack

* **🐍 Python** – Backend and integration
* **🤖 Google Gemini 2.0** – Large Language Model for response generation
* **🧩 LangChain** – Multi-agent orchestration
* **📦 Pinecone** – Vector database for semantic search
* **🖼️ LLaMA-4 Scout** – Medical image analysis
* **🎤 Google Web Speech API** – Voice input
* **🌐 Tavily API** – Real-time web search

---

## ⚡ Installation

**Prerequisites:** Python 3.8+, pip, and internet connection for API access.

```bash
# Clone the repository
git clone https://github.com/yourusername/healthguru.git
cd healthguru

# Install dependencies
pip install -r requirements.txt
```

**Set up environment variables (.env):**

```env
GEMINI_API_KEY=your_gemini_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_ENVIRONMENT=your_pinecone_env
TAVILY_API_KEY=your_tavily_api_key
LLAMA_API_KEY=your_llama_api_key
PINECONE_INDEX_NAME=healthguru-index
```

**Initialize database:**

```bash
python scripts/setup_database.py --source-dir ./data/health_docs
```

**Run the chatbot:**

```bash
python app.py
```

Open in browser: `http://localhost:7860`

---

## 💡 Usage Examples

* **Text Query:**
  `User: "What are the symptoms of diabetes?"`
  `HealthGuru:` Returns a detailed, contextual response from trusted sources.

* **Voice Query:**
  Click microphone → Speak query → Transcribed & processed like text.

* **Image Input:**
  Upload prescription or medical images → LLaMA-4 Scout analyzes and provides relevant context.

---

## 🚀 Future Enhancements

* User personalization and health history tracking
* Latency optimization with caching
* Advanced reasoning using Chain-of-Thought agents
* Multilingual support with XLM-R/mBERT

---

## ⚠️ Disclaimer

* **Informational Only:** HealthGuru provides guidance; it is **not a substitute for professional medical advice**.
* **Emergency Situations:** Always contact emergency services in urgent cases.
* **Data Privacy:** Ensure compliance with local healthcare data regulations.

---

## 🙏 Acknowledgments

* Mayo Clinic, NIH, MedlinePlus, PubMed – for trusted medical data
* Google – Gemini AI models
* Pinecone – vector database services
* Open-source community – various libraries and tools
