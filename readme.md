# Draft Board Analyzer Backend

This is the backend service that powers the "Parse with AI" feature in the Draft Board Analyzer..

## Deployment to Vercel (Free)

### Prerequisites
- A Vercel account (sign up at https://vercel.com)
- Your Anthropic API key

### Steps

1. **Create a GitHub repo** (if you don't have one):
   - Go to https://github.com/new
   - Name it "draft-board-backend"
   - Create and push these files there

2. **Deploy to Vercel**:
   - Go to https://vercel.com/import
   - Select "GitHub" and choose your repo
   - Set the environment variable:
     - Name: `ANTHROPIC_API_KEY`
     - Value: Your API key (sk-ant-api03-...)
   - Click "Deploy"

3. **Get your API URL**:
   - After deployment, Vercel gives you a URL like: `https://draft-board-backend.vercel.app`
   - Your endpoint is: `https://draft-board-backend.vercel.app/api/parse`

4. **Update your Draft Board**:
   - In the HTML file, find the `callClaudeAPI` function
   - Change the fetch URL from `https://api.anthropic.com/v1/messages` to your Vercel URL
   - Example: Replace the fetch with:
```javascript
   res = await fetch('https://draft-board-backend.vercel.app/api/parse', {
```

That's it! The Parse with AI button will now work.

## Local Development

```bash
npm install
node api/parse.js
```

Then test by POSTing to `http://localhost:3000/api/parse`
