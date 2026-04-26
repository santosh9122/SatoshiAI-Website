# SatoshiAI — Official Website

**AI-Powered Web3 Ecosystem on Solana**

Live site: [satoshi-ai.netlify.app](https://satoshi-ai.netlify.app)  
Twitter: [@satosi_ai](https://x.com/satosi_ai)  
Telegram: [t.me/satosiiAI](https://t.me/satosiiAI)  
Contract: `BHSd65jRJz3hnzKtuwnmCWWah3qwNVKZ6bHg4wLmri7i`

---

## Project Overview

SatoshiAI (satAI) is a next-generation AI-powered blockchain ecosystem built on Solana,
designed to merge decentralised finance, automation, and intelligent systems into a unified
Web3 infrastructure. This repository contains the complete source code for the official
SatoshiAI marketing and information website.

---

## Repository Structure

```
satoshiai-website/
├── index.html               ← Main website (rename from satoshiai-final.html)
├── admin.html               ← Password-protected admin panel
├── config.json              ← Site configuration (banner, links, analytics)
├── netlify.toml             ← Netlify deployment configuration
├── satoshiai-whitepaper.pdf ← Official project whitepaper
├── satoshiai-logo.png       ← Project logo
└── README.md                ← This file
```

---

## Tech Stack

- **Frontend:** HTML5, CSS3, Vanilla JavaScript
- **Blockchain:** Solana Web3.js (@solana/web3.js)
- **Wallet:** Phantom Wallet integration
- **Fonts:** Google Fonts (Orbitron, Outfit)
- **Deployment:** Netlify (static hosting)
- **Analytics:** Google Analytics 4 (via config.json)

---

## Features

- Phantom wallet connect / disconnect
- Live satAI token balance from Solana mainnet
- Click-to-copy contract address
- Whitepaper PDF download
- Admin panel with password protection
- Announcement banner system
- Google Analytics 4 event tracking
- Fully responsive (mobile, tablet, desktop)
- SEO optimised (Open Graph, Twitter Card, meta tags)

---

## Configuration

All site content is managed via `config.json`. Edit this file and redeploy to:

- Enable or disable the announcement banner
- Update Telegram, Twitter, and Discord links
- Add your Google Analytics GA4 Measurement ID

```json
{
  "announcement": {
    "enabled": false,
    "text": "Your announcement here",
    "link": "https://t.me/satosiiAI"
  },
  "social": {
    "telegram": "https://t.me/satosiiAI",
    "twitter": "https://x.com/satosi_ai",
    "discord": "#"
  },
  "analytics": {
    "gaId": ""
  }
}
```

---

## Admin Panel

Access at: `https://yoursite.netlify.app/admin.html`

Default credentials:
- Username: `admin`
- Password: `SatoshiAI2026!`

**Change your password after first login.**

The admin panel allows you to:
- Toggle the announcement banner on/off
- Update all social media links
- Add your Google Analytics ID
- Export an updated `config.json` to upload to Netlify

---

## Deployment

See `HOSTING_GUIDE.md` for full step-by-step instructions on how to deploy
this site from GitHub to Netlify.

Quick steps:
1. Push this repository to GitHub
2. Connect GitHub repo to Netlify
3. Netlify auto-detects `netlify.toml` and deploys

---

## Token Information

| Field | Value |
|-------|-------|
| Name | SatoshiAI |
| Symbol | satAI |
| Network | Solana |
| Decimals | 9 |
| Total Supply | 1,000,000,000 |
| Contract | BHSd65jRJz3hnzKtuwnmCWWah3qwNVKZ6bHg4wLmri7i |

### Token Distribution

| Allocation | Percentage |
|------------|------------|
| Vault (Long-term stability) | 45% |
| Liquidity | 20% |
| Development | 15% |
| Marketing | 10% |
| Team | 10% |

---

## Future Updates

The following will be integrated after DEX listing:

- **Live price chart** — DexScreener/Jupiter embed (requires liquidity pool address)
- **Buy button** — Direct swap link on Raydium (requires pool address)
- **Holder count** — Live data via Solscan API

---

## Security

- No private keys or seed phrases are ever requested or stored
- All smart contract interactions are read-only (balance display)
- Admin panel credentials are stored locally in browser localStorage
- Developer access has been fully removed after project handover

---

## License

All rights reserved. © 2026 SatoshiAI Ecosystem.
