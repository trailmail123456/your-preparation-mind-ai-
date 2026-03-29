# PrepMind AI — Deployment Guide

## Project Structure
```
prepmind-deploy/
├── index.html                  ← Main app
├── netlify.toml                ← Netlify config
├── vercel.json                 ← Vercel config
├── netlify/functions/
│   └── claude.js               ← Netlify serverless proxy
└── api/
    └── claude.js               ← Vercel serverless proxy
```

---

## 🚀 Deploy on Netlify (Free)

1. Go to https://netlify.com → Sign up / Log in
2. Click **"Add new site"** → **"Deploy manually"**
3. Drag and drop this entire folder
4. Once deployed, go to **Site Settings → Environment Variables**
5. Add:
   - Key: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...` (your key from console.anthropic.com)
6. Go to **Deploys → Trigger deploy** to redeploy with the env var
7. Done! Your site is live 🎉

---

## 🚀 Deploy on Vercel (Free)

### Option A — Vercel CLI
```bash
npm i -g vercel
cd prepmind-deploy
vercel
```

### Option B — Vercel Dashboard
1. Go to https://vercel.com → Sign up / Log in
2. Click **"Add New Project"** → Import or drag folder
3. After deploy, go to **Project Settings → Environment Variables**
4. Add:
   - Key: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...`
5. Redeploy — Done! 🎉

---

## 🔑 Get your Anthropic API Key
1. Go to https://console.anthropic.com
2. Sign in → API Keys → Create Key
3. Copy the `sk-ant-...` key and add it as the env variable above

## ⚠️ Important
- NEVER put your API key directly in index.html
- The serverless function keeps the key server-side and secure
- Free tier on both Netlify & Vercel is sufficient for personal use
