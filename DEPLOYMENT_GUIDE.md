# Claude Code Deployment Guide
## Step-by-Step Instructions for Uploading to GitHub

This guide will help you use Claude Code CLI to upload this website to GitHub and deploy it.

## Prerequisites

1. **Claude Code CLI installed**
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

2. **Git installed**
   ```bash
   git --version
   ```

3. **GitHub account** with authentication set up

## Step 1: Navigate to Website Directory

```bash
cd pnw-rigging-website-complete
```

## Step 2: Initialize Git Repository

```bash
# Initialize git
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: PNW Rigging Solutions website

- Homepage with SEO optimization
- Service pages: Heavy Equipment Moving, Crane Services
- Location page: Seattle
- Complete documentation and templates
- Ready for deployment"
```

## Step 3: Create GitHub Repository

### Option A: Using GitHub CLI (gh)

```bash
# Install gh if needed
# macOS: brew install gh
# Windows: winget install GitHub.cli

# Login to GitHub
gh auth login

# Create repository and push
gh repo create pnw-rigging-website --public --source=. --push

# Enable GitHub Pages
gh api repos/YOUR-USERNAME/pnw-rigging-website/pages \
  -X POST \
  -F source='{"branch":"main","path":"/"}'
```

### Option B: Manual GitHub Creation

1. Go to https://github.com/new
2. Repository name: `pnw-rigging-website`
3. Description: "Professional industrial rigging services website for Washington State"
4. Public repository
5. Don't initialize with README (we already have one)
6. Click "Create repository"

Then connect your local repo:

```bash
git remote add origin https://github.com/YOUR-USERNAME/pnw-rigging-website.git
git branch -M main
git push -u origin main
```

## Step 4: Enable GitHub Pages

### Via GitHub Web Interface:
1. Go to your repository on GitHub
2. Click **Settings** tab
3. Scroll to **Pages** section (left sidebar)
4. Under "Source":
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**
6. Wait 2-3 minutes for deployment
7. Your site will be live at: `https://YOUR-USERNAME.github.io/pnw-rigging-website/`

### Via GitHub CLI:
```bash
gh api repos/YOUR-USERNAME/pnw-rigging-website/pages \
  -X POST \
  -F source='{"branch":"main","path":"/"}'
```

## Step 5: Configure Custom Domain (Optional)

If you own a domain (e.g., pnwrigging.com):

1. **In your domain registrar (GoDaddy, Namecheap, etc.):**
   
   Add these DNS records:
   ```
   Type    Name    Value
   A       @       185.199.108.153
   A       @       185.199.109.153
   A       @       185.199.110.153
   A       @       185.199.111.153
   CNAME   www     YOUR-USERNAME.github.io
   ```

2. **In GitHub repository settings:**
   - Go to Settings → Pages
   - Custom domain: Enter `www.pnwrigging.com`
   - Save
   - Check "Enforce HTTPS" (after DNS propagates)

3. **Update CNAME file:**
   The CNAME file is already created with `www.pnwrigging.com`
   - If using different domain, edit the CNAME file
   - Commit and push changes

## Step 6: Verify Deployment

1. **Check GitHub Actions:**
   - Go to your repo → Actions tab
   - Verify "pages build and deployment" succeeded

2. **Visit your site:**
   - GitHub Pages URL: `https://YOUR-USERNAME.github.io/pnw-rigging-website/`
   - Custom domain (after DNS): `https://www.pnwrigging.com/`

3. **Test all pages:**
   - Homepage loads correctly
   - Service pages accessible
   - Location pages accessible
   - All links work
   - Mobile responsive

## Step 7: Post-Deployment Setup

### A. Update Contact Information
Search and replace in all files:
```bash
# Phone numbers
find . -type f -name "*.html" -exec sed -i '' 's/(509) 555-0100/YOUR-REAL-PHONE/g' {} +

# Email addresses  
find . -type f -name "*.html" -exec sed -i '' 's/info@pnwrigging.com/YOUR-REAL-EMAIL/g' {} +

# Address
find . -type f -name "*.html" -exec sed -i '' 's/123 Industrial Way/YOUR-REAL-ADDRESS/g' {} +
```

### B. Set Up Google Search Console
1. Go to https://search.google.com/search-console
2. Add property: Your domain
3. Verify ownership (add meta tag to index.html OR upload HTML file)
4. Submit sitemap: `https://www.pnwrigging.com/sitemap.xml`

### C. Set Up Google Analytics
1. Create GA4 property at https://analytics.google.com
2. Get tracking code
3. Add to all HTML files before `</head>`
4. Commit and push changes

### D. Submit Sitemap to Bing
1. Go to https://www.bing.com/webmasters
2. Add your site
3. Submit sitemap

## Step 8: Ongoing Deployment

After initial setup, deploying updates is simple:

```bash
# Make changes to your files
# ...

# Stage changes
git add .

# Commit with descriptive message
git commit -m "Add new location page for Tacoma"

# Push to GitHub
git push origin main

# GitHub Pages will automatically rebuild and deploy (2-3 minutes)
```

## Alternative: Deploy to Netlify (Recommended for Production)

Netlify offers better performance and features than GitHub Pages:

1. **Connect GitHub Repository:**
   - Go to https://netlify.com
   - Sign up / Sign in with GitHub
   - Click "New site from Git"
   - Choose your repository
   - Deploy settings:
     - Branch: `main`
     - Build command: (leave empty)
     - Publish directory: `/`
   - Click "Deploy site"

2. **Configure Custom Domain:**
   - Site settings → Domain management
   - Add custom domain
   - Follow DNS configuration instructions
   - Netlify auto-provisions SSL certificate

3. **Benefits over GitHub Pages:**
   - Faster global CDN
   - Form handling built-in
   - Instant cache invalidation
   - Better analytics
   - More deployment options

## Troubleshooting

### Issue: Site not loading
- Check GitHub Actions for build errors
- Verify GitHub Pages is enabled in settings
- Wait 5-10 minutes after first deployment
- Clear browser cache

### Issue: 404 errors on pages
- Verify file paths are correct (case-sensitive)
- Check that all HTML files are committed
- Ensure proper directory structure

### Issue: Styles not loading
- Styles are inline, so this shouldn't happen
- If you extracted CSS, verify paths
- Check browser console for errors

### Issue: Custom domain not working
- DNS propagation takes 24-48 hours
- Verify DNS records are correct
- Check CNAME file has correct domain
- Ensure "Enforce HTTPS" is checked (after DNS propagates)

## Claude Code Specific Commands

If using Claude Code CLI for automation:

```bash
# Upload all files to GitHub
claude-code github:push --repo pnw-rigging-website --branch main

# Create new service page
claude-code generate:page --template service --name "structural-steel-rigging"

# Batch create location pages
claude-code generate:batch --template location --cities "Tacoma,Spokane,Bellevue"

# Run SEO audit
claude-code seo:audit --url https://www.pnwrigging.com

# Update all contact information
claude-code replace:contact --phone "555-123-4567" --email "info@realcompany.com"
```

## Success Checklist

- [ ] Repository created on GitHub
- [ ] All files pushed successfully
- [ ] GitHub Pages enabled and site live
- [ ] Homepage loads correctly
- [ ] All service pages accessible
- [ ] All location pages accessible
- [ ] Mobile responsive verified
- [ ] Contact information updated
- [ ] Google Search Console configured
- [ ] Google Analytics installed
- [ ] Sitemap submitted
- [ ] Custom domain configured (if applicable)
- [ ] SSL/HTTPS working

## Next Steps After Deployment

1. **Complete remaining pages** (see PAGE_GENERATION_GUIDE.md)
2. **Add real images** to assets/images/
3. **Set up form backend** (Netlify Forms, FormSpree, etc.)
4. **Begin SEO campaign** (see SEO_IMPLEMENTATION_ROADMAP.md)
5. **Start citation building** (see COMPETITOR_ANALYSIS.md)
6. **Generate reviews** on Google Business Profile
7. **Create social media profiles**
8. **Begin content marketing** (blog posts)

---

Your website is now live and ready to dominate Washington State rigging search results! 🚀
