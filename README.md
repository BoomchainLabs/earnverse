# 🎮 Earnverse Sanity Studio

Welcome to the fullstack CMS dashboard powering the **Earnverse** rewards and trivia ecosystem. This studio manages content, user stats, token redemptions, and platform engagement data using [Sanity.io](https://www.sanity.io).

---

## 🛠️ Tech Stack

- **Sanity Studio v3**
- **Cloudflare Pages Deployment**
- **Custom Domain**: [`studio.boomchainlab.com`](https://studio.boomchainlab.com)
- **GitHub Repo**: [`BoomchainLabs/earnverse`](https://github.com/BoomchainLabs/earnverse)

---

## ⚙️ Local Development

### 1. 📦 Install dependencies

```bash
npm install


2. 🔐 Setup Environment
Create a .env file:
SANITY_AUTH_TOKEN=your_sanity_token_here
Get this token from https://www.sanity.io/manage/project/ba6nvctk

3. ▶️ Run locally
npm run dev
Sanity Studio will be live at http://localhost:3333


🧩 Structure Overview
.
├── sanity.config.ts        # Core config
├── schemas/                # Earnverse schemas
│   ├── userStats.ts
│   ├── rewardTokens.ts
│   └── dailyTrivia.ts
├── .env                    # Secrets (never commit this)
├── .github/workflows/
│   └── sanity-cloudflare.yml
└── README.md


🚀 Deployment on Cloudflare

This project auto-deploys on push to main via GitHub Actions + Cloudflare Pages.

Cloudflare Project Details:
	•	Project Name: Earnverse
	•	Project ID: ba6nvctk
	•	Org ID: oobQPS7og

Workflow Config: .github/workflows/sanity-cloudflare.yml
name: Deploy Sanity Studio to Cloudflare Pages

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Node
        uses: actions/setup-node@v4


        with:
          node-version: '20'
      - run: npm install
      - run: npm run build
      - name: Deploy to Cloudflare
        uses: cloudflare/pages-action@v1
        with:
          apiToken: ${{ secrets.CF_API_TOKEN }}
          accountId: ${{ secrets.CF_ACCOUNT_ID }}
          projectName: earnverse
          directory: dist

🌐 Domain & CORS Setup
sanity cors add https://studio.boomchainlab.com
📦 Build Commands
npm run build     # builds to /dist


🧠 Schema Customization

You can add/edit:
	•	userStats: Wallet-linked user performance
	•	rewardTokens: Config for airdrops, redeemables
	•	dailyTrivia: Daily quizzes tied to $CHONK9K earnings

⸻

📮 Support
	•	Email: support@boomchainlab.com
	•	Docs: Sanity Docs
	•	Live Studio: studio.boomchainlab.com

✅ Done

Once deployed, your team can manage trivia, leaderboards, rewards, and daily engagement data—all from a secure, headless CMS interface.
