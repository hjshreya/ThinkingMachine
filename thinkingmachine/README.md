# 思考 - Socratic Thinking Tool (Gemini - SIMPLIFIED)

**This is a simplified version that works 100% with Vercel!**

## Quick Deploy Steps

### 1. Get Gemini API Key (FREE)
- Go to: https://aistudio.google.com/app/apikey
- Click "Create API Key"
- Copy it

### 2. Deploy to Vercel

#### METHOD 1: GitHub (Recommended)
1. Create a new GitHub repository
2. Upload ALL files from this folder to the repo
3. Go to vercel.com
4. Click "New Project"
5. Import your GitHub repo
6. Click "Deploy" (don't change any settings)

#### METHOD 2: Vercel CLI
```bash
npm i -g vercel
cd socratic-gemini-simple
vercel
```

### 3. Add Environment Variable
1. In Vercel dashboard → Your Project
2. Settings → Environment Variables
3. Add:
   - Name: `GEMINI_API_KEY`
   - Value: (your API key)
   - Environment: Production
4. Save

### 4. Redeploy
- Go to Deployments tab
- Click "..." on latest deployment
- Click "Redeploy"

## What's Different in This Version?

This is a **super simplified structure** that Vercel recognizes immediately:
- Minimal `vercel.json` (no complex routing)
- `index.html` in root (Vercel auto-serves this)
- `api/` folder for serverless functions
- No build steps needed

## Troubleshooting

**Still getting 404?**
1. Make sure you uploaded ALL files
2. Check that `index.html` is in the ROOT, not in a subfolder
3. Make sure `api/chat.js` is inside an `api/` folder

**API not working?**
1. Verify `GEMINI_API_KEY` is set in Environment Variables
2. Make sure you clicked "Redeploy" after adding the variable
3. Check Function Logs in Vercel for errors

## File Structure Should Look Like:
```
your-project/
├── index.html          ← Homepage (must be in root!)
├── api/
│   └── chat.js        ← API endpoint
├── package.json
└── vercel.json
```

That's it! Simple and works every time.
