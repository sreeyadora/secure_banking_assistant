 HSBC Secure Banking Assistant

A modular, extensible conversational AI demo for banking workflows — featuring multi-turn context, fallback handling, and a Gradio-powered HSBC-branded web UI.  
Runs locally or in Google Colab (no ngrok required).

---

Setup

Colab / Jupyter:
1. Install dependencies:
   ```python
   !pip install gradio
   ```
2. Copy project files (`src/` folder and `app.py`, `requirements.txt`) to your environment.

Local:
1. Clone repo:
   ```bash
   git clone <your-repo-url>
   cd hsbc-banking-assistant
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run:
   ```bash
   python src/app.py
   ```
   Or (if using the Gradio CLI):
   ```bash
   gradio src/app.py
   ```

---

Supported Flows & Example Prompts

- Account Info  
  - "Show my balance"
  - "Show my mini statement"
- Block Card  
  - "Block my debit card 1111-2222-3333-4444"
- Apply for Loan  
  - "Apply for a loan for 25000 for education"
  - "Apply for a loan" (system will guide for missing info)
- Loan Status
  - "Show my loans"
- Fallback 
  - Unrecognized queries will trigger help/fallback

---

Project Structure

```
hsbc-banking-assistant/
├── src/
│   ├── app.py               # Main entrypoint, Gradio UI
│   ├── banking_api.py       # Business logic / API layer (in-memory DB, modular)
│   └── dialogue_manager.py  # Dialogue & state management, intent detection
├── requirements.txt
└── README.md
```

---

 Usage Guide

- Multi-turn flows: If you provide incomplete info (e.g. “apply for a loan”), the assistant will ask for missing details.
- Context switches: You can change topics mid-conversation; the agent will adapt.
- Extensibility: Add new flows or replace APIs by editing `dialogue_manager.py` and `banking_api.py`.
- Colab: After running, open the `gradio.live` link for the UI.
- Local: Access the assistant via `localhost:7860` (default Gradio port).

---

Dependencies

- gradio (tested >= 4.15)
- Python 3.8+

---

License & Attribution

Demo for hackathon purposes.  
HSBC branding for demonstration only.
