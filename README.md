# Clinisight

An intelligent medical diagnosis assistant that combines symptom extraction, AI-powered diagnosis suggestions, and peer-reviewed research integration from PubMed to provide comprehensive medical insights.

## 🎯 Overview

Clinisight is a FastAPI-based application that leverages advanced NLP and the power of OpenAI's GPT-4 model to:
- Extract medical symptoms from patient descriptions
- Generate evidence-based diagnosis suggestions and treatment recommendations
- Fetch and summarize relevant peer-reviewed articles from PubMed
- Present comprehensive medical information in an accessible format

## ✨ Features

- **Symptom Extraction**: Intelligently identifies symptoms from natural language descriptions
- **AI-Powered Diagnosis**: Uses OpenAI GPT-4 to suggest possible diagnoses and treatments
- **PubMed Integration**: Automatically fetches relevant peer-reviewed medical research articles
- **Research Summarization**: Condenses complex medical abstracts into readable summaries
- **RESTful API**: Built with FastAPI for easy integration with frontend applications

## 🛠️ Tech Stack

- **Backend Framework**: FastAPI
- **Server**: Uvicorn
- **AI/NLP**: OpenAI GPT-4
- **Web Scraping**: BeautifulSoup4, lxml, requests
- **Environment Management**: python-dotenv
- **Python**: 3.13+

## 📋 Dependencies

- `openai` - OpenAI API client
- `fastapi` - Modern web framework
- `uvicorn` - ASGI server
- `beautifulsoup4` - HTML/XML parsing
- `lxml` - XML processing
- `requests` - HTTP client
- `python-dotenv` - Environment variable management

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Medical\ Diagnosis\ App
   ```

2. **Create a virtual environment** (optional but recommended)
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   ```

## 🏃 Running the Application

### Start the FastAPI Server
```bash
python3 app.py
```
The API will be available at `http://localhost:8080`

### API Documentation
Once the server is running, access:
- **Swagger UI**: `http://localhost:8080/docs`
- **ReDoc**: `http://localhost:8080/redoc`

## 📡 API Endpoints

### POST `/diagnosis`
Analyzes patient symptoms and returns diagnosis suggestions with relevant research.

**Request Body:**
```json
{
  "description": "I have a severe headache, fever, and feeling very tired"
}
```

**Response:**
```json
{
  "symptom": ["headache", "fever", "fatigue"],
  "diagnosis": "Based on your symptoms...",
  "pubmed_summary": "Summary of relevant research..."
}
```

## 📁 Project Structure

```
clinisight/
├── app.py                      # Main FastAPI application
├── main.py                     # Entry point
├── mcp_tool.py                 # MCP tool configuration
├── requirements.txt            # Project dependencies
├── pyproject.toml              # Project metadata
├── README.md                   # This file
└── functions/
    ├── symptom_extractor.py    # Symptom identification logic
    ├── diagnosis_symptoms.py    # OpenAI diagnosis generation
    ├── pubmed_articles.py       # PubMed API integration
    └── summerize_pubmed.py      # Medical text summarization
```

## 🔑 Key Components

### Symptom Extractor (`functions/symptom_extractor.py`)
Extracts relevant medical symptoms from patient descriptions using pattern matching.

### Diagnosis Generator (`functions/diagnosis_symptoms.py`)
Uses OpenAI GPT-4 to analyze symptoms and provide potential diagnoses with treatment suggestions.

### PubMed Integration (`functions/pubmed_articles.py`)
Fetches peer-reviewed articles from PubMed, including:
- Article titles and abstracts
- Author information
- Publication dates
- Direct links to full articles

### Text Summarizer (`functions/summerize_pubmed.py`)
Summarizes complex medical abstracts using GPT-4 for easier comprehension.

## ⚙️ Configuration

For MCP (Model Context Protocol) setup:
```bash
mcp install mcp_tool.py
uv run mcp dev mcp_tool.py
```

Reference: [PubMed NCBI](https://pubmed.ncbi.nlm.nih.gov/)

## ⚠️ Disclaimer

This application is designed as an informational tool and should not replace professional medical advice. Always consult with qualified healthcare professionals for diagnosis and treatment decisions.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.
