# 🤖 n8n Gmail → Sarcastic Spending Roast Bot

This project contains an automation workflow built with n8n that:

- Monitors your Gmail inbox for transaction alerts  
- Detects debit/spending messages  
- Uses an LLM (via Groq) to generate a brutally sarcastic reply  
- Sends the response to WhatsApp using Twilio  

---

## ⚙️ How It Works

1. **Gmail Trigger**
   - Polls your inbox every minute
   - Reads incoming email snippets  

2. **Filter (IF Node)**
   - Checks if the message contains `"debited"`  
   - Only continues if it's a spending alert  

3. **LLM Processing**
   - Uses Groq (LLaMA model)  
   - Generates a short, savage, sarcastic response  

4. **WhatsApp/SMS via Twilio**
   - Sends the generated message to your number  

---

## 🚀 Setup Instructions

### 1. Import Workflow into n8n
- Open n8n
- Click **Import**
- Upload the provided `.json` file  

---

### 2. Configure Credentials

You must reconnect the following inside n8n:

- Gmail OAuth2  
- Groq API  
- Twilio API  

> ⚠️ Credentials are not included in this repo for security reasons.

---

### 3. Update Phone Numbers

Inside the Twilio node:
- Replace:
  - `from` → your Twilio number  
  - `to` → your personal WhatsApp number  

---

### 4. Activate Workflow

- Click **Execute Workflow** (test)
- Then toggle **Active** to enable automation  

---

## ⚠️ Important Notes

- This workflow sends **harsh, sarcastic messages automatically**
- Make sure:
  - You are okay receiving such messages 😅  
  - It only triggers on relevant emails (bank alerts)

👉 Recommended improvements:
- Add sender filtering (bank emails only)
- Add spending threshold logic
- Add approval step before sending messages

---

## 🛠 Tech Stack

- n8n (workflow automation)  
- Groq (LLM inference)  
- Twilio (WhatsApp/SMS API)  

---

