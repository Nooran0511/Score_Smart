# 📚 DEPLOYMENT GUIDE - STEP BY STEP

## ✅ CHECKLIST BEFORE DEPLOYING

- [x] Project builds successfully (`npm run build`)
- [x] All animations working
- [x] WhatsApp links functional
- [x] No console errors
- [x] Responsive on mobile
- [x] `.env.local` created
- [x] `.gitignore` created
- [x] README.md created

---

## 🔐 STEP 1: ENVIRONMENT VARIABLES

Your `.env.local` file is already created at:
```
e:\score-smart-website\score-smart\.env.local
```

**File Contents:**
```
NEXT_PUBLIC_WHATSAPP_PHONE=923158999139
```

✅ **This is done!** This file is in `.gitignore` so it won't be pushed to GitHub.

---

## 🐙 STEP 2: PUSH TO GITHUB

### 2.1 Create GitHub Account (if you don't have one)
- Go to https://github.com/signup
- Sign up with your email

### 2.2 Create a New Repository

**In your browser:**
1. Go to https://github.com/new
2. Fill in:
   - **Repository name:** `score-smart-website`
   - **Description:** `Score Smart IELTS Academy - Marketing Website`
   - **Visibility:** Public (for Vercel free tier)
3. Click **Create Repository**

### 2.3 Push Code from Terminal

**Run these commands in PowerShell:**

```powershell
# Navigate to project
cd e:\score-smart-website\score-smart

# Initialize git (if not already done)
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"

# Add all files
git add .

# Create first commit
git commit -m "Initial commit: Score Smart IELTS Academy website"

# Add remote repository (REPLACE with your URL)
git remote add origin https://github.com/YOUR_USERNAME/score-smart-website.git

# Rename branch to main
git branch -M main

# Push to GitHub
git push -u origin main
```

**Expected Output:**
```
Enumerating objects: ...
Counting objects: ...
Compressing objects: ...
Writing objects: ...
Total 123 (delta 0) ...
```

✅ **Check:** Go to your GitHub repo URL and verify all files are there!

---

## 🚀 STEP 3: DEPLOY TO VERCEL

### 3.1 Create Vercel Account

1. Go to https://vercel.com
2. Click **Sign Up**
3. Select **Continue with GitHub**
4. Authorize Vercel to access your GitHub

### 3.2 Create New Project

**In Vercel Dashboard:**
1. Click **New Project** (top right)
2. Click **Import** next to your `score-smart-website` repository
3. You should see the repo listed - click **Import**

### 3.3 Configure Project

**Project Settings:**
- **Framework Preset:** Next.js (auto-selected)
- **Root Directory:** Click **Edit** → Select `score-smart` folder
- **Build Settings:** Should auto-detect from `package.json`
  - Build Command: `npm run build`
  - Output Directory: `.next`
  - Install Command: `npm install`

### 3.4 Add Environment Variables

**IMPORTANT:** Before deployment, add environment variables!

1. Scroll down to **Environment Variables**
2. Click **Add**
3. Fill in:
   - **Name:** `NEXT_PUBLIC_WHATSAPP_PHONE`
   - **Value:** `923158999139`
   - **Environments:** Select all (Production, Preview, Development)
4. Click **Save**

### 3.5 Deploy

1. Click **Deploy** (blue button at bottom)
2. Wait for deployment... (takes 2-5 minutes)
3. You'll see:
   ```
   ✅ Deployment Complete
   Your live URL: https://score-smart-[random].vercel.app
   ```

✅ **Your site is LIVE!**

---

## 📋 STEP 4: VERIFY DEPLOYMENT

**Test your live site:**

1. Click the deployment URL from Vercel
2. Verify all sections load
3. Test scroll animations
4. Click WhatsApp buttons - should open WhatsApp
5. Try the enrollment form - should work

**If something's wrong:**
- Check Vercel **Deployments** tab for errors
- Click **Logs** to see build errors
- Common issues:
  - Missing env vars → Add in Vercel dashboard
  - Build failed → Check for TypeScript errors

---

## 🔄 STEP 5: FUTURE UPDATES

### Making Changes Locally

```powershell
# Make code changes...

# Stage and commit
git add .
git commit -m "Description of your changes"

# Push to GitHub
git push origin main
```

### Automatic Deployment

✅ **Vercel auto-deploys when you push to GitHub!**
- No manual redeploy needed
- Check Vercel dashboard to see deployment status
- Takes 1-3 minutes typically

---

## 📊 VERCEL DASHBOARD OVERVIEW

After deployment, your Vercel dashboard shows:

| Section | Purpose |
|---------|---------|
| **Deployments** | View all deployments & status |
| **Preview** | Test URLs for Pull Requests |
| **Production** | Your live domain |
| **Settings** | Environment variables, domain, etc. |
| **Analytics** | Traffic, performance metrics |
| **Logs** | Build and runtime errors |

---

## 🎯 CUSTOM DOMAIN (Optional)

Want to use custom domain like `scoresmartielts.com`?

1. **In Vercel Dashboard:**
   - Go to **Settings** → **Domains**
   - Click **Add**
   - Enter your domain: `scoresmartielts.com`

2. **In your Domain Host:**
   - Go to DNS settings
   - Add **CNAME record:**
     - Name: `www`
     - Value: (shown in Vercel)
   - Wait 10-30 minutes for DNS to update

✅ Your domain is now live!

---

## 🆘 TROUBLESHOOTING

### Build Failed
**Solution:**
- Check Vercel Logs
- Run `npm run build` locally first
- Fix any TypeScript/syntax errors

### Page Shows 404
**Solution:**
- Clear browser cache
- Hard refresh (Ctrl+Shift+R)
- Check if deployment is complete in Vercel dashboard

### Animations Not Working
**Solution:**
- Hard refresh browser (Ctrl+Shift+R)
- Check browser console (F12) for JS errors
- Try different browser

### WhatsApp Links Don't Work
**Solution:**
- Check `.env.local` has correct phone number
- Redeploy after updating env vars
- Wait for deployment to complete

---

## ✨ SUMMARY

**You've successfully:**
1. ✅ Created `.env.local` for environment config
2. ✅ Pushed code to GitHub
3. ✅ Deployed to Vercel
4. ✅ Added environment variables
5. ✅ Published live website!

**Your live website URL:**
```
https://score-smart-[random-id].vercel.app
```

🎉 **CONGRATULATIONS! YOUR WEBSITE IS LIVE!**

---

## 📞 Need Help?

- **Vercel Support:** https://vercel.com/support
- **GitHub Issues:** Create in your repo
- **Next.js Docs:** https://nextjs.org/docs
- **Troubleshooting:** See sections above
