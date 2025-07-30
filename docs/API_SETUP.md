# API Setup Guide

## AI Provider Setup

### OpenAI (GPT-4)

1. **Create Account**
   - Visit [OpenAI Platform](https://platform.openai.com/)
   - Sign up or log in

2. **Generate API Key**
   - Go to [API Keys](https://platform.openai.com/api-keys)
   - Click "Create new secret key"
   - Name it (e.g., "Email Assistant")
   - Copy the key immediately (you won't see it again)

3. **Pricing**
   - GPT-4: ~$0.03 per 1K tokens
   - Typical email summary: ~500-1000 tokens
   - Monthly cost estimate: $5-20 for moderate use

### Anthropic (Claude)

1. **Create Account**
   - Visit [Anthropic Console](https://console.anthropic.com/)
   - Request access if needed

2. **Generate API Key**
   - Navigate to API Keys section
   - Create new key
   - Store securely

3. **Pricing**
   - Claude 3 Opus: ~$0.015 per 1K tokens
   - Often more detailed responses than GPT-4

### Google (Gemini)

1. **Create Project**
   - Visit [Google AI Studio](https://makersuite.google.com/)
   - Sign in with Google account

2. **Get API Key**
   - Click "Get API key"
   - Create new or use existing Google Cloud project
   - Copy API key

3. **Pricing**
   - Free tier: 60 queries per minute
   - Paid tier: $0.00025 per 1K characters
   - Best for testing and light usage

## Email Provider Setup

### Gmail API Setup

1. **Enable Gmail API**
   ```
   1. Go to Google Cloud Console
   2. Create new project or select existing
   3. Enable Gmail API
   4. Go to "Credentials"
   ```

2. **Create OAuth 2.0 Credentials**
   ```
   1. Click "Create Credentials" > "OAuth client ID"
   2. Configure consent screen:
      - User Type: External
      - App name: "AI Email Assistant"
      - Add your email to test users
   3. Create OAuth client:
      - Application type: Desktop app
      - Name: "Email Assistant Client"
   4. Download JSON file as gmail_credentials.json
   ```

3. **First Run Authorization**
   - On first run, browser will open
   - Log in and authorize the app
   - Token saved for future use

### Yahoo Mail Setup

1. **Enable 2-Factor Authentication**
   ```
   1. Go to Yahoo Account Security
   2. Enable "Two-step verification"
   3. Add phone number
   ```

2. **Generate App Password**
   ```
   1. In Security settings, find "Generate app password"
   2. Select "Other app"
   3. Name it "Email Assistant"
   4. Copy the 16-character password
   ```

### iCloud Mail Setup

1. **Enable 2-Factor Authentication**
   ```
   1. Go to appleid.apple.com
   2. Sign in > Security
   3. Enable Two-Factor Authentication
   ```

2. **Generate App-Specific Password**
   ```
   1. Under Security, click "Generate Password..."
   2. Label: "Email Assistant"
   3. Copy the password (xxxx-xxxx-xxxx-xxxx format)
   ```

### Microsoft/Outlook Setup

1. **Register Application**
   ```
   1. Go to Azure Portal
   2. Navigate to "App registrations"
   3. Click "New registration"
      - Name: "AI Email Assistant"
      - Supported account types: Personal Microsoft accounts
   4. Note the Application (client) ID
   ```

2. **Add Permissions**
   ```
   1. Go to "API permissions"
   2. Add permission > Microsoft Graph
   3. Delegated permissions:
      - Mail.Read
      - Mail.Send
   4. Grant admin consent
   ```

3. **Create Client Secret**
   ```
   1. Go to "Certificates & secrets"
   2. New client secret
   3. Description: "Email Assistant"
   4. Copy the Value (not the ID)
   ```

4. **Get Tenant ID**
   ```
   1. Go to "Overview"
   2. Copy Directory (tenant) ID
   ```

## Troubleshooting

### Common Gmail Issues

**"Access blocked" error**
- Ensure OAuth consent screen is configured
- Add your email to test users
- Try using a Google Workspace account

**Token refresh failed**
- Delete gmail_token.pickle
- Re-authenticate

### Common IMAP Issues

**"Authentication failed"**
- Verify app-specific password is correct
- Check 2FA is enabled
- Ensure IMAP is enabled in email settings

**Connection timeout**
- Check firewall settings
- Verify IMAP server addresses:
  - Yahoo: imap.mail.yahoo.com:993
  - iCloud: imap.mail.me.com:993

### AI Provider Issues

**Rate limits**
- Implement exponential backoff
- Use different API keys for different projects
- Consider caching responses

**Token limits**
- Truncate long email bodies
- Summarize in batches
- Use system prompts efficiently