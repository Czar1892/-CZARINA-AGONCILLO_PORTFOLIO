# 🚀 Deployment Guide

## Quick Start - GitHub Pages Deployment

### Step 1: Create a New Repository on GitHub

1. Go to [GitHub](https://github.com) and sign in
2. Click the **+** icon in the top right corner
3. Select **New repository**
4. Repository settings:
   - **Name**: `portfolio` (or any name you prefer)
   - **Description**: "My professional portfolio website"
   - **Visibility**: Public
   - **Initialize**: Do NOT check "Add a README file" (we already have one)
5. Click **Create repository**

### Step 2: Upload Your Files

#### Option A: Using GitHub Web Interface (Easiest)

1. On your new repository page, click **uploading an existing file**
2. Drag and drop ALL these files:
   - `index.html`
   - `profile.jpg`
   - `README.md`
   - `LICENSE`
   - `.gitignore`
   - `CNAME` (optional - only if you have a custom domain)
3. Add a commit message: "Initial commit - Portfolio website"
4. Click **Commit changes**

#### Option B: Using Git Command Line

```bash
# Navigate to your folder with the files
cd /path/to/your/portfolio/files

# Initialize git repository
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit - Portfolio website"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR-USERNAME/portfolio.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Scroll down and click **Pages** (left sidebar)
4. Under "Source":
   - Select **main** branch
   - Select **/ (root)** folder
5. Click **Save**
6. Wait 1-2 minutes for deployment
7. Your site will be live at: `https://YOUR-USERNAME.github.io/portfolio/`

### Step 4: Custom Domain (Optional)

If you want to use your own domain (e.g., czarinaagoncillo.com):

1. **Update CNAME file**: Edit the `CNAME` file with your domain name
2. **Configure DNS**: In your domain registrar (GoDaddy, Namecheap, etc.):
   - Add A records pointing to GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Or add a CNAME record: `www` → `YOUR-USERNAME.github.io`
3. **Wait for DNS**: Can take 24-48 hours to propagate

---

## Alternative Deployment Options

### Netlify (Great for custom domains and forms)

1. Go to [Netlify](https://netlify.com)
2. Sign up/Login with GitHub
3. Click **Add new site** → **Import an existing project**
4. Connect to your GitHub repository
5. Deploy settings:
   - Build command: (leave empty)
   - Publish directory: (leave empty or `/`)
6. Click **Deploy site**
7. Your site is live! You'll get a random URL like `random-name-123.netlify.app`
8. You can change this in Site settings → Domain management

### Vercel

1. Go to [Vercel](https://vercel.com)
2. Sign up/Login with GitHub
3. Click **Add New Project**
4. Import your GitHub repository
5. Click **Deploy**
6. Done! Your site is live

### Traditional Web Hosting

For cPanel or traditional hosting:

1. Login to your hosting control panel
2. Go to File Manager
3. Navigate to `public_html` folder
4. Upload `index.html`
5. Your site is live at your domain!

---

## Testing Locally

Before deploying, test your site locally:

### Option 1: Simple Open
- Just double-click `index.html` to open in browser

### Option 2: Local Server (Recommended)
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (if you have npx)
npx serve

# Then visit: http://localhost:8000
```

---

## Updating Your Site

### Via GitHub Web:
1. Go to your repository
2. Click on the file you want to edit
3. Click the pencil icon (Edit)
4. Make changes
5. Commit changes

### Via Git Command Line:
```bash
# Make your changes to files

# Stage changes
git add .

# Commit with message
git commit -m "Updated portfolio content"

# Push to GitHub
git push origin main

# Changes will automatically deploy to GitHub Pages
```

---

## Troubleshooting

### Site not loading after deployment
- Wait 2-3 minutes for GitHub Pages to build
- Check that `index.html` is in the root directory
- Verify GitHub Pages is enabled in Settings

### 404 Error
- Make sure file is named `index.html` (lowercase)
- Check GitHub Pages source is set to main branch

### Custom domain not working
- Verify CNAME file contains only your domain (no http://)
- Check DNS settings in your domain registrar
- Wait 24-48 hours for DNS propagation

### Images or fonts not loading
- This portfolio uses Google Fonts CDN (should work automatically)
- If you add images, make sure paths are correct

---

## Need Help?

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Netlify Documentation](https://docs.netlify.com)
- [Git Basics Tutorial](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

---

**Happy Deploying! 🎉**
