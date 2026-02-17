# GitHub Setup & Connection Guide

**Project:** Alpha Rigging Website
**Repository:** https://github.com/SyncShepherd-Main/alpha-rigging-website
**Live Site:** https://syncshepherd-main.github.io/alpha-rigging-website/

---

## Table of Contents

1. [Repository Information](#repository-information)
2. [First Time Setup](#first-time-setup)
3. [Daily Workflow](#daily-workflow)
4. [Making Changes](#making-changes)
5. [Common Git Commands](#common-git-commands)
6. [GitHub Pages Deployment](#github-pages-deployment)
7. [Troubleshooting](#troubleshooting)

---

## Repository Information

### Repository Details
- **Owner:** SyncShepherd-Main
- **Repository Name:** alpha-rigging-website
- **Branch:** master
- **Visibility:** Public
- **Hosting:** GitHub Pages (automatic deployment)

### URLs
- **Repository:** https://github.com/SyncShepherd-Main/alpha-rigging-website
- **Live Site:** https://syncshepherd-main.github.io/alpha-rigging-website/
- **Clone URL (HTTPS):** https://github.com/SyncShepherd-Main/alpha-rigging-website.git
- **Clone URL (SSH):** git@github.com:SyncShepherd-Main/alpha-rigging-website.git

---

## First Time Setup

### Option 1: Already Have the Files (Current Setup)

**You're already set up!** The local folder is already connected to GitHub.

**Verify Connection:**
```bash
cd "G:/Websites/Alpha Rigging/pnw-rigging-website-complete"
git remote -v
```

**Expected Output:**
```
origin  https://github.com/SyncShepherd-Main/alpha-rigging-website.git (fetch)
origin  https://github.com/SyncShepherd-Main/alpha-rigging-website.git (push)
```

---

### Option 2: Clone Repository (Fresh Start)

**If you need to clone the repository to a new location or different computer:**

```bash
# Navigate to where you want the project
cd "G:/Websites/Alpha Rigging/"

# Clone the repository
git clone https://github.com/SyncShepherd-Main/alpha-rigging-website.git

# Navigate into the project
cd alpha-rigging-website
```

---

### Option 3: Download as ZIP

1. Go to: https://github.com/SyncShepherd-Main/alpha-rigging-website
2. Click green "Code" button
3. Select "Download ZIP"
4. Extract to your desired location
5. Initialize git in that folder:
   ```bash
   cd "path/to/extracted/folder"
   git init
   git remote add origin https://github.com/SyncShepherd-Main/alpha-rigging-website.git
   git fetch
   git checkout master
   ```

---

## Daily Workflow

### Quick Start (Using Quick Connect)

**Fastest way to start working:**
```bash
alpharigging
# or
alpharig
```

This automatically:
- Navigates to project directory
- Launches Claude Code
- Ready to work!

---

### Standard Workflow

**1. Navigate to Project**
```bash
cd "G:/Websites/Alpha Rigging/pnw-rigging-website-complete"
```

**2. Check Current Status**
```bash
git status
```

**3. Pull Latest Changes** (if working with others)
```bash
git pull origin master
```

**4. Make Your Changes**
- Edit HTML files
- Update CSS
- Add images
- Modify content

**5. Check What Changed**
```bash
git status
git diff
```

**6. Stage Changes**
```bash
# Stage all changes
git add .

# Or stage specific files
git add index.html
git add services/crane-services.html
```

**7. Commit Changes**
```bash
git commit -m "Your descriptive commit message here"
```

**8. Push to GitHub**
```bash
git push origin master
```

**9. Wait for Deployment** (1-2 minutes)
- GitHub Pages automatically rebuilds
- Check live site: https://syncshepherd-main.github.io/alpha-rigging-website/

---

## Making Changes

### Example: Update Phone Number

**1. Navigate to project:**
```bash
cd "G:/Websites/Alpha Rigging/pnw-rigging-website-complete"
```

**2. Edit the file(s):**
```bash
# Use any text editor
code index.html
# or
notepad index.html
```

**3. Make the changes:**
- Find: `(509) 555-0100`
- Replace with: `(360) 748-XXXX` (real number)

**4. Save the file**

**5. Check what changed:**
```bash
git diff index.html
```

**6. Stage, commit, and push:**
```bash
git add index.html
git commit -m "Update phone number to real business line"
git push origin master
```

**7. Verify live in 1-2 minutes**

---

### Example: Add New Image

**1. Add image file to assets folder:**
```bash
cp /path/to/photo.jpg "G:/Websites/Alpha Rigging/pnw-rigging-website-complete/assets/images/photo.jpg"
```

**2. Update HTML to reference it:**
```html
<img src="assets/images/photo.jpg" alt="Description">
```

**3. Stage both the image and HTML:**
```bash
git add assets/images/photo.jpg
git add index.html
git commit -m "Add company logo to homepage"
git push origin master
```

---

### Example: Update Multiple Pages

**If you need to update phone numbers across all pages:**

**1. Use find and replace (sed):**
```bash
# Update all HTML files
sed -i 's/509) 555-0100/360) 748-XXXX/g' *.html services/*.html locations/*.html about.html
```

**2. Review changes:**
```bash
git status
git diff
```

**3. Stage all changes:**
```bash
git add .
```

**4. Commit and push:**
```bash
git commit -m "Update all phone numbers to real business line"
git push origin master
```

---

## Common Git Commands

### Checking Status

```bash
# See what files have changed
git status

# See detailed changes in files
git diff

# See commit history
git log

# See recent commits (last 5)
git log -5 --oneline
```

---

### Staging & Committing

```bash
# Stage all changes
git add .

# Stage specific file
git add index.html

# Stage multiple specific files
git add index.html about.html

# Stage all files in a directory
git add services/

# Unstage a file (if you added by mistake)
git reset HEAD index.html

# Commit with message
git commit -m "Your message here"

# Commit with detailed message
git commit -m "Short summary" -m "Longer detailed description of changes"
```

---

### Pushing & Pulling

```bash
# Push to GitHub
git push origin master

# Pull latest from GitHub
git pull origin master

# Force push (DANGEROUS - use with caution)
git push --force origin master
```

---

### Viewing Changes

```bash
# See changes in working directory
git diff

# See changes that are staged
git diff --staged

# See changes in specific file
git diff index.html

# See who changed what and when
git blame index.html
```

---

### Undoing Changes

```bash
# Discard changes in working directory (NOT staged yet)
git checkout -- index.html

# Unstage file (remove from staging, keep changes)
git reset HEAD index.html

# Undo last commit (keep changes in working directory)
git reset --soft HEAD~1

# Undo last commit (discard all changes - DANGEROUS)
git reset --hard HEAD~1

# Revert a specific commit (creates new commit)
git revert abc123
```

---

### Branches (Advanced)

```bash
# List all branches
git branch

# Create new branch
git branch feature-blog

# Switch to branch
git checkout feature-blog

# Create and switch in one command
git checkout -b feature-blog

# Merge branch into master
git checkout master
git merge feature-blog

# Delete branch
git branch -d feature-blog
```

---

## GitHub Pages Deployment

### How It Works

1. **You make changes** locally on your computer
2. **You commit** those changes to git
3. **You push** to GitHub (master branch)
4. **GitHub Pages automatically rebuilds** the site (1-2 minutes)
5. **Site is live** at: https://syncshepherd-main.github.io/alpha-rigging-website/

**No additional deployment steps needed!** It's automatic.

---

### Checking Deployment Status

**1. Go to GitHub Repository:**
https://github.com/SyncShepherd-Main/alpha-rigging-website

**2. Click "Actions" tab**
- See deployment status
- Green checkmark = deployed successfully
- Yellow circle = currently deploying
- Red X = deployment failed

**3. Click on the deployment to see details**

---

### Deployment Settings

**Current Configuration:**
- **Source:** master branch
- **Folder:** / (root)
- **Custom Domain:** None (using github.io subdomain)
- **HTTPS:** Enforced

**To View/Change Settings:**
1. Go to repository on GitHub
2. Click "Settings"
3. Click "Pages" in left sidebar
4. View/modify deployment settings

---

## Troubleshooting

### Problem: "Permission denied" when pushing

**Cause:** Authentication issue

**Solution:**
```bash
# If using HTTPS, you may need to re-authenticate
git remote set-url origin https://github.com/SyncShepherd-Main/alpha-rigging-website.git

# Or use SSH (requires SSH key setup)
git remote set-url origin git@github.com:SyncShepherd-Main/alpha-rigging-website.git
```

---

### Problem: "Your branch is behind 'origin/master'"

**Cause:** Someone else pushed changes, or you pushed from different computer

**Solution:**
```bash
# Pull the latest changes
git pull origin master

# If you have local changes, they'll try to merge
# If merge conflicts, git will tell you which files
```

---

### Problem: Merge Conflicts

**Cause:** Same file edited in different places

**Solution:**
```bash
# Git will mark conflicts in files like this:
# <<<<<<< HEAD
# Your changes
# =======
# Their changes
# >>>>>>> master

# 1. Open the conflicted file
# 2. Choose which version to keep (or combine them)
# 3. Remove the conflict markers (<<<, ===, >>>)
# 4. Save the file
# 5. Stage and commit:
git add index.html
git commit -m "Resolve merge conflict in index.html"
git push origin master
```

---

### Problem: Changes not showing on live site

**Possible Causes & Solutions:**

**1. Deployment not finished yet**
- Wait 2-3 minutes
- Check Actions tab on GitHub
- Refresh browser with Ctrl+F5 (hard refresh)

**2. Browser cache**
```bash
# Clear browser cache
# Or hard refresh: Ctrl + Shift + R (Chrome)
# Or: Ctrl + F5
```

**3. Deployment failed**
- Check GitHub Actions for errors
- Common cause: syntax error in HTML
- Validate HTML: https://validator.w3.org/

**4. Changes not pushed**
```bash
# Verify changes are on GitHub
git status
# Should say "nothing to commit, working tree clean"

# If not:
git add .
git commit -m "Push missing changes"
git push origin master
```

---

### Problem: Accidentally deleted important file

**Solution:**
```bash
# If not committed yet:
git checkout -- filename.html

# If committed and pushed:
git log --all --full-history -- filename.html
# Find the commit hash before deletion
git checkout abc123 -- filename.html
git add filename.html
git commit -m "Restore accidentally deleted file"
git push origin master
```

---

### Problem: Want to undo last push

**Solution (if no one else has pulled):**
```bash
# Undo last commit, keep changes
git reset --soft HEAD~1

# Make corrections
git add .
git commit -m "Corrected commit message"

# Force push (use with caution)
git push --force origin master
```

**Solution (if others may have pulled):**
```bash
# Create a new commit that undoes the last one
git revert HEAD
git push origin master
```

---

## Best Practices

### Commit Messages

**Good commit messages:**
```bash
git commit -m "Update phone number to real business line"
git commit -m "Add Trevor's bio photo to About page"
git commit -m "Fix navigation dropdown on mobile devices"
git commit -m "Update all service pages with new pricing"
```

**Bad commit messages:**
```bash
git commit -m "updates"
git commit -m "fix"
git commit -m "changes"
git commit -m "asdf"
```

**Format:**
- Start with capital letter
- Use imperative mood ("Add" not "Added")
- Be specific about what changed
- Keep under 72 characters for summary

---

### When to Commit

**Commit when you:**
- ✅ Finish a logical unit of work
- ✅ Complete a single feature or fix
- ✅ Want to save a working version
- ✅ Before trying something risky

**Don't commit when:**
- ❌ Code is broken
- ❌ In the middle of a change
- ❌ Temporary/test files included

---

### What to Commit

**Always commit:**
- ✅ HTML files
- ✅ CSS files
- ✅ JavaScript files
- ✅ Documentation
- ✅ Configuration files

**Never commit:**
- ❌ Passwords or API keys
- ❌ Large binary files (unless images for site)
- ❌ Temporary files
- ❌ System files (.DS_Store, Thumbs.db)

---

## GitHub Repository Management

### Viewing Repository on GitHub

**1. Go to:** https://github.com/SyncShepherd-Main/alpha-rigging-website

**2. Tabs Available:**
- **Code:** Browse files, view code
- **Issues:** Track bugs, feature requests
- **Pull Requests:** Review code changes (if using branches)
- **Actions:** See deployment history
- **Settings:** Configure repository

---

### Adding Collaborators

**If you want to give someone else access:**

1. Go to repository on GitHub
2. Click "Settings"
3. Click "Collaborators" in left sidebar
4. Click "Add people"
5. Enter their GitHub username or email
6. They'll receive an invitation

---

### Protecting the Master Branch

**To prevent accidental force pushes:**

1. Go to Settings > Branches
2. Click "Add rule"
3. Branch name pattern: `master`
4. Check "Require pull request reviews"
5. Save changes

---

## Quick Reference Card

### Most Common Commands

```bash
# Start working
cd "G:/Websites/Alpha Rigging/pnw-rigging-website-complete"

# Check status
git status

# Stage all changes
git add .

# Commit
git commit -m "Description of changes"

# Push to GitHub
git push origin master

# Pull latest changes
git pull origin master

# See what changed
git diff

# View commit history
git log --oneline
```

---

## Getting Help

### Git Help Commands

```bash
# General git help
git --help

# Help for specific command
git commit --help
git push --help
```

### Useful Resources

- **Git Documentation:** https://git-scm.com/doc
- **GitHub Guides:** https://guides.github.com/
- **Git Cheat Sheet:** https://education.github.com/git-cheat-sheet-education.pdf

---

## Contact & Support

### For Repository Issues:
- Check this guide first
- Review git error messages carefully
- Check GitHub Actions tab for deployment errors

### For Website Content Issues:
- Refer to PROJECT_DEVELOPMENT_LOG.md
- Check existing page structure
- Validate HTML before committing

---

## Summary

**Your setup is complete and working!**

✅ Repository connected: https://github.com/SyncShepherd-Main/alpha-rigging-website
✅ Live site deployed: https://syncshepherd-main.github.io/alpha-rigging-website/
✅ Quick connect alias: `alpharigging` or `alpharig`
✅ Automatic deployment via GitHub Pages

**Basic workflow:**
1. Make changes locally
2. `git add .`
3. `git commit -m "message"`
4. `git push origin master`
5. Wait 1-2 minutes for deployment
6. View live site!

---

*Last Updated: February 16, 2026*
*Repository: SyncShepherd-Main/alpha-rigging-website*
*Branch: master*
