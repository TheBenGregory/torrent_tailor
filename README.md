# n8n Workflow: Torrent Tailor

[![n8n](https://img.shields.io/badge/n8n-workflow-blueviolet?style=flat&logo=n8n&logoColor=white)](https://n8n.io/) [![Telegram](https://img.shields.io/badge/Telegram-Bot-blue?style=flat&logo=telegram&logoColor=white)](https://telegram.org/) [![qBittorrent](https://img.shields.io/badge/qBittorrent-Download-orange?style=flat&logo=qBittorrent&logoColor=white)](https://www.qbittorrent.org/)

This n8n workflow acts as your personal torrent curator: Triggered by Telegram messages, it intelligently parses movie queries with ChatGPT, searches 1337x for matches (bypassing Cloudflare via FlareSolverr), extracts magnet links, and queues them in qBittorrent. Everything logs to Google Sheets for easy tracking—tailored downloads, no fuss.

![Workflow Overview](workflow-screenshot.png)  


## 🚀 Features
- **Telegram Integration**: Starts on bot commands (e.g., `/search Inception`).
- **AI-Powered Parsing**: GPT-4o-mini corrects spellings and formats titles with years (e.g., "inceptoin" → "Inception (2010)").
- **Smart Scraping**: Hits 1337x search, grabs details, and pulls top magnet links.
- **qBittorrent Queue**: Adds torrents with labels (e.g., "Movies") for organized downloads.
- **Fallbacks**: Saves "no results" to Sheets; handles multiple links per hit.

## 📋 Requirements
- **n8n**: Self-hosted v1.0+ (tested on 1.117.3).
- **Credentials**:
  - Telegram Bot Token (for trigger).
  - OpenAI API Key (for ChatGPT).
  - FlareSolverr (self-hosted for scraping).
  - qBittorrent WebUI creds (host/port/username/password).
  - Google Sheets API (for logging; optional).
- **Services**: FlareSolverr instance running, qBittorrent with WebUI enabled.

## 🔧 Setup
1. **Import Workflow**: In n8n, go to **Workflows** > **Import from File** > Upload `Torrent-Tailor-Sanitized.json`.
2. **Configure Credentials**: 
   - Telegram: Add bot token.
   - OpenAI: Add API key.
   - HTTP nodes: Set FlareSolverr/qBittorrent URLs (replace placeholders like `http://your-flaresolverr:port`).
3. **Customize Nodes**:
   - **"ChatGPT API"**: Tweak model/prompt as needed.
   - **"Save to Sheets"**: Update sheet ID/range.
4. **Activate**: Toggle **Active** on—test with `/search Ubuntu 24.x` in Telegram.

## 📱 Usage
- Message your bot: `/search [movie name]`.
- Bot searches magnet link
- Downloads queue in qBittorrent under
- Review logs in Sheets (timestamp, user, query, results).

## ⚠️ Notes
- **Sanitization**: Placeholders (e.g., `[REDACTED]`) are for demo—replace with your setup.
- **Legal**: Personal use only; respect site ToS and copyright laws.
- **Troubleshooting**: Scraping issues? Check FlareSolverr status. Errors in n8n **Executions**.

## 📄 License
MIT—fork and refine! Questions? [Open an issue](https://github.com/yourusername/torrent-tailor/issues).

---

*Built with ❤️ using n8n. Export date: October 28, 2025.*
