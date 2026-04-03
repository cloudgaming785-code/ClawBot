# ClawBot
//
~/phone_control.sh && chmod +x ~/phone_control.sh
curl -sL https://raw.githubusercontent.com/orailnoor/orailnoor-CloudBot-Termux/main/phone_agent.sh > ~/phone_agent.sh && chmod +x ~/phone_agent.sh
curl -sL https://raw.githubusercontent.com/orailnoor/orailnoor-CloudBot-Termux/main/AGENTS.md > ~/.openclaw/workspace/AGENTS.md
```

**6. Start the bot:**
```bash
openclaw gateway --verbose
```

Done! Send a message to your Telegram bot 🎉

---

## 🧠 How It Works

```
You (Telegram) → OpenClaw Gateway → AI Model (Gemini) → Shell Commands → Your Phone
```

1. You send a message via Telegram
2. OpenClaw receives it and sends to Gemini AI
3. Gemini decides which command to run
4. The command executes on your phone
5. Result is sent back to Telegram

### Vision Agent (Advanced)
For complex tasks like navigating app UIs, the **Vision Agent** (`phone_agent.sh`):
- Takes a screenshot of your phone
- Sends it to Gemini Vision API
- AI decides where to tap/swipe/type
- Repeats until task is complete

---

## 📋 Available Commands

| Command | What it does |
|---------|-------------|
| `bash ~/phone_control.sh open-app <pkg>` | Open any app |
| `bash ~/phone_control.sh youtube-search "<query>"` | Search YouTube directly |
| `bash ~/phone_control.sh open-url "<url>"` | Open any URL |
| `bash ~/phone_control.sh whatsapp-send <num> "<msg>"` | Send WhatsApp message |
| `bash ~/phone_control.sh playstore-search "<app>"` | Search Play Store |
| `bash ~/phone_control.sh wifi on/off` | Toggle WiFi |
| `bash ~/phone_control.sh bluetooth on/off` | Toggle Bluetooth |
| `bash ~/phone_control.sh brightness <0-255>` | Set brightness |
| `bash ~/phone_control.sh battery` | Check battery level |
| `bash ~/phone_control.sh call <number>` | Make a phone call |
| `bash ~/phone_control.sh send-sms <num> "<msg>"` | Send SMS |
| `bash ~/phone_control.sh screenshot` | Take screenshot |
| `bash ~/phone_agent.sh "<task>"` | AI Vision agent |

---

## 💰 Cost

Uses **Gemini 2.5 Flash Lite** — Google's cheapest AI model:

| Usage | Monthly Cost |
|---|---|
| Light (10 tasks/day) | ~$0.24 |
| Medium (50 tasks/day) | ~$1.20 |
| Heavy (200 tasks/day) | ~$4.80 |

**Free tier:** 1,500 requests/day at no cost!

---

## 🔧 Troubleshooting

| Issue | Fix |
|---|---|
| "Gateway service not supported" | Normal on Android — run `openclaw gateway --verbose` manually |
| Magisk root toast notifications | Magisk → Settings → Superuser Notification → None |
| Screen flipped | `adb shell settings put system user_rotation 0` |

---

## 📄 License

MIT License — use freely!

---
