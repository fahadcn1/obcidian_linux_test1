---
title: "fb_manager — Facebook Comment Moderator"
created: 2026-09-07
updated: 2026-09-07
tags: [project/fb_manager, python, automation, facebook, playwright, llm, sentiment-analysis, status/active]
source_path: "/media/yin/my_personal/fb_manager"
status: active
---

# fb_manager — Facebook Comment Moderator

Personal-profile Facebook comment moderator. Opens Chrome with the real user profile, loads a Facebook post, extracts comments, scores negativity with an LLM (or keyword fallback), hides negative comments, and optionally replies automatically.

> ⚠️ **Risk**: Violates Meta's Terms of Service. May trigger security checks or account restrictions. Always start in `DRY_RUN=true` mode.

---

## Quick Facts

| Field | Value |
| :--- | :--- |
| **Source path** | `/media/yin/my_personal/fb_manager` |
| **Language** | Python 3 |
| **Browser** | Chrome via Playwright (persistent profile) |
| **AI providers** | OpenAI, Kimi/Moonshot, DeepSeek, Anthropic, Google Gemini, OpenAI-compatible |
| **Status** | #status/active |

---

## Files

| File | Purpose |
| :--- | :--- |
| `main.py` | Pipeline runner: history, browser, post processing, persistence |
| `facebook.py` | `FacebookModerator` class — Chrome/Playwright automation |
| `sentiment.py` | LLM + keyword sentiment analysis |
| `config.py` | `.env` loader and validator |
| `setup.py` | Interactive `.env` generator |
| `requirements.txt` | Python dependencies |
| `.env.example` | Configuration template |
| `recorder.py` | Records manual clicks to fix selectors |

---

## Data Flow

```text
.env → config.py → main.py
                  ↓
           facebook.py (Chrome/Playwright)
                  ↓
          Extract comments
                  ↓
           sentiment.py (LLM / keyword)
                  ↓
         Decide action
                  ↓
      Reply → Hide → Record history
```

---

## Configuration

Minimal `.env`:

```env
AI_PROVIDER=openai
AI_API_KEY=sk-...
CHROME_USER_DATA_DIR=C:/Users/<user>/AppData/Local/Google/Chrome/User Data
POST_URL=https://www.facebook.com/share/v/...
DRY_RUN=true
USE_LLM=true
HIDE_THRESHOLD=0.75
REPLY_THRESHOLD=0.85
REPLY_MESSAGE=Thank you for sharing your thoughts. We are looking into this.
MAX_COMMENTS=50
EXEMPT_AUTHORS=Fahad Hossen
HIDE_IMAGE_ONLY_COMMENTS=true
HISTORY_FILE=comment_history.json
RESCAN_DAYS=7
ASK_BEFORE_CLOSE=true
```

---

## Commands

```bash
# Install
pip install -r requirements.txt
python -m playwright install chromium

# Setup
python setup.py

# Run (dry-run by default)
python main.py

# Record clicks for selector fixes
python recorder.py
```

---

## Key Design Notes

- **Replies before hides**: a hidden comment cannot be replied to.
- **Image-only comments**: hidden directly without LLM when enabled.
- **History deduplication**: comments are SHA256-hashed by `author|text`; rescan window saves API cost.
- **Batch pending**: skipped comments are saved to `batch_pending.json` for future batch processing.
- **Fallback**: if LLM fails or `USE_LLM=false`, a keyword list (English + Bangla/Romanized-Bangla) is used.

---

## Recent Changes

- 2026-09-07: Vault reference note created. Pipeline: extract → LLM score → reply/hide → history.

---

## Related

- [[README]] — vault index
- [[LLM.md]] — AI assistant rules
- [[AGENTS.md]] — vault governance
