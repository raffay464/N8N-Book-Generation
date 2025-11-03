# 📚 n8n Book Generation Workflow

An **AI-powered automation system built with n8n** that dynamically generates entire books from structured data using **OpenAI GPT models**.  
The workflow automates everything from input parsing and validation to AI content generation, Supabase storage, and file compilation — all inside n8n.  
*(Gmail delivery integration planned.)*

---

## 🚀 Overview

This workflow demonstrates how to orchestrate a **complete AI content pipeline** within **n8n** using function nodes, conditional logic, and API integrations.

### 🔄 Main Workflow Steps

1. **Trigger:**  
   Starts automatically using the **Schedule Trigger** node.

2. **Data Fetching:**  
   Downloads input files (Excel/JSON) via an **HTTP Request** node.

3. **Data Extraction:**  
   Parses the input using **Extract from File** to get book titles, notes, or metadata.

4. **Validation:**  
   Uses **IF** logic to ensure the book title and notes are present before generation.

5. **OpenAI Integration:**  
   - Generates **chapter outlines** using the **OpenAI GPT node**.  
   - Generates **chapter content** for each outline.  

6. **Data Structuring:**  
   Multiple **Code (Function)** nodes format and validate chapters, ensuring clean JSON structures for storage.

7. **Supabase Integration:**  
   - Book and chapter data are created/updated via **HTTP Request** nodes to a **Supabase** backend.  
   - REST API keys and bearer tokens manage secure communication.

8. **Compilation:**  
   All chapters are merged into a single formatted book file (text-based).

9. **Output (Planned):**  
   - Converts the compiled book into a `.txt` or `.pdf` binary file.  
   - Sends the generated book via **Gmail node** (to be configured).

---

## 🧩 Key Nodes Used

| Node Type | Purpose |
|------------|----------|
| **Schedule Trigger** | Starts the automation on a timed interval |
| **HTTP Request** | Fetches source files and interacts with Supabase REST API |
| **Extract from File** | Extracts content from Excel or JSON |
| **IF** | Validates that required fields are not empty |
| **Code (Function)** | Formats and structures JSON data |
| **OpenAI GPT Node** | Generates book outlines and chapter content |
| **Supabase API** | Stores and updates book data |
| **Gmail (Planned)** | Sends the final generated book via email |

---

## 🧠 Example Use Case

This workflow can be adapted for:
- Dynamic content or report generation
- Knowledge base creation
- Automated document writing
- AI-assisted publishing systems

It demonstrates how **AI + automation** can replace manual content workflows using only **n8n** — no custom backend needed.

---

## ⚙️ Setup Instructions

1. **Install n8n:**  
   ```bash
   npm install n8n -g
   n8n start


2. Import Workflow:
Open the n8n editor at http://localhost:5678
Click Import → Upload the file N8N Book generation.json

3.Configure Credentials:
Add OpenAI API key under Credentials → OpenAI API
Add Supabase API key and endpoint URL under HTTP Request Credentials
(Optional) Add Gmail OAuth2 credentials if you plan to enable the email delivery node.

4.Run the Workflow:
Click Execute Workflow or enable the Schedule Trigger for automation.



## 📦 Tech Stack
n8n :
  Workflow automation platform
OpenAI API :
  GPT-based content generation
Supabase :
  Backend database and API
  JavaScript (for logic and custom Function nodes)
  Gmail API (planned integration)


## 📧 Future Improvements
 1-Complete Gmail node configuration for automatic book delivery
 2-Add PDF export option
 3-Include progress notifications via Telegram or Slack
 4-Extend workflow for multi-book batch generation  
