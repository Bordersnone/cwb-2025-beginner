# Render Deployment Check

This guide will help you confirm that your Render deployment is set up correctly and working.

## Step 1: Check Your GitHub Repository

First, make sure your GitHub repository is properly set up:

1. Go to GitHub and navigate to your repository
2. Verify that your repository contains an `index.html` file
3. Check that the file has some basic HTML content

## Step 2: Verify Render Connection

1. Log in to [Render](https://render.com)
2. Go to your Dashboard
3. Find your web service (it should be listed with your project name)
4. Click on the service to view its details

## Step 3: Check the GitHub Connection

In your Render service details:

1. Look for the "GitHub" section
2. Verify that it shows your correct repository name
3. Check that the branch is set to `main` (or your default branch)

## Step 4: Trigger a Manual Deploy

If your site isn't deployed yet, or you want to redeploy:

1. Click the **"Manual Deploy"** button in Render
2. Select **"Deploy latest commit"**
3. Wait for the deployment to complete (you'll see a log output)
4. Look for a success message like "Build successful" or "Deploy live"

## Step 5: Visit Your Live Site

1. In your Render dashboard, find the URL for your site (it will look like `https://your-project-name.onrender.com`)
2. Click the URL or copy it into a new browser tab
3. You should see your `index.html` page displayed

## Troubleshooting

### My site shows a 404 error

- Make sure your `index.html` file is in the root directory of your repository (not in a subfolder)
- Check that the file name is exactly `index.html` (lowercase)

### The deployment failed

- Check the deployment logs in Render for error messages
- Verify your HTML file doesn't have syntax errors
- Make sure your latest changes have been pushed to GitHub

### Changes aren't showing up

- Render automatically deploys when you push to GitHub, but it may take a minute
- Try a hard refresh in your browser: `Cmd+Shift+R` (Mac) or `Ctrl+Shift+R` (Windows)
- Check the "Events" tab in Render to see if a new deployment was triggered

## Commands Reference

```bash
# Check your current git status
git status

# View your remote repository URL
git remote -v

# Push changes to GitHub (triggers Render deployment)
git push origin main
```

## Success Checklist

- ✅ GitHub repository exists and contains `index.html`
- ✅ Render service is connected to the correct repository
- ✅ Deployment completed successfully
- ✅ Live site URL loads your HTML page

---

[← Back to Class 7](./)
