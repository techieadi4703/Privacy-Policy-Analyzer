# 🔐 Privacy Policy Analyzer – Chrome Extension

> **AI-Powered Privacy Transparency.** Dissect complex legal jargon into clear, actionable insights using local LLMs.

The **Privacy Policy Analyzer** is a Chrome extension that uses AI to evaluate the privacy policies of websites. It provides structured insights into how websites collect, use, and share user data — helping users make informed decisions about their online privacy without sending their data to third-party AI clouds.

---

## ✨ Features

- **🔍 Auto-Extraction:** Automatically scrapes and evaluates the privacy policy text of any website.
- **⭐ Weighted Ratings:** Provides structured ratings (out of 5) for:
  - **Data Collection:** What is being tracked?
  - **Data Privacy:** How is it stored?
  - **Data Sharing:** Who else gets your info?
- **🌟 Visual Scorecard:** Real-time star rating visualization (including half-star support).
- **📊 Detailed Breakdown:** Results displayed in a clean, scannable tabular format.
- **🎛 Safety Controls:** Quick-action buttons to "Proceed to Website" or retreat to "Google Homepage."

---

## 🧱 Technology Stack

### Frontend

- **HTML5 / CSS3** – Clean, responsive Popup UI.
- **JavaScript** – DOM manipulation and Chrome Extension API integration.

### Backend

- **Python / Flask** – Lightweight API server.
- **Flask-CORS** – Secure cross-origin resource sharing.

### AI Engine (Local)

- **Ollama** – Local LLM runtime.
- **Llama 3** – Advanced language model for policy reasoning.

---

## ⚙️ System Requirements

- **Python:** 3.8+
- **Browser:** Google Chrome (or any Chromium-based browser)
- **Local AI:** [Ollama](https://ollama.com/) installed
- **Model:** Llama3 downloaded via Ollama

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone <https://github.com/shrujal24/Privacy-Policy-Analyzer>
cd privacy-policy-analyzer
```

### 2. Configure Local AI (Ollama)

You must have the Llama3 model running locally for the analysis to work.

```bash
# Verify Ollama is installed
ollama --version

# Pull the Llama3 model
ollama pull llama3

# Run the model
ollama run llama3
```

> **Note:** Keep Ollama running in the background while using the extension.

### 3. Set Up the Flask Backend

```bash
# Install dependencies
pip install flask flask-cors

# Start the server
python main.py
```

### 4. Load the Chrome Extension

1. Open Chrome and go to `chrome://extensions/`
2. Enable **Developer mode** (toggle in the top right)
3. Click **Load unpacked**
4. Select the folder containing your `manifest.json` file

---

## ▶️ Usage Instructions

1. Visit any website with a privacy policy.
2. Click the **Privacy Policy Analyzer** icon in your extension bar.
3. Click the **Analyze** button.
4. Review the Report:
   - Check the **Overall Star Rating**.
   - Read the **Detailed Breakdown** in the table.
   - Decide whether to stay or leave using the interactive buttons.

---

## 🧠 How It Works

1. **Extraction:** The extension identifies and pulls text content from the active tab.
2. **Transmission:** Content is sent to the local Flask backend.
3. **Inference:** The backend prompts the local Llama3 model to analyze the text.
4. **Structure:** The model returns a structured JSON evaluation.
5. **Visualization:** The extension parses the JSON and renders the UI/Star ratings.

---

## ⚠️ Known Issues & Limitations

- **Performance:** Analysis speed depends heavily on your local CPU/GPU hardware.
- **Length Limits:** Extremely long policies might be truncated based on the model's context window.
- **Browser Support:** Half-star CSS rendering may vary on older browser versions.
