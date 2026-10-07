# 🤖 LLM Prompt Library with LangChain + Groq

A reusable **LLM Prompt Library** built with **Python, LangChain, and Groq** for common Data Analyst and Business Intelligence tasks.

The project demonstrates how to create versioned prompts, connect them to Groq-hosted LLMs through LangChain, automatically select an available model, parse structured outputs, and save reusable prompt configurations and results.

---

## 🚀 Project Overview

This project contains four reusable LLM prompt modules:

1. **Sentiment Classifier**
2. **Insight Summarizer**
3. **SQL Explainer**
4. **Churn Retention Advisor**

Each prompt has a defined version, output type, system instruction, and human input template.

The application dynamically retrieves the available Groq models and attempts to use preferred models first, with automatic fallback to other compatible models.

---

## ✨ Key Features

- 🔑 Secure API-key input using `GROQ_API_KEY`
- 🤖 Groq LLM integration
- 🔗 LangChain prompt pipelines
- 🧩 Reusable prompt library
- 📌 Versioned prompts
- 🔄 Automatic model fallback
- 📊 Sentiment analysis
- 💡 Business insight summarization
- 🗃️ SQL query explanation
- 📉 Customer churn retention recommendations
- 📝 JSON and text output parsing
- 💾 Automatic saving of prompt configurations and results

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| LangChain | Prompt and LLM orchestration |
| Groq | LLM inference |
| Requests | Groq API model discovery |
| JSON | Prompt and result storage |
| Google Colab | Development environment |

---

## 📁 Project Structure

```text
llm-prompt-library/
│
├── llm_prompt_library_with_langchain.py
├── README.md
├── requirements.txt
├── LICENSE

```

---

## 🧠 Prompt Modules

### 1. Sentiment Classifier

Classifies customer feedback into:

- Positive
- Negative
- Neutral

It also returns:

- Confidence score
- Short reasoning

Example:

```text
Input:
The delivery was two days late and the packaging was damaged.

Output:
{
  "sentiment": "negative",
  "confidence": 0.98,
  "reason": "Late delivery and damaged packaging indicate poor service."
}
```

---

### 2. Insight Summarizer

Converts analytical findings into business-friendly insights.

The output follows:

```text
Finding
Impact
Recommendation
```

Example input:

```text
58% of 50,000 customers are in the At Risk RFM group;
Random Forest reached 91.6% accuracy and 93% precision for churn.
```

---

### 3. SQL Explainer

Explains SQL queries in simple English for non-technical business users.

Example:

```sql
SELECT category,
       SUM(price * quantity) AS revenue
FROM products
GROUP BY category
ORDER BY revenue DESC
LIMIT 5;
```

The LLM explains what the query returns and why the result is useful for business decision-making.

---

### 4. Churn Retention Advisor

Uses churn-analysis results to generate practical customer-retention actions.

Example input:

```text
At Risk group = 58% (29,094 customers);
class-balanced Logistic Regression churn recall = 73.8%.
```

The model generates three concise retention recommendations tied to the provided metrics.

---

## 🔄 How the Pipeline Works

```text
User Input
    ↓
Prompt Library
    ↓
LangChain ChatPromptTemplate
    ↓
Groq LLM
    ↓
Output Parser
    ↓
Structured / Text Result
    ↓
results.json
```

---

## 🤖 Model Selection

The application first retrieves the currently available models from Groq.

Preferred models are checked first.

If a preferred model is unavailable, the application automatically tries another compatible model.

This makes the application more resilient to model availability changes.

---

## 🔐 API Key Setup

### Option 1 — Environment Variable

Windows PowerShell:

```powershell
$env:GROQ_API_KEY="your_api_key_here"
```

Linux/macOS:

```bash
export GROQ_API_KEY="your_api_key_here"
```

### Option 2 — Google Colab

Add `GROQ_API_KEY` to Colab Secrets.

### Option 3 — Hidden Prompt

If no environment variable or Colab Secret is available, the program securely requests the API key through a hidden input prompt.

**Never commit your API key to GitHub.**

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/llm-prompt-library.git
```

Move into the project:

```bash
cd llm-prompt-library
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Project

```bash
python llm_prompt_library_with_langchain.py
```

The program will:

1. Load the Groq API key.
2. Retrieve available Groq models.
3. Select a compatible model.
4. Build LangChain prompt chains.
5. Run all four demonstration prompts.
6. Parse the outputs.
7. Save the prompt library and results.

---

## 📂 Generated Files

### `prompt_library.json`

Contains the reusable prompt definitions, including:

- Prompt name
- Version
- Output type
- System prompt
- Human prompt template

### `results.json`

Stores:

- Input
- Model used
- Generated output

---

## 📊 Example Results

The demonstration includes:

| Module | Purpose |
|---|---|
| Sentiment Classifier | Customer feedback classification |
| Insight Summarizer | Business insight generation |
| SQL Explainer | SQL-to-business explanation |
| Churn Retention Advisor | Customer retention recommendations |

---

## 💼 Business Use Cases

This project can be adapted for:

- Customer feedback analysis
- E-commerce analytics
- Customer churn analysis
- SQL assistance
- Business intelligence
- Data analyst workflows
- Customer retention
- Automated reporting
- LLM-powered analytics applications

---

## 🎯 Skills Demonstrated

This project demonstrates practical knowledge of:

- Python
- LangChain
- LLM integration
- Groq API
- Prompt engineering
- Structured output parsing
- JSON handling
- API integration
- Error handling
- Model fallback strategies
- Business analytics
- SQL explanation
- Customer churn analysis

---

## 🔮 Future Improvements

Possible extensions:

- Add a Streamlit user interface
- Add more analytical prompts
- Add prompt evaluation metrics
- Add prompt version tracking
- Add database storage
- Add batch processing for CSV files
- Add RAG capabilities
- Add LangSmith tracing
- Add automated prompt testing
- Add authentication and multi-user support

---

## 👨‍💻 Author

**Amit Shahare**

MCA | Data Analyst | Business Analyst | AI/ML Enthusiast

Skills:

`Python` `SQL` `Power BI` `Pandas` `LangChain` `LLMs` `Groq` `Data Analytics`

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.
