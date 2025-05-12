# agenteJean
🧠 AI Agent Automation Workflow (n8n Overview)

🎯 Purpose:

To automate Telegram voice/text messages, transcribe them (if voice), interpret them using AI (OpenAI Chat), and convert them into structured outputs like:
	•	Email messages (Gmail)
	•	Calendar appointments (Google Calendar)

⸻

🔄 General Flow:
	1.	📩 Telegram Trigger
	•	Listens for new messages (text or voice).
	2.	🧮 Code + Switch Node
	•	Determines message type: voice or text.

⸻

🎙 If Voice Message:
	3.	Get Voice File → Downloads voice from Telegram.
	4.	Speech to Text (OpenAI Whisper or similar) → Transcribes the audio.
	5.	Edit + Set Telegram → Prepares the transcribed message for processing.

⸻

📝 If Text Message:
	6.	Text is merged with transcribed voice (if applicable).
	7.	Final formatting via set_final.

⸻

🤖 AI Interpretation:
	8.	Custom AI Agent (“Dan Conversor de Leads”)
	•	Built with:
	•	OpenAI Chat Model
	•	Simple Memory
	•	Multiple Tools:
	•	Email Agent
	•	Calendar Agent
	•	Calculator
	•	SerpAPI
	•	Google Sheets Tool (for contact updates)

⸻

📧 Email Automation (Email Agent Workflow):
	•	Triggered internally.
	•	Uses OpenAI to understand intent.
	•	Sends, replies, or manages Gmail:
	•	Send Email
	•	Email Reply
	•	Label, Get, Delete, Create Draft
	•	Mark Unread
	•	Reads from Google Sheet (contact_tool)

⸻

📆 Calendar Automation (Calendar Agent Workflow):
	•	Triggered internally.
	•	Uses AI + Google Calendar tools to:
	•	Create or update events
	•	Create Google Meet
	•	Invite attendees
	•	Read/write from contact_tool sheet

⸻

📤 Output Based on Channel:
	•	Uses Switch to decide where to send output:
	•	Telegram response
	•	WhatsApp (optional)
	•	Webhook/API

⸻

🛠️ Tools Used:
	•	n8n
	•	Telegram Bot API
	•	OpenAI API (GPT & Whisper)
	•	Google Calendar API
	•	Gmail API
	•	Google Sheets
	•	Custom Code/JavaScript nodes
	•	Memory & Tools Agent 
