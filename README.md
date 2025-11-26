# ChatBot Sentiment Analyser

A full-stack intelligent chatbot application with real-time sentiment analysis, built using Flask, Google Generative AI (Gemini), and a custom two-tier sentiment analysis engine. The system provides message-level sentiment tracking, conversation-level insights, and comprehensive conversation history management.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/flask-2.0+-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

##  Features

- **Interactive Chatbot UI** - Clean, responsive interface for natural conversations
- **Dual-Tier Sentiment Analysis**
  - **Tier 1**: Real-time message-level sentiment scoring
  - **Tier 2**: AI-powered conversation-level insights and behavioral patterns
- **Conversation Management** - Store, view, analyze, and delete conversation histories
- **Google Gemini Integration** - Powered by advanced AI for intelligent responses
- **Persistent Storage** - SQLite database with SQLAlchemy ORM
- **Modular Architecture** - Clean separation of concerns for easy maintenance and extension

##  Technology Stack

### Backend
- **Python Flask** - Lightweight web framework
- **Google Generative AI (Gemini API)** - Advanced language model
- **SQLite** - Embedded database for conversation storage
- **SQLAlchemy ORM** - Database abstraction layer
- **python-dotenv** - Environment variable management

### Frontend
- **HTML5** - Semantic markup
- **CSS3** - Modern styling
- **Vanilla JavaScript** - No framework dependencies

### Analytics
- Custom sentiment analysis engine
- Conversation-level analytics processor
- Keyword-based polarity scoring with weighted lexicons

##  Getting Started

### Prerequisites

- Python 3.8 or higher
- Google Gemini API key ([Get one here](https://makersuite.google.com/app/apikey))
- Git

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Watcher141/ChatBot_Sentiment_Analyser.git
   cd ChatBot_Sentiment_Analyser
   ```

2. **Create a Virtual Environment**
   ```bash
   # macOS/Linux
   python -m venv venv
   source venv/bin/activate

   # Windows
   python -m venv venv
   venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables**
   
   Create a `.env` file in the root directory:
   ```env
   GOOGLE_API_KEY=your_gemini_api_key_here
   ```

5. **Run the Application**
   ```bash
   python app.py
   ```

6. **Access the Application**
   
   Open your browser and navigate to:
   ```
   http://localhost:5000
   ```

##  Sentiment Analysis Architecture

### Tier 1: Message-Level Sentiment

Every user message is analyzed in real-time using the `analyze_message(message)` function.

**Analysis Components:**
- Keyword-based polarity scoring
- Weighted positive/negative lexicon matching
- Semantic rule evaluation
- Optional LLM enhancement

**Output Format:**
```json
{
  "sentiment": "positive" | "neutral" | "negative",
  "score": -1.0 to 1.0
}
```

Each message's sentiment is stored in the database with its timestamp and context.

### Tier 2: Conversation-Level Analytics

Conversation insights are generated using `analyze_conversation_llm(history)`.

**Process:**
1. Retrieves full conversation history from database
2. Compiles message sentiments and contextual data
3. Sends aggregated data to Google Gemini
4. Generates comprehensive insights

**Insights Include:**
- Overall emotional trend and trajectory
- User mindset and behavioral patterns
- Conversation summary and key themes
- Potential user intent detection
- Recommendations for engagement

##  Project Structure

```
ChatBot_Sentiment_Analyser/
├── app.py                 # Main Flask application
├── database.py            # Database models and operations
├── sentiment.py           # Sentiment analysis logic
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables (create this)
├── static/
│   ├── css/              # Stylesheets
│   └── js/               # JavaScript files
├── templates/
│   └── index.html        # Main UI template
└── README.md
```

##  Testing

### Recommended Test Structure

**Unit Tests:**
- Message sentiment scoring accuracy
- Database CRUD operations
- Gemini API call mocking
- Sentiment score calculations

**Integration Tests:**
- Complete chat flow (user → bot → storage)
- Sentiment pipeline validation
- Conversation deletion functionality
- API endpoint responses

Run tests (if implemented):
```bash
pytest tests/
```

##  Implementation Status

| Feature | Status |
|---------|--------|
| Message-level sentiment | ✅ Completed |
| Conversation-level LLM analysis | ✅ Completed |
| Conversation storage & retrieval | ✅ Completed |
| "Analyze Conversation" UI button | ✅ Completed |
| Sentiment visualization | ✅ Completed |

##  Key Innovations

1. **Dual-Stage Sentiment Pipeline** - Combines rule-based and AI-powered analysis
2. **Modular Architecture** - Clean separation enables easy testing and extension
3. **Comprehensive Data Storage** - Every message includes:
   - Full text content
   - Sender identification
   - Sentiment score
   - Precise timestamp
4. **LLM-Powered Insights** - Deep conversation understanding beyond simple sentiment
5. **Extensible Design** - Ready for graphs, advanced ML models, and analytics dashboards


## Author

**Watcher141**
- GitHub: [@Watcher141](https://github.com/Watcher141)
