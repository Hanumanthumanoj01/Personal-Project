# 💕 Anniversary Website — Deployment Guide (For Beginners!)

This is your personal anniversary website for Akka & Bawa. 
Follow the steps below — I'll explain everything like you're 10 years old. No worries! 😄

---

## 📁 Your Project Files

```
anniversary/
├── index.html        ← The actual website
├── app.py            ← Python server that serves it
├── requirements.txt  ← Python packages needed
├── Procfile          ← Tells the server how to run it
└── README.md         ← This file!
```

---

## 🖥️ STEP 1 — Install Python (if not already)

1. Go to https://www.python.org/downloads/
2. Download Python 3.11 or higher
3. Install it. On Windows, tick ✅ "Add Python to PATH" during install
4. Open your Terminal (Mac/Linux) or Command Prompt (Windows)
5. Type: `python --version` → Should say something like Python 3.11.x ✅

---

## 📦 STEP 2 — Install Git (if not already)

Git lets you upload your code to GitHub (which Render uses).

1. Go to https://git-scm.com/downloads
2. Download and install for your OS
3. Check it works: `git --version`

---

## 🐙 STEP 3 — Put Your Project on GitHub

GitHub is like Google Drive but for code.

1. Go to https://github.com and create a free account
2. Click the green **"New"** button to create a new repository
3. Name it: `anniversary-website`
4. Keep it **Public** (so Render can see it)
5. Click **"Create repository"**

Now go back to your Terminal/Command Prompt:

```bash
# Go into your project folder
cd path/to/anniversary

# Set up git
git init
git add .
git commit -m "My anniversary website 💕"

# Connect to GitHub (replace YOUR_USERNAME with yours)
git remote add origin https://github.com/YOUR_USERNAME/anniversary-website.git

# Push your code up
git branch -M main
git push -u origin main
```

Done! Your code is now on GitHub. 🎉

---

## 🚀 STEP 4 — Deploy on Render (FREE!)

Render is a free hosting service. Your website will get a real URL like:
`https://anniversary-website.onrender.com`

### Steps:

1. Go to https://render.com and sign up (use your GitHub account to sign in — easier!)
2. Click **"New +"** → Select **"Web Service"**
3. Click **"Connect a repository"** → Select `anniversary-website`
4. Fill in the form:
   - **Name:** `anniversary-website` (or anything you like)
   - **Runtime:** `Python 3`
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn app:app`
5. Scroll down, click **"Create Web Service"**
6. Wait 2-3 minutes while it builds ⏳
7. You'll get a green URL at the top — that's your website! 🎊

Share that URL with Akka and Bawa! 💕

---

## 🔄 STEP 5 — How to Update the Website Later

If you want to change something (e.g., add real photos):

1. Edit the files on your computer
2. Run these 3 commands in Terminal:
   ```bash
   git add .
   git commit -m "Updated the website"
   git push
   ```
3. Render auto-deploys in ~1 minute. Done! ✅

---

## 📸 STEP 6 — Adding Real Photos (Optional)

The gallery currently shows emoji placeholders. To add real photos:

1. Create a folder called `static/` inside your project
2. Put your images there (e.g., `wedding.jpg`)
3. In `index.html`, find the `.gallery-card` divs and replace:
   ```html
   <span>🌙</span>
   ```
   with:
   ```html
   <img src="/static/wedding.jpg" style="width:100%;height:100%;object-fit:cover;" />
   ```

---

## 🎵 Note on Background Music

The music uses a free source (bensound.com). If it doesn't play, it's likely because:
- The browser blocked autoplay (normal — user has to click the 🎵 button)
- The link changed. In that case, find another free MP3 and replace the URL in index.html.

---

## ❓ Common Issues

| Problem | Fix |
|---|---|
| `git: command not found` | Install Git from git-scm.com |
| `python: command not found` | Install Python from python.org |
| Render says "Build failed" | Check that `requirements.txt` exists and has `flask` and `gunicorn` |
| Website not loading | Wait 2-3 more minutes, Render's free tier is a bit slow to start |

---

## 💙 You're Done!

Send the link to Akka and watch her cry happy tears. 😄❤️

Made with love, for love.
