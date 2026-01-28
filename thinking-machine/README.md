# 思考 (Shikō) - Socratic Thinking Tool (Gemini Version)

A beautiful AI-powered tool that guides your thinking through Socratic questioning instead of providing direct answers. **This version uses Google's Gemini API.**

## Features

- **Powered by Google Gemini**: Uses Gemini 1.5 Flash for fast, intelligent responses
- **No Direct Answers**: The AI guides through carefully crafted questions
- **Socratic Method**: Examines assumptions, explores implications, encourages deeper analysis
- **Elegant Design**: Clean, literary aesthetic that encourages contemplation
- **Serverless Architecture**: Built for Vercel with edge functions

## Deployment Instructions

### 1. Get Your Gemini API Key (FREE!)

1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy your API key

**Note**: Gemini has a generous free tier, perfect for personal projects!

### 2. Deploy to Vercel

#### Option A: Deploy with Vercel CLI

```bash
# Install Vercel CLI globally
npm i -g vercel

# Navigate to the project directory
cd socratic-tool-gemini

# Deploy
vercel

# Follow the prompts
```

#### Option B: Deploy via Vercel Dashboard

1. Push this folder to a GitHub repository
2. Go to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will auto-detect the configuration

### 3. Add Your API Key as Environment Variable

After deployment:

1. Go to your project in Vercel Dashboard
2. Click "Settings" → "Environment Variables"
3. Add a new variable:
   - **Name**: `GEMINI_API_KEY`
   - **Value**: Your API key from step 1
   - **Environment**: Production (and Preview if you want)
4. Click "Save"
5. **Important**: Redeploy your project
   - Go to Deployments
   - Click the three dots on the latest deployment
   - Click "Redeploy"

### 4. Test Your Deployment

Visit your Vercel URL (e.g., `your-project.vercel.app`) and start exploring your thoughts!

## Project Structure

```
socratic-tool-gemini/
├── api/
│   └── chat.js          # Serverless function for Gemini API
├── index.html           # Main HTML file with UI
├── vercel.json          # Vercel configuration
├── package.json         # Project metadata
└── README.md           # This file
```

## How It Works

1. **Frontend** (`index.html`): 
   - User types their question
   - Sends request to `/api/chat`
   - Displays the AI's guiding questions

2. **Backend** (`api/chat.js`):
   - Receives the request
   - Converts messages to Gemini format
   - Calls Google's Gemini API with your key
   - Converts response back and returns to frontend

3. **Security**:
   - API key stored in Vercel environment variables (never exposed)
   - CORS headers properly configured
   - Input validation on both client and server

## Local Development

```bash
# Install Vercel CLI
npm i -g vercel

# Create .env file with your API key
echo "GEMINI_API_KEY=your_key_here" > .env

# Run local development server
vercel dev

# Open http://localhost:3000
```

## Why Gemini?

- **Free Tier**: Generous free quota for personal projects
- **Fast**: Gemini 1.5 Flash is optimized for speed
- **Capable**: Excellent at conversational AI tasks
- **Easy Setup**: Quick API key generation

## Gemini API Limits (Free Tier)

- 15 requests per minute
- 1,500 requests per day
- 1 million tokens per day

Perfect for personal use and testing!

## Troubleshooting

**"Something went wrong" error:**
- Verify you've added `GEMINI_API_KEY` environment variable in Vercel
- Make sure you've redeployed after adding the variable
- Check the Vercel function logs for detailed errors

**API key issues:**
- Verify your API key at [Google AI Studio](https://aistudio.google.com/app/apikey)
- Ensure no extra spaces in the environment variable
- Check that API key has not been revoked

**Rate limit errors:**
- Free tier has 15 requests/minute limit
- Wait a minute and try again
- Consider upgrading if you need higher limits

## Switching from Claude to Gemini

The main differences:
- **Environment Variable**: Use `GEMINI_API_KEY` instead of `ANTHROPIC_API_KEY`
- **Model**: Uses Gemini 1.5 Flash (fast and efficient)
- **API Format**: Automatically converted in the serverless function
- **Cost**: Free tier available (Claude requires payment)

## Customization

Edit the `systemPrompt` in `index.html` (around line 328) to change how the AI guides thinking.

## License

MIT

---

Made with thoughtful consideration 思  
Powered by Google Gemini 🌟
