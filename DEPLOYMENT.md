# Deployment Guide: Host on Render

Follow these steps to deploy your NeuralFlow landing page to Render.

## ✅ Already Completed

- [x] Git repository initialized
- [x] All files committed to Git
- [x] Render configuration file created (`render.yaml`)

## 📋 Next Steps

### Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the **"+"** icon in the top-right corner
3. Select **"New repository"**
4. Fill in the details:
   - **Repository name:** `neuralflow-landing` (or your preferred name)
   - **Description:** "Production-ready SaaS landing page with distinctive design"
   - **Visibility:** Public (Render free tier requires public repos)
   - **DO NOT** initialize with README (we already have one)
5. Click **"Create repository"**

### Step 2: Push Code to GitHub

After creating the repository, GitHub will show you commands. Use these:

```bash
# Add the remote repository
git remote add origin https://github.com/YOUR_USERNAME/neuralflow-landing.git

# Push your code
git branch -M main
git push -u origin main
```

**Replace `YOUR_USERNAME`** with your actual GitHub username!

### Step 3: Deploy to Render

1. Go to [Render](https://render.com) and sign in (or create a free account)

2. Click **"New +"** in the top-right corner

3. Select **"Static Site"**

4. Connect your GitHub account if you haven't already:
   - Click **"Connect GitHub"**
   - Authorize Render to access your repositories

5. Find and select your **`neuralflow-landing`** repository

6. Configure the deployment:
   - **Name:** `neuralflow-landing` (or your preferred name)
   - **Branch:** `main`
   - **Build Command:** Leave empty (or use: `echo "No build needed"`)
   - **Publish Directory:** `.` (current directory)

7. Click **"Create Static Site"**

### Step 4: Wait for Deployment

Render will now:
- Clone your repository
- Deploy your static site
- Provide you with a live URL (e.g., `https://neuralflow-landing.onrender.com`)

This usually takes **1-2 minutes**.

### Step 5: View Your Live Site!

Once deployed, you'll see:
- ✅ **Status:** "Live"
- 🔗 **URL:** Your live site link

Click the URL to view your NeuralFlow landing page live on the internet!

## 🎉 Success!

Your landing page is now hosted on Render with:
- ✨ Automatic HTTPS
- 🚀 Global CDN
- 🔄 Auto-deploy on git push
- 📊 Free hosting for static sites

## 🔄 Making Updates

Whenever you want to update your site:

1. Make changes to your HTML file locally
2. Commit the changes:
   ```bash
   git add .
   git commit -m "Update landing page design"
   git push
   ```
3. Render will automatically detect the push and redeploy (takes 1-2 minutes)

## 🛠️ Troubleshooting

**Issue: "Page not found" error**
- Make sure `index.html` exists in your repository
- Check that the publish directory is set to `.`

**Issue: "Build failed"**
- Since this is a static site, you can leave the build command empty
- Or set it to: `echo "No build needed"`

**Issue: Render shows old version**
- Clear your browser cache
- Wait 1-2 minutes for deployment to complete
- Check the "Events" tab in Render dashboard for deployment status

## 📚 Additional Resources

- [Render Static Sites Documentation](https://render.com/docs/static-sites)
- [GitHub Documentation](https://docs.github.com)
- [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

## 💡 Pro Tips

1. **Custom Domain:** You can add a custom domain in Render settings (free on all plans)
2. **Preview Deploys:** Enable pull request previews in Render settings
3. **Environment:** Render automatically sets up HTTPS for all sites
4. **Analytics:** Consider adding Google Analytics or Plausible for tracking

---

**Need help?** Check the Render dashboard for deployment logs and status.
