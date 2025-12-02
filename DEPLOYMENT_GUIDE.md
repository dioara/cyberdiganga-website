# 🚀 Deployment Guide: GitHub + Vercel

This guide will help you deploy the CyberDiganga Consulting website to GitHub and then to Vercel for free hosting.

## 📋 Prerequisites

- GitHub account ([Sign up here](https://github.com))
- Vercel account ([Sign up here](https://vercel.com))
- Git installed on your computer

## 🔧 Method 1: Using GitHub CLI (Recommended)

### Step 1: Authenticate with GitHub
```bash
gh auth login
```
Follow the prompts to authenticate with your GitHub account.

### Step 2: Create Repository and Push
```bash
# Navigate to the project directory
cd cyberdiganga-website

# Create GitHub repository
gh repo create cyberdiganga-website --public --description "Professional website for CyberDiganga Consulting Limited"

# Push code to GitHub
git remote add origin https://github.com/YOUR_USERNAME/cyberdiganga-website.git
git branch -M main
git push -u origin main
```

## 🌐 Method 2: Manual GitHub Setup

### Step 1: Create Repository on GitHub
1. Go to [GitHub](https://github.com)
2. Click "New repository"
3. Name: `cyberdiganga-website`
4. Description: `Professional website for CyberDiganga Consulting Limited`
5. Make it **Public**
6. **Don't** initialize with README (we already have one)
7. Click "Create repository"

### Step 2: Push Local Code
```bash
# Navigate to project directory
cd cyberdiganga-website

# Add GitHub remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/cyberdiganga-website.git

# Rename branch to main
git branch -M main

# Push to GitHub
git push -u origin main
```

## ⚡ Deploy to Vercel

### Option A: One-Click Deploy
1. Go to your GitHub repository
2. Click the "Deploy with Vercel" button in the README
3. Sign in to Vercel with GitHub
4. Click "Deploy"
5. Your site will be live in seconds!

### Option B: Manual Vercel Setup
1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Click "New Project"
3. Import your GitHub repository
4. Configure:
   - **Framework Preset**: Other
   - **Root Directory**: `./`
   - **Build Command**: Leave empty
   - **Output Directory**: Leave empty
5. Click "Deploy"

## 🎯 Post-Deployment Steps

### 1. Update Repository URL
After creating the GitHub repository, update the repository URL in:
- `package.json` (line 19)
- `README.md` (Vercel button link)

### 2. Custom Domain (Optional)
1. In Vercel dashboard, go to your project
2. Click "Settings" → "Domains"
3. Add your custom domain
4. Follow DNS configuration instructions

### 3. Environment Variables (If needed)
If you add backend functionality later:
1. Go to Vercel project settings
2. Click "Environment Variables"
3. Add any required variables

## 🔄 Making Updates

### Update Website Content
```bash
# Make your changes to files
# Then commit and push
git add .
git commit -m "Update website content"
git push
```

Vercel will automatically redeploy when you push to GitHub!

## 📊 Monitoring & Analytics

### Vercel Analytics
1. Go to your Vercel project
2. Click "Analytics" tab
3. Enable analytics for visitor insights

### Google Analytics (Optional)
Add this to `index.html` before `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🛠 Troubleshooting

### Common Issues

**Issue**: Git push fails with authentication error
**Solution**: 
```bash
gh auth login
# Or use personal access token
```

**Issue**: Vercel build fails
**Solution**: Check that all files are committed and pushed to GitHub

**Issue**: Images not loading
**Solution**: Ensure image paths are relative (e.g., `assets/images/image.jpg`)

### Getting Help
- [Vercel Documentation](https://vercel.com/docs)
- [GitHub Documentation](https://docs.github.com)
- [GitHub CLI Documentation](https://cli.github.com/manual/)

## 🎉 Success!

Once deployed, your website will be available at:
- **Vercel URL**: `https://cyberdiganga-website.vercel.app`
- **Custom Domain**: (if configured)

The website will automatically update whenever you push changes to GitHub!

---

**Need help?** Feel free to reach out for assistance with the deployment process.
