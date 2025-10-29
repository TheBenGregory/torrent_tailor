n8n Workflow: Torrent Tailor
  
This n8n workflow acts as your personal torrent curator: Triggered by Telegram messages, it intelligently parses movie queries with ChatGPT, searches 1337x for matches (bypassing Cloudflare via FlareSolverr), extracts magnet links, and queues them in qBittorrent. Everything logs to Google Sheets for easy tracking—tailored downloads, no fuss.
Failed to load imageView link
(Add your screenshot here for visual appeal—e.g., a diagram of the node flow from Telegram to qBittorrent.)
🚀 Features

Telegram Integration: Starts on bot commands (e.g., /search Inception).
AI-Powered Parsing: GPT-4o-mini corrects spellings and formats titles with years (e.g., "inceptoin" → "Inception (2010)").
Smart Scraping: Hits 1337x search, grabs details, and pulls top magnet links.
qBittorrent Queue: Adds torrents with labels (e.g., "Movies") for organized downloads.
Fallbacks: Saves "no results" to Sheets; handles multiple links per hit.

📋 Requirements

n8n: Self-hosted v1.0+ (tested on 1.117.3).
Credentials:

Telegram Bot Token (for trigger).
OpenAI API Key (for ChatGPT).
FlareSolverr (self-hosted for scraping).
qBittorrent WebUI creds (host/port/username/password).
Google Sheets API (for logging; optional).


Services: FlareSolverr instance running, qBittorrent with WebUI enabled.

🔧 Setup

Import Workflow: In n8n, go to Workflows > Import from File > Upload Torrent-Tailor-Sanitized.json.
Configure Credentials:

Telegram: Add bot token.
OpenAI: Add API key.
HTTP nodes: Set FlareSolverr/qBittorrent URLs (replace placeholders like http://your-flaresolverr:8191).


Customize Nodes:

"ChatGPT API": Tweak model/prompt as needed.
"Save to Sheets": Update sheet ID/range.


Activate: Toggle Active on—test with /search The Dark Knight in Telegram.

📱 Usage

Message your bot: /search [movie name].
Bot responds with top 3 torrents + magnets (or "No results").
Downloads queue in qBittorrent under "Movies".
Review logs in Sheets (timestamp, user, query, results).

⚠️ Notes

Sanitization: Placeholders (e.g., [REDACTED]) are for demo—replace with your setup.
Legal: Personal use only; respect site ToS and copyright laws.
Troubleshooting: Scraping issues? Check FlareSolverr status. Errors in n8n Executions.

📄 License
MIT—fork and refine! Questions? Open an issue.

Built with ❤️ using n8n. Export date: October 28, 2025.
Troubleshooting: Scraping issues? Check FlareSolverr status. Errors in n8n Executions.

License: MIT—fork and refine! Questions? Open an issue.

Built with ❤️ using n8n. Export date: October 28, 2025.
