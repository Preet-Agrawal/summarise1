# Environment Variables Setup Guide

## 🔐 How to Set Up Your GitHub Token

### For Local Development:

1. **Create a `.env` file** in your project root (same folder as `app.py`):
```
GITHUB_TOKEN=your_actual_github_token_here
```

2. **Replace `your_actual_github_token_here`** with your real GitHub token

3. **Install dependencies locally**:
```bash
pip install -r requirements.txt
```

4. **Run your app**:
```bash
python app.py
```

### For Deployment Platforms:

#### Railway:
1. Go to your project dashboard
2. Click on "Variables" tab
3. Add new variable:
   - **Name**: `GITHUB_TOKEN`
   - **Value**: `your_actual_github_token_here`

#### Render:
1. Go to your service dashboard
2. Click on "Environment" tab
3. Add environment variable:
   - **Key**: `GITHUB_TOKEN`
   - **Value**: `your_actual_github_token_here`

#### Vercel:
1. Go to your project dashboard
2. Click on "Settings" → "Environment Variables"
3. Add new variable:
   - **Name**: `GITHUB_TOKEN`
   - **Value**: `your_actual_github_token_here`

#### PythonAnywhere:
1. Go to your web app configuration
2. Scroll to "Environment variables"
3. Add:
   - **Name**: `GITHUB_TOKEN`
   - **Value**: `your_actual_github_token_here`

## 🔑 How to Get Your GitHub Token:

1. **Go to GitHub.com** and sign in
2. **Click your profile picture** → "Settings"
3. **Scroll down** → "Developer settings" (left sidebar)
4. **Click "Personal access tokens"** → "Tokens (classic)"
5. **Generate new token** → "Generate new token (classic)"
6. **Give it a name** (e.g., "Flask App API")
7. **Select scopes**: Check "repo" and "read:user"
8. **Click "Generate token"**
9. **Copy the token** (you won't see it again!)

## ⚠️ Important Security Notes:

- **NEVER commit your `.env` file** to Git
- **NEVER share your token** publicly
- **Use different tokens** for different projects
- **Rotate tokens** regularly

## 📁 File Structure:
```
your-project/
├── app.py
├── requirements.txt
├── Procfile
├── .env                    ← Your token goes here (local only)
├── templates/
│   └── index.html
└── static/
    └── style.css
```

## 🧪 Testing Your Setup:

1. **Create `.env` file** with your token
2. **Install requirements**: `pip install -r requirements.txt`
3. **Run app**: `python app.py`
4. **Test the API** by visiting your app

## 🚀 Deployment Checklist:

- [ ] GitHub token obtained
- [ ] `.env` file created (for local testing)
- [ ] Environment variable set in deployment platform
- [ ] App tested locally
- [ ] Code pushed to GitHub
- [ ] Deployed successfully 