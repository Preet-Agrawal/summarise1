# Deployment Guide for Flask App

## Option 1: Railway (Recommended - Free)

1. **Sign up** at [railway.app](https://railway.app)
2. **Connect your GitHub** account
3. **Create a new project** and select "Deploy from GitHub repo"
4. **Select your repository**
5. **Add environment variables**:
   - `GITHUB_TOKEN`: Your GitHub token for the API
6. **Deploy** - Railway will automatically detect it's a Python app and deploy

## Option 2: Render (Free)

1. **Sign up** at [render.com](https://render.com)
2. **Connect your GitHub** account
3. **Create a new Web Service**
4. **Select your repository**
5. **Configure**:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
6. **Add environment variables**:
   - `GITHUB_TOKEN`: Your GitHub token
7. **Deploy**

## Option 3: Vercel (Free)

1. **Sign up** at [vercel.com](https://vercel.com)
2. **Install Vercel CLI**: `npm i -g vercel`
3. **Create vercel.json** in your project root:
```json
{
  "version": 2,
  "builds": [
    {
      "src": "app.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "app.py"
    }
  ]
}
```
4. **Deploy**: `vercel`

## Option 4: PythonAnywhere (Free)

1. **Sign up** at [pythonanywhere.com](https://pythonanywhere.com)
2. **Upload your files** or clone from GitHub
3. **Create a new web app** (Flask)
4. **Set up your virtual environment** and install requirements
5. **Configure WSGI file** to point to your app
6. **Add environment variables** in the web app settings

## Environment Variables

Make sure to set these in your deployment platform:
- `GITHUB_TOKEN`: Your GitHub token for the API

## Local Testing

Before deploying, test locally:
```bash
pip install -r requirements.txt
python app.py
```

## Important Notes

- Your app uses the GitHub Copilot Models API, so you'll need a valid `GITHUB_TOKEN`
- The app is configured to run on any port (useful for cloud platforms)
- Debug mode is disabled for production
- CORS is enabled for cross-origin requests 