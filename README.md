# ms-365-agents-demo

With the Microsoft 365 Agents SDK, you can create agents deployable to channels of your choice, such as Microsoft 365 Copilot, Microsoft Teams, Web & Custom Apps and more, with scaffolding to handle the required communication. Developers can use the AI Services of their choice, and make the agents they build available using the channel management capabilities of the SDK.

This repository demonstrates how to build Microsoft 365-aware intelligent agents using:

- **Python**
- **Microsoft 365 Agents SDK**
- **LangChain v1 (Multi-Agent Behavior)**
- **google_genai (Gemini LLM model)**

The project includes a simple multi-agent pattern with calendar and email-related capabilities, exposed through an application entrypoint and runnable via a local server.

---

## 📂 Repository Structure


```bash
ms-365-agents-demo/
│
├── src/
│   ├── agents_v1.py
│   ├── app.py
│   ├── main.py
│   └── start_server.py
│
├── requirements.txt
└── README.md
````


### File Purpose

| File | Purpose |
|------|---------|
| **agents_v1.py** | Contains the implementation of agent logic (Calendar + Email agent behavior using LangChain + Gemini). |
| **app.py** | Defines the primary application setup, wiring Microsoft 365 Agent SDK with LLM and routing. |
| **main.py** | Entry script used for initializing and invoking the agents interactively or programmatically. |
| **start_server.py** | Starts a runnable server instance for interacting with the agents locally. |

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/MusaddiqueHussainLabs/ms-365-agents-demo.git
cd ms-365-agents-demo
````

### 2️⃣ Create a Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate      # macOS / Linux
# or
.\.venv\Scripts\activate        # Windows
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔧 Configuration

Before running the application, ensure the following are configured:

| Requirement                   | Description                                                                       |
| ----------------------------- | --------------------------------------------------------------------------------- |
| **Microsoft 365 credentials** | For Calendar and Email access via Microsoft Graph (Client ID, Tenant ID, Secret). |
| **google_genai API key**      | Required to run Gemini model for LLM processing.                                  |

These values must be provided via environment variables before running the application.

---

## ▶️ Running the Application

There are two primary execution approaches:

### **Option 1 — Run as CLI Agent Test**

```bash
python src/main.py
```

### **Option 2 — Start Local Server**

```bash
python src/start_server.py
```

Once running, you may ask natural language questions such as:

```
"Schedule a meeting with the design team next Tuesday 25th Nov 2025, at 2pm for 1 hour,"
"and send them an email reminder design_team@org.com about reviewing the ppt presentation of Microsoft 365 agents sdk."
```

---

## 🧠 How It Works

* The **Gemini model** (via google_genai) interprets user intent.
* **LangChain v1** manages multi-agent routing and tool selection.
* The **Microsoft 365 Agent SDK** manages integration with Microsoft 365 services including:

  * Calendar
  * Email (Outlook)

Logic for both capabilities resides inside `agents_v1.py`.

---

## 📌 Notes

* This repository is intended as a **reference/demo** and not a final production solution.
* Your Microsoft Graph App must include permissions such as:

  * `Calendars.ReadWrite`
  * `Mail.ReadWrite`
  * `Mail.Send`

---

## 🤝 Contributions

Contributions are welcome.

If you'd like to improve or extend the example, please open an issue or submit a pull request.

---

## 📄 License

This project is licensed under the MIT License.

---

### ⭐ If you find this useful, please consider starring the repo!
