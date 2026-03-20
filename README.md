# 🚀 n8n Slack Newsletter Automation

This project is an end-to-end automation workflow built using **n8n** that allows users to trigger newsletter delivery directly from Slack.

When a user mentions the bot in Slack with a keyword, the workflow:

1. Fetches latest newsletter articles from an RSS feed  
2. Aggregates all articles into a single digest  
3. Sends a formatted digest email via Gmail  
4. Posts a confirmation message back to Slack  

---

## 🎯 Workflow Architecture


Slack Trigger (App Mention)
↓
IF Node (Keyword Filter)
↓
RSS Read Node (Fetch Newsletter)
↓
Aggregate Node (Merge Articles)
↓
Set Node (Format Digest)
↓
Gmail Node (Send Digest Email)
↓
Slack Node (Send Confirmation Message)


---

## ⚙️ Features

✅ Trigger automation from Slack  
✅ Fetch latest newsletter articles automatically  
✅ Send **Single Digest Email** instead of multiple emails  
✅ Keyword-based execution control  
✅ Slack confirmation notification  
✅ Prevents bot self-trigger loops  
✅ Production webhook automation  

---

## 🧠 How It Works

### Step 1 — Slack Trigger

Workflow starts only when the bot is mentioned:


@n8n-newsletter-bot newsletter


---

### Step 2 — IF Node Filter

Workflow runs only when message contains keyword:


newsletter


---

### Step 3 — RSS Feed Fetch

RSS Read node pulls latest articles from configured newsletter feed.

Example:


https://feeds.feedburner.com/TechCrunch/


---

### Step 4 — Aggregate Articles

Aggregate node collects all RSS items into a single data array.

---

### Step 5 — Format Digest (Set Node)

Articles are formatted into a clean digest list:


• Article Title
Article Link


---

### Step 6 — Send Gmail Digest

Gmail node sends **one email containing all newsletter articles.**

Important setting:


Execute Once = TRUE


---

### Step 7 — Slack Confirmation

After email is sent, workflow posts confirmation message in Slack channel:


Newsletter digest email sent successfully ✅


---

## 🔑 Required Integrations

- Slack App (Bot Token + Event Subscriptions)
- Gmail OAuth Credentials
- Public n8n URL (Production Webhook)

---

## 🧪 Testing vs Production

| Mode | Trigger URL | Behaviour |
|------|------------|-----------|
| Manual Test | Test Webhook | Runs only when “Listen” is active |
| Active Workflow | Production Webhook | Runs automatically |

---

## 🚀 Future Improvements

- AI summarization of newsletter articles  
- HTML formatted email template  
- Store newsletter logs in Google Sheets / Notion  
- Daily scheduled automation  
- Multi-channel Slack notifications  
- Error handling + retry logic  

---

## 👨‍💻 Built With

- n8n Workflow Automation  
- Slack Events API  
- Gmail Integration  
- RSS Feed Processing  

---

## 📌 Author

Built as a practical automation learning project using n8n.
