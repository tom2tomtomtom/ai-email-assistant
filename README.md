# AI Email Assistant 🤖📧

An intelligent email aggregator that monitors multiple email accounts (Gmail, Yahoo, iCloud, Microsoft) and provides AI-powered summaries, natural language queries, and automated email composition.

## ✨ Features

### 🎯 Core Capabilities
- **Multi-Account Support**: Monitor Gmail, Yahoo, iCloud, and Microsoft accounts in one place
- **AI-Powered Analysis**: Automatic categorization and priority scoring of emails
- **Natural Language Queries**: Ask questions like "Show me urgent emails from this week"
- **Smart Email Composition**: AI helps write professional replies and new emails
- **Intelligent Summaries**: Daily briefings with AI insights about your email patterns

### 🤖 AI Features
- **Smart Categorization**: Automatically sorts emails into Work, Personal, Financial, etc.
- **Priority Detection**: AI analyzes content for urgency and importance
- **Context-Aware Replies**: Generates appropriate responses based on email content
- **Semantic Search**: Find emails by meaning, not just keywords
- **Pattern Recognition**: Identifies trends and important items across all accounts

## 🚀 Quick Start

### Prerequisites
```bash
python 3.8+
pip install -r requirements.txt
```

### Installation
1. Clone the repository:
```bash
git clone https://github.com/tom2tomtomtom/ai-email-assistant.git
cd ai-email-assistant
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the assistant:
```bash
python email_aggregator.py
```

This will create a sample `email_config.json` file for you to configure.

## 🔧 Configuration

### AI Provider Setup
Edit `email_config.json` to add your AI provider:

```json
{
  "ai": {
    "provider": "openai",  // Options: "openai", "anthropic", "google"
    "api_key": "your-api-key-here",
    "enable_semantic_search": true
  },
  "accounts": [...]
}
```

### Email Account Setup

#### Gmail
1. Enable Gmail API in Google Cloud Console
2. Create OAuth 2.0 credentials
3. Download as `gmail_credentials.json`

#### Yahoo Mail
1. Enable 2-factor authentication
2. Generate app-specific password
3. Use in configuration

#### iCloud Mail
1. Go to Apple ID settings
2. Generate app-specific password
3. Add to config

#### Microsoft/Outlook
1. Register app in Azure Portal
2. Get Client ID, Secret, and Tenant ID
3. Configure in settings

## 💻 Usage

### Interactive CLI Mode
```bash
python email_aggregator.py
```

Available commands:
- `fetch` - Get new emails from all accounts
- `query` - Ask questions about your emails
- `reply` - Compose a reply with AI assistance
- `compose` - Write a new email
- `send` - Send a draft email
- `summary` - Show email summary
- `help` - Show all commands

### Example Interactions

```bash
📧 > query show me urgent emails from this week

📧 > reply
[Select an email and provide instructions like "accept the meeting"]

📧 > compose
To: manager@company.com
What do you want to say? request Friday off for appointment
```

### Background Mode
```bash
python email_aggregator.py --daemon
```

Runs daily checks at configured time.

## 📊 Example Output

```
📧 AI Email Summary - 2025-07-30 09:00
============================================================

🔥 REQUIRES IMMEDIATE ATTENTION:
------------------------------
• From: client@important.com
  Subject: Contract Renewal - Response Needed
  AI Summary: Client requesting renewal decision by EOD.
  Category: Work/Professional
  Priority Score: 8.5

💡 AI INSIGHTS:
------------------------------
1. You have 3 urgent client requests needing responses today
2. Financial emails show 2 pending invoices totaling $5,420
3. Meeting conflicts detected for Thursday 2pm
```

## 🛡️ Security

- OAuth2 for Gmail and Microsoft
- App-specific passwords for Yahoo/iCloud
- Local SQLite database for metadata
- API keys should be stored in environment variables
- Email bodies processed locally, only summaries sent to AI

## 🤝 Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## 📄 License

MIT License - see LICENSE file for details

## 🙏 Acknowledgments

- Google Gmail API
- Microsoft Graph API
- OpenAI/Anthropic/Google AI
- Python email libraries

---

**Note**: This tool requires API keys for AI features. Free tiers are available for testing with Google's Gemini API.