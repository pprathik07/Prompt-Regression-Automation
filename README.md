# 🧠 Prompt-Regression-Automation

A lightweight automation agent designed to test, validate, and audit outputs from LLMs (e.g., Gemini, GPT) for hallucinations, reasoning drift, and structural inconsistencies — then log and report issues via email in near real-time.

---

## ⚙️ What It Does

- Runs a batch of prompts through an LLM (currently Gemini)
- Compares token-level output against expected structure or logic
- Detects regressions in reasoning, tone, structure, or factual content
- Automatically sends email alerts for flagged outputs

---

## 🔁 Workflow

> Built using `n8n`, integrated with:
- **Gemini API** for prompt execution
- **Gmail** for auto-alerts
- **Telegram** for real-time notifications

graph TD;
    A[🕒 Schedule Trigger] --> B[📄 Get Rows from Google Sheet];
    B --> C[✏️ Edit Fields (Preprocessing)];
    C --> D[🤖 Gemini Chat Model API];
    D --> E[🧠 AI Agent: Internal Validation + Memory Tool];
    E --> F[✏️ Edit Fields (LLM Response Formatting)];
    F --> G[✏️ Edit Fields (Drift Detection Logic)];
    G --> H[✏️ Final Output Formatter];
    H --> I[📊 Update Google Sheet];
    I --> J{❓ If: Is Drift Detected?};
    J -- true --> K[🧮 Aggregate Alert Data];
    K --> L[📧 Send Alert Email];


🧪 Key Features
✅ Token-level comparison for logic or factual inconsistencies
📤 Auto-email alerts when drifts are detected
🔄 Extendable to support multiple LLM providers
📈 Tracks regression over time to improve prompt quality

🚀 Why This Matters
Manual testing of LLM responses is slow and error-prone. This agent:
Tested 10 prompts with 30+ points each in under 4 minutes
Reduced manual review time by 80%+
Supports iterative prompt refinement at scale

🛠️ Tech Stack
n8n
Gemini API (can be extended to OpenAI)
Gmail API
Telegram Bot API
