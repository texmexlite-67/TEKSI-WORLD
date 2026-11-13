# 𝚃𝙴𝚇𝙼𝙴𝚇𝙻𝙸𝚃𝙴

### 𝙿𝙾𝚆𝙴𝚁𝙴𝙳 𝙱𝚈 𝚃𝙴𝙺𝚂𝙸 𝚆𝙾𝚁𝙻𝙳 ⚡

> A lite, fast, sci-fi styled **WhatsApp Multi-Device Bot** built on [Baileys MD](https://github.com/WhiskeySockets/Baileys).
> Pairing Code + QR Code • Plugin System • Sci-Fi Fonts • No API Key Needed

```
╔══════════════════════════════════════════════════════════════════════╗
║   ████████╗███████╗██╗  ██╗███╗   ███╗███████╗██╗  ██╗               ║
║   ╚══██╔══╝██╔════╝╚██╗██╔╝████╗ ████║██╔════╝╚██╗██╔╝               ║
║      ██║   █████╗   ╚███╔╝ ██╔████╔██║█████╗   ╚███╔╝                ║
║      ██║   ██╔══╝   ██╔██╗ ██║╚██╔╝██║██╔══╝   ██╔██╗                ║
║      ██║   ███████╗██╔╝ ██╗██║ ╚═╝ ██║███████╗██╔╝ ██╗               ║
║      ╚═╝   ╚══════╝╚═╝  ╚═╝╚═╝     ╚═╝╚══════╝╚═╝  ╚═╝               ║
║            𝚃𝙴𝚇𝙼𝙴𝚇𝙻𝙸𝚃𝙴  •  𝙿𝙾𝚆𝙴𝚁𝙴𝙳 𝙱𝚈 𝚃𝙴𝙺𝚂𝙸 𝚆𝙾𝚁𝙻𝙳              ║
╚══════════════════════════════════════════════════════════════════════╝
```

---

## ✨ Features

| Feature | Status |
|---|---|
| Multi-Device (Baileys MD) | ✅ |
| Pairing Code Login | ✅ |
| QR Code Login | ✅ |
| Auto-Reconnect | ✅ |
| Plugin / Command System | ✅ |
| Sci-Fi Fonts (`.font` command) | ✅ |
| Sticker Maker (`.sticker`) | ✅ |
| Public / Self Mode | ✅ |
| Owner Commands | ✅ |
| Lite — No Database Needed | ✅ |

## 📦 Requirements

- **Node.js 18+** — https://nodejs.org
- A WhatsApp number for the bot
- (For stickers) works out-of-the-box with `sharp`

## 🚀 Installation

```bash
# 1. Unzip
unzip TEXMEXLITE.zip
cd TEXMEXLITE

# 2. Install dependencies
npm install

# 3. Edit config
# Open config.js and change:
#   ownerNumber: ["2547XXXXXXXX"]   <-- your number
#   pairingNumber: ""               <-- bot number for pairing code, or leave "" for QR

# 4. Start
npm start
```

## 🔗 Pairing (Recommended)

1. Run `npm start`
2. Choose `y` for Pairing Code
3. Enter the bot's WhatsApp number (e.g. `2547XXXXXXXX`)
4. Copy the 8-digit code shown
5. On your phone: **WhatsApp → Settings → Linked Devices → Link a Device → Link with phone number instead**
6. Enter the code — done! ✅

> Or just scan the QR code in the terminal if you choose `n`.

## 💬 Commands

| Command | Description |
|---|---|
| `.menu` / `.help` | Show sci-fi menu |
| `.ping` | Speed / latency test |
| `.alive` | Bot status |
| `.runtime` | Uptime |
| `.owner` | Owner contact card |
| `.info` | Bot information |
| `.font <text>` | Convert text to 5 sci-fi fonts |
| `.sticker` | Reply to image → sticker |
| `.say <text>` | Bot repeats text |
| `.joke` | Random joke |
| `.eval <code>` | Owner only |

**Prefix is changeable in `config.js` (default `.`)**

## 🔤 Sci-Fi Fonts

All bot text uses WhatsApp-native Unicode sci-fi fonts — no images needed:

- 𝙼𝙾𝙽𝙾𝚂𝙿𝙰𝙲𝙴 — `𝚃𝙴𝚇𝙼𝙴𝚇𝙻𝙸𝚃𝙴`
- 𝐁𝐎𝐋𝐃 — `𝐓𝐄𝐊𝐒𝐈 𝐖𝐎𝐑𝐋𝐃`
- 𝔻𝕆𝕌𝔹𝕃𝔼 — `𝕋𝔼𝕏𝕄𝔼𝕏`
- 𝗦𝗔𝗡𝗦 𝗕𝗢𝗟𝗗 — `𝗧𝗘𝗫𝗠𝗘𝗫𝗟𝗜𝗧𝗘`
- ꜱᴍᴀʟʟ ᴄᴀᴘꜱ — `ᴛᴇxᴍᴇxʟɪᴛᴇ`

Try it in chat: `.font TEXMEXLITE`

For the logo / banners on a PC, use a sci-fi font like **Orbitron, Audiowede, Zen Dots** (Google Fonts, free) with the text `TEXMEXLITE — POWERED BY TEKSI WORLD`.

## 🧩 Adding Your Own Command

Create `plugins/mycommand.js`:

```js
module.exports = {
    command: ['hello'],
    description: 'Say hello',
    handler: async ({ reply, senderNumber }) => {
        reply(`Hello @${senderNumber}! ⚡ TEXMEXLITE`);
    }
};
```

Restart the bot — done. No other files to edit.

## ☁️ Deploy (Optional)

- **Panel / VPS:** `npm install && npm start`, keep alive with `pm2 start index.js --name texmexlite`
- **Termux (Android):**
  ```bash
  pkg install nodejs git
  npm install
  npm start
  ```
- **Heroku / Render / Railway:** Use `npm start` as start command, Node 18+. Note: session folder must persist or re-pair on restart.

## ⚠️ Disclaimer

This is an unofficial WhatsApp bot using the Baileys library. Use at your own risk, respect WhatsApp's Terms of Service, and don't use it for spam. Use a separate number for the bot where possible.

## 👑 Credits

**𝚃𝙴𝚇𝙼𝙴𝚇𝙻𝙸𝚃𝙴 — 𝙿𝙾𝚆𝙴𝚁𝙴𝙳 𝙱𝚈 𝚃𝙴𝙺𝚂𝙸 𝚆𝙾𝚁𝙻𝙳**

Built with Baileys MD • Sci-Fi Fonts • TEKSI WORLD
