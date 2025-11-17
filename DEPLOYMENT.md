# 🚀 Deployment Guide for Des&Co. Newsletter Funnel

This guide provides multiple options for deploying your newsletter funnel. Choose the one that works best for you.

---

## Option 1: Netlify (Recommended - Easiest)

### Method A: Deploy from GitHub

1. Go to [netlify.com](https://netlify.com) and sign in
2. Click "Add new site" → "Import an existing project"
3. Choose "GitHub" and authorize Netlify
4. Select repository: `test-repo-1750335658167`
5. Configure build settings:
   - **Branch to deploy**: `claude/desco-newsletter-funnel-012aW4pyogaKEyFDzie7exjc` (or merge to main first)
   - **Build command**: Leave empty
   - **Publish directory**: `.`
6. Click "Deploy site"

Your site will be live at a Netlify URL (e.g., `https://random-name-12345.netlify.app`)

### Method B: Netlify Drop (Manual)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop the entire project folder
3. Your site is instantly live!

**Note:** `netlify.toml` is already configured for you.

---

## Option 2: Vercel

1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "Add New" → "Project"
3. Import your GitHub repository: `test-repo-1750335658167`
4. Configure project:
   - **Framework Preset**: Other
   - **Build Command**: Leave empty
   - **Output Directory**: `.`
5. Click "Deploy"

Your site will be live at a Vercel URL (e.g., `https://desco-newsletter.vercel.app`)

**Note:** `vercel.json` is already configured for you.

---

## Option 3: GitHub Pages

### Step 1: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/Dest-89/test-repo-1750335658167`
2. Click "Settings" → "Pages"
3. Under "Source", select:
   - **Branch**: `claude/desco-newsletter-funnel-012aW4pyogaKEyFDzie7exjc`
   - **Folder**: `/ (root)`
4. Click "Save"

### Step 2: Wait for Deployment

GitHub will automatically deploy your site. It may take 1-2 minutes.

Your site will be live at:
```
https://dest-89.github.io/test-repo-1750335658167/
```

### Alternative: Create gh-pages branch

If you prefer a dedicated deployment branch:

```bash
# Create and switch to gh-pages branch
git checkout -b gh-pages

# Push to GitHub
git push -u origin gh-pages

# Go to Settings → Pages and select gh-pages branch
```

---

## Option 4: Cloudflare Pages

1. Go to [pages.cloudflare.com](https://pages.cloudflare.com)
2. Sign in and click "Create a project"
3. Connect to your GitHub repository
4. Configure build:
   - **Build command**: Leave empty
   - **Build output directory**: `/`
5. Click "Save and Deploy"

---

## Option 5: Custom Server (Advanced)

### Using a Simple HTTP Server

If you have a web server, simply upload these files to your web root:
- `index.html`
- `thank-you.html`

### Using Node.js locally (for testing)

```bash
# Install a simple HTTP server
npm install -g http-server

# Run the server
http-server .

# Visit http://localhost:8080
```

### Using Python locally (for testing)

```bash
# Python 3
python3 -m http.server 8080

# Visit http://localhost:8080
```

---

## 🔧 Post-Deployment Checklist

After deploying, make sure to:

1. ✅ **Update Encharge Webhook URL**
   - Edit `index.html` line 412
   - Replace `https://YOUR_ENCHARGE_WEBHOOK_URL_HERE` with your actual webhook

2. ✅ **Add Google Tag Manager**
   - Add GTM code to both `index.html` and `thank-you.html`
   - Look for `<!-- GTM HEAD SNIPPET PLACEHOLDER -->` comments

3. ✅ **Test the Form**
   - Fill out the form with test data
   - Verify webhook receives the data
   - Verify redirect to thank-you page works
   - Verify personalization shows your name

4. ✅ **Update CTA Button**
   - Edit `thank-you.html` line 144
   - Replace `href="#"` with actual link

5. ✅ **Set Up Custom Domain** (Optional)
   - Most hosting providers allow custom domains
   - Configure DNS records to point to your deployment
   - Example: `newsletter.yourcompany.com`

6. ✅ **Enable HTTPS**
   - All recommended platforms provide free SSL certificates
   - Ensure your site uses HTTPS for security

---

## 📊 Recommended: Netlify

**Why Netlify?**
- ✅ Free tier is generous
- ✅ Automatic HTTPS
- ✅ Continuous deployment from Git
- ✅ Form handling built-in (can replace Encharge if needed)
- ✅ Easy custom domain setup
- ✅ Instant cache invalidation

---

## 🆘 Need Help?

If you run into issues:
1. Check the deployment logs in your hosting platform
2. Verify all files are committed to Git
3. Test locally first using a simple HTTP server
4. Ensure webhook URL is correctly configured

---

**Your newsletter funnel is ready to go live! Choose a deployment option and start capturing leads. 🎉**
