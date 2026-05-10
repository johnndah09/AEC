# GitHub Deployment Guide

Complete guide for deploying AMBASSADORS SMS to GitHub and GitHub Pages.

---

## 📋 Table of Contents

1. [Prerequisites](#prerequisites)
2. [GitHub Setup](#github-setup)
3. [Repository Configuration](#repository-configuration)
4. [GitHub Pages Deployment](#github-pages-deployment)
5. [Domain Configuration](#domain-configuration)
6. [Post-Deployment](#post-deployment)
7. [Troubleshooting](#troubleshooting)
8. [Maintenance](#maintenance)

---

## ✅ Prerequisites

### Software Requirements
- **Git** installed on your machine
  - Download: https://git-scm.com/downloads
  - Verify: `git --version`

- **GitHub Account** (free or paid)
  - Sign up: https://github.com/signup
  - Verify email address

- **Text Editor or IDE**
  - VS Code (recommended): https://code.visualstudio.com
  - Sublime Text, Atom, or any text editor

- **Terminal/Command Prompt**
  - Windows: Command Prompt or PowerShell
  - macOS/Linux: Terminal

### Knowledge Requirements
- Basic Git commands
- GitHub interface navigation
- Command line basics

---

## 🚀 GitHub Setup

### Step 1: Create a GitHub Account

1. Visit [github.com](https://github.com)
2. Click "Sign up"
3. Enter email address
4. Create password
5. Choose username (this will be in your URL)
6. Verify email address

**Important:** Your GitHub username will be part of your project URL:
```
https://github.com/yourusername/ambassadors-sms
https://yourusername.github.io/ambassadors-sms
```

### Step 2: Configure Git Locally

Open terminal and run:

```bash
# Set your name
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@gmail.com"

# Verify configuration
git config --list
```

### Step 3: Generate SSH Key (Optional but Recommended)

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@gmail.com"

# Copy the key to clipboard
# macOS
cat ~/.ssh/id_ed25519.pub | pbcopy

# Linux
cat ~/.ssh/id_ed25519.pub | xclip -selection clipboard

# Windows (PowerShell)
Get-Content ~/.ssh/id_ed25519.pub | Set-Clipboard
```

Add SSH key to GitHub:
1. Go to Settings → SSH and GPG keys
2. Click "New SSH key"
3. Paste your key
4. Click "Add SSH key"

---

## 📁 Repository Configuration

### Step 1: Create a New Repository

1. Log into GitHub
2. Click "New" or go to [github.com/new](https://github.com/new)
3. **Repository name:** `ambassadors-sms`
4. **Description:** "Professional School Management System for Cameroon secondary schools"
5. **Visibility:** Public (recommended for open source)
6. **Initialize repository:** 
   - ☐ Don't check "Add a README file" (we'll add our own)
   - ☐ Don't add .gitignore yet
7. Click "Create repository"

### Step 2: Prepare Your Files Locally

Create a folder structure:

```
ambassadors-sms/
├── index.html                      (GitHub Pages homepage)
├── school_management_system.html   (Main application)
├── README.md                       (Documentation)
├── CONTRIBUTING.md                 (Contributing guidelines)
├── CHANGELOG.md                    (Version history)
├── LICENSE                         (MIT License)
└── .gitignore                      (Git ignore rules)
```

### Step 3: Initialize Local Repository

```bash
# Create folder
mkdir ambassadors-sms
cd ambassadors-sms

# Initialize git
git init

# Add all files
git add .

# Initial commit
git commit -m "Initial commit: Add school management system"

# Add remote (replace 'yourusername' with your GitHub username)
git remote add origin https://github.com/yourusername/ambassadors-sms.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

---

## 🌐 GitHub Pages Deployment

### Step 1: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (gear icon)
3. Scroll to **"Pages"** section (left sidebar)
4. **Source:** Select `main` branch
5. **Folder:** Select `/ (root)`
6. Click **Save**

### Step 2: Configure GitHub Pages Settings

1. Still in **Pages** section:
   - **Enforce HTTPS:** Check this box ✓
   - **Custom domain:** Leave blank (unless using custom domain)
2. Click **Save**

### Step 3: Verify Deployment

1. GitHub will show your site URL:
   ```
   https://yourusername.github.io/ambassadors-sms/
   ```

2. Wait 1-5 minutes for the site to go live
3. Visit the URL to verify it's working

4. You should see the `index.html` homepage

---

## 🔗 Domain Configuration

### Using Custom Domain (Optional)

If you want to use a custom domain like `ambassadorssms.cm`:

#### Step 1: Purchase Domain
- Domain registrar: GoDaddy, Namecheap, etc.
- Cost: Usually $5-15 per year

#### Step 2: Configure DNS Records

In your domain registrar's settings, add these DNS records:

**Type: A Records**
```
@        A        185.199.108.153
@        A        185.199.109.153
@        A        185.199.110.153
@        A        185.199.111.153
```

**Type: CNAME Record (if using www subdomain)**
```
www      CNAME    yourusername.github.io
```

#### Step 3: Add Domain to GitHub Pages

1. Repository → Settings → Pages
2. **Custom domain:** Enter your domain name
3. Click **Save**
4. GitHub will check the DNS configuration

#### Step 4: Enable HTTPS

1. Back to Settings → Pages
2. Wait for SSL certificate to be issued (5-30 mins)
3. Check **Enforce HTTPS**

**Note:** Custom domain setup may take 24 hours to fully propagate

---

## ✨ Post-Deployment

### Step 1: Verify All Files Are Accessible

Check these URLs:
```
https://yourusername.github.io/ambassadors-sms/
https://yourusername.github.io/ambassadors-sms/school_management_system.html
https://yourusername.github.io/ambassadors-sms/README.md
```

### Step 2: Test the Application

1. Open the main application URL
2. Test all features:
   - Navigation works
   - Forms open
   - Data entry works
   - All modules accessible

3. Test on different browsers:
   - Chrome
   - Firefox
   - Safari
   - Edge

4. Test on mobile:
   - iPhone/iPad
   - Android device

### Step 3: Create GitHub Release

1. Go to **Releases** on your repository
2. Click **Create a new release**
3. **Tag version:** v1.0.0
4. **Release title:** School Management System v1.0.0
5. **Description:** Add release notes
6. **Attach files:** Upload HTML file if desired
7. Click **Publish release**

### Step 4: Add Repository Topics

1. Go to repository main page
2. Click **⚙️ About** (right side)
3. Add topics:
   - `school-management`
   - `student-enrollment`
   - `attendance-tracking`
   - `cameroon`
   - `education`
   - `open-source`
4. Click **Save changes**

### Step 5: Enable Discussions (Optional)

1. Settings → Features
2. Check **Discussions**
3. Save

---

## 🐛 Troubleshooting

### Issue: Pages not showing up

**Solution 1:** Check Pages is enabled
```
Settings → Pages → Check main branch is selected
```

**Solution 2:** Wait for deployment
- GitHub Pages takes 1-5 minutes
- Check the "Deployments" tab

**Solution 3:** Check file names
- Ensure `index.html` is in the root folder
- Case-sensitive on Linux servers

### Issue: CSS/JavaScript not loading

**Possible cause:** Wrong file paths

**Solution:**
```html
<!-- Instead of: -->
<link rel="stylesheet" href="/style.css">

<!-- Use: -->
<link rel="stylesheet" href="style.css">

<!-- Or for subfolders: -->
<link rel="stylesheet" href="./css/style.css">
```

### Issue: 404 errors on subpaths

**Cause:** Single Page Application routing issue

**Solution 1:** Use hash-based routing
```
https://yourusername.github.io/ambassadors-sms/#/attendance
```

**Solution 2:** Create 404.html redirect
```html
<!-- Create 404.html in root -->
<script>
  // Redirect to index.html with path info
  window.location.replace('/ambassadors-sms/?' + window.location.pathname.split('/').slice(2).join('/'));
</script>
```

### Issue: Cannot push to GitHub

**Solution 1:** Check SSH keys
```bash
ssh -T git@github.com
```

**Solution 2:** Use HTTPS instead
```bash
git remote set-url origin https://github.com/yourusername/ambassadors-sms.git
```

**Solution 3:** Authenticate with token
- Generate: Settings → Developer settings → Personal access tokens
- Use as password when prompted

### Issue: Large files being rejected

**Solution 1:** Use .gitignore
```
# Add to .gitignore
*.zip
*.psd
node_modules/
```

**Solution 2:** Use Git LFS for large files
```bash
git lfs install
git lfs track "*.zip"
git add .gitattributes
git commit -m "Add Git LFS tracking"
```

---

## 🔄 Maintenance

### Regular Updates

When making changes:

```bash
# Make changes to files

# Stage changes
git add .

# Commit with message
git commit -m "feat: Add new feature or fix: Fix issue"

# Push to GitHub
git push origin main
```

### Branch Management

Create a development branch:

```bash
# Create branch
git checkout -b develop

# Make changes and commit
git commit -m "Development work"

# Push branch
git push origin develop

# Create Pull Request on GitHub for review
```

### Backup Your Repository

```bash
# Clone to backup location
git clone --mirror https://github.com/yourusername/ambassadors-sms.git
```

### Monitor GitHub Actions

1. Go to **Actions** tab
2. View deployment status
3. Check build logs if issues occur

### Keep Dependencies Updated

Though this project has no external dependencies, if you add any in future versions:

```bash
# Check for updates
npm outdated

# Update packages
npm update

# Commit changes
git commit -m "chore: Update dependencies"
git push origin main
```

---

## 📊 GitHub Pages Analytics

### View Traffic

1. Repository → Insights → Traffic
2. See page views and referrers
3. Monitor usage

### Set up Google Analytics (Optional)

Add to your HTML:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>
```

---

## 🔐 Security

### Protect Main Branch

1. Settings → Branches
2. Add rule for `main` branch
3. **Require pull request reviews:** Check
4. **Dismiss stale pull request approvals:** Check
5. **Require HTTPS:** Check

### Secret Management

For future database integration:
```bash
# Add secrets at Settings → Secrets → New repository secret
# Use in GitHub Actions:
# ${{ secrets.SECRET_NAME }}
```

### Regular Security Updates

1. Settings → Security & analysis
2. Enable:
   - Dependency alerts ✓
   - Dependabot alerts ✓
   - Secret scanning ✓

---

## 📈 Post-Launch Checklist

- ✅ Repository created
- ✅ Files committed and pushed
- ✅ GitHub Pages enabled
- ✅ Site is live and accessible
- ✅ All features tested
- ✅ Documentation complete
- ✅ License file added
- ✅ Topics added
- ✅ Initial release created
- ✅ Social media updated
- ✅ Email list notified
- ✅ School website updated

---

## 🚀 Scaling for Production

When ready to handle more users:

1. **Add Backend Server**
   - Use Firebase, MongoDB, or traditional database
   - Create API endpoints

2. **Setup CI/CD Pipeline**
   - GitHub Actions for automated testing
   - Automatic deployments on push

3. **Performance Optimization**
   - Compress images
   - Minify CSS/JavaScript
   - Implement caching

4. **Enhanced Security**
   - User authentication
   - Data encryption
   - Regular backups

---

## 📞 Support Resources

- **GitHub Help:** https://docs.github.com
- **Pages Documentation:** https://pages.github.com
- **GitHub Community:** https://github.community
- **Stack Overflow:** Tag: `github-pages`

---

## ✅ Final Verification

Visit your live site and verify:

1. **Homepage loads** → https://yourusername.github.io/ambassadors-sms/
2. **App launches** → Click "Launch Application"
3. **All modules work** → Test each section
4. **Mobile responsive** → View on phone
5. **Navigation works** → All links functional
6. **Forms submit** → Data entry successful
7. **Reports generate** → PDF downloads work

---

**Congratulations!** 🎉 Your AMBASSADORS SMS is now live on the internet!

Share your achievement:
- Tweet: "Just launched AMBASSADORS School Management System on GitHub! #edtech #cameroon #opensource"
- Email: Your stakeholders
- School website: Link to the system
- Social media: Post about it

---

**Last Updated:** January 2024
**Maintained By:** Ambassadors Educational Complex
