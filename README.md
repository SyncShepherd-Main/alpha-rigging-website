# Alpha Rigging - Professional Industrial Rigging Services

> **Internal mockup for team review - Not for public distribution**

[![Live Demo](https://img.shields.io/badge/Demo-Live-success.svg)](https://syncshepherd-main.github.io/alpha-rigging-website/)

## 🌐 Live Demo

**View Site:** [https://syncshepherd-main.github.io/alpha-rigging-website/](https://syncshepherd-main.github.io/alpha-rigging-website/)

---

## 🎯 Overview

This is a complete, SEO-optimized website for a professional industrial rigging company serving Washington State. The site is designed to rank first in search results for industrial rigging, heavy equipment moving, and structural steel rigging across the Pacific Northwest.

## 📝 Recent Updates (2026-02-17)

**Major changes - see [CHANGELOG.md](CHANGELOG.md) and [UPDATES-2026-02-17.md](UPDATES-2026-02-17.md) for full details:**
- ✅ **Removed crane services** - Deleted page and all references (not a primary service)
- ✅ **Updated to 24/6 availability** - Company not open Saturdays (was incorrectly showing 24/7)
- ✅ **Created contact page** - New dedicated contact.html with full form
- ✅ **Updated all navigation** - Site-wide updates to links and CTAs

## 📁 Directory Structure

```
alpha-rigging-website-complete/
├── index.html                          # Homepage
├── about.html                          # About page
├── contact.html                        # Contact page (NEW - 2026-02-17)
├── services/                           # Service pages
│   ├── heavy-equipment-moving.html
│   ├── structural-steel-rigging.html
│   ├── plant-maintenance.html
│   ├── load-engineering.html
│   └── material-handling.html
├── locations/                          # Location pages
│   ├── seattle-rigging-services.html
│   └── [11 more location pages needed]
├── assets/
│   ├── css/                           # Stylesheets (inline for now)
│   ├── js/                            # JavaScript (inline for now)
│   └── images/                        # Images directory (empty - add your photos)
├── docs/                              # Documentation
│   ├── COMPETITOR_ANALYSIS_SEO_STRATEGY.md
│   ├── SEO_IMPLEMENTATION_ROADMAP.md
│   └── PAGE_GENERATION_GUIDE.md
└── README.md                          # This file
```

## 🚀 Quick Start - Deploy to GitHub Pages

### Option 1: Using Claude Code CLI (Recommended)

1. **Initialize Git repository:**
```bash
cd alpha-rigging-website-complete
git init
git add .
git commit -m "Initial commit: Alpha Rigging website"
```

2. **Create GitHub repository and push:**
```bash
# Create a new repository on GitHub (via web or gh CLI)
gh repo create alpha-rigging-website --public --source=. --push

# Or manually:
git remote add origin https://github.com/YOUR-USERNAME/alpha-rigging-website.git
git branch -M main
git push -u origin main
```

3. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Source: Deploy from branch
   - Branch: main / (root)
   - Save

Your site will be live at: `https://YOUR-USERNAME.github.io/alpha-rigging-website/`

### Option 2: Using GitHub Desktop

1. Open GitHub Desktop
2. File → Add Local Repository
3. Choose the `alpha-rigging-website-complete` folder
4. Publish repository to GitHub
5. Enable GitHub Pages in repository settings

### Option 3: Manual Upload

1. Create new repository on GitHub.com
2. Upload all files and folders
3. Enable GitHub Pages in settings

## 🌐 Deployment Options

### GitHub Pages (Free)
- **Cost:** Free
- **Custom Domain:** Yes (add CNAME file)
- **SSL:** Automatic
- **Best for:** Testing, portfolio, initial launch

### Netlify (Recommended for Production)
1. Connect GitHub repository to Netlify
2. Build settings: None needed (static HTML)
3. Deploy
4. Add custom domain in Netlify settings

### Vercel
1. Import GitHub repository
2. Deploy (automatic)
3. Configure custom domain

### Traditional Web Hosting
1. Upload all files via FTP
2. Point domain to hosting
3. Ensure index.html is in root

## 🔧 Configuration Needed

### Before Going Live:

1. **Update Contact Information:**
   - Search and replace `(509) 555-0100` with real phone number
   - Update `info@alpharigginginc.com` with real email
   - Update address in footer and schema markup

2. **Add Real Business Details:**
   - Replace `123 Industrial Way, Seattle, WA 98101` with actual address
   - Update business hours if different
   - Add actual insurance/license numbers

3. **Add Images:**
   - Equipment photos → `/assets/images/equipment/`
   - Project photos → `/assets/images/projects/`
   - Team photos → `/assets/images/team/`
   - Facility photos → `/assets/images/facility/`
   - Logo → `/assets/images/logo.png`

4. **Update Schema Markup:**
   - Add actual business coordinates (lat/long)
   - Add real business registration numbers
   - Update actual review count/ratings when available

5. **Configure Forms:**
   - Current forms are HTML only
   - Set up form backend (FormSpree, Netlify Forms, or custom)
   - Update form action URLs

## 📊 SEO Setup Checklist

### Immediate (Before Launch):
- [ ] Google Search Console verification
- [ ] Google Analytics 4 setup
- [ ] Google Business Profile claimed
- [ ] Bing Webmaster Tools
- [ ] robots.txt file created
- [ ] sitemap.xml generated and submitted

### Week 1:
- [ ] Complete remaining 4 service pages
- [ ] Complete remaining 11 location pages
- [ ] Submit to top 50 citations
- [ ] Set up review generation system

### Month 1:
- [ ] 100+ citations completed
- [ ] First 10 backlinks acquired
- [ ] 25+ Google reviews
- [ ] Blog content strategy launched

See `/docs/SEO_IMPLEMENTATION_ROADMAP.md` for complete timeline.

## 🎨 Customization Guide

### Colors
Current color scheme (in CSS variables):
- Primary Orange: `#FF6B2C`
- Deep Charcoal: `#1A1D23`
- Steel Gray: `#4A5568`
- Concrete Gray: `#E2E8F0`

To change: Search and replace hex codes in HTML files.

### Fonts
Current: Bebas Neue (headings) + Outfit (body)
Loaded from Google Fonts - modify `<link>` tag in each HTML file.

### Layout
All styling is inline in each HTML file for simplicity.
For easier maintenance, extract CSS to `/assets/css/style.css`

## 📝 Content Creation

### Remaining Pages Needed:

**Service Pages (4):**
1. Structural Steel Rigging
2. Plant Maintenance Support
3. Load Engineering & Lift Planning
4. Material Handling Solutions

**Location Pages (11):**
1. Tacoma
2. Spokane
3. Bellevue
4. Everett
5. Vancouver
6. Yakima
7. Bellingham
8. Olympia
9. Tri-Cities (Pasco/Richland/Kennewick)
10. South King County (Kent/Renton/Auburn)
11. Eastside (Redmond/Kirkland)

Use the templates in `/docs/PAGE_GENERATION_GUIDE.md` to create these pages efficiently.

## 🔒 Security Notes

- All forms currently HTML only (no backend)
- No user authentication needed
- No database required
- Static HTML = inherently secure
- Enable SSL/HTTPS (automatic with GitHub Pages, Netlify, Vercel)

## 📈 Analytics Setup

### Google Analytics 4:
Add this code before `</head>` in all HTML files:

```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Google Search Console:
Add verification meta tag to homepage:
```html
<meta name="google-site-verification" content="YOUR-VERIFICATION-CODE" />
```

## 🛠️ Maintenance

### Weekly:
- Respond to contact form submissions
- Update Google Business Profile
- Monitor analytics and rankings
- Check for broken links

### Monthly:
- Add new blog content (if implemented)
- Update service areas if expanding
- Review and respond to reviews
- Check competitor activity

### Quarterly:
- Refresh content on key pages
- Update case studies/projects
- Review and update pricing
- Technical SEO audit

## 📞 Support & Documentation

- **SEO Strategy:** See `/docs/COMPETITOR_ANALYSIS_SEO_STRATEGY.md`
- **Implementation Roadmap:** See `/docs/SEO_IMPLEMENTATION_ROADMAP.md`
- **Content Templates:** See `/docs/PAGE_GENERATION_GUIDE.md`

## 🎯 Expected Results

### 6 Months:
- 30+ keywords in top 10
- 2,000+ monthly organic visits
- 50+ quality backlinks
- Domain Authority 35+

### 12 Months:
- #1 rankings for primary keywords
- 5,000+ monthly organic visits
- 75+ quality backlinks
- Market leadership position in WA

## 🚨 Important Notes

1. **Phone Numbers:** All phone numbers are placeholder (555). Update before launch!
2. **Email Addresses:** Update all email addresses to real ones
3. **Forms:** Need backend integration (FormSpree, Netlify Forms, etc.)
4. **Images:** Directory structure ready, add actual photos
5. **Legal:** Add Privacy Policy and Terms of Service pages
6. **Schema:** Update with real business data

## 📄 License

This website package is provided for your business use. Modify as needed.

## 🤝 Next Steps

1. **Review all content** and customize for your specific business
2. **Update contact information** throughout all files
3. **Add real images** to the images directory
4. **Complete remaining pages** using the templates
5. **Deploy to hosting** (GitHub Pages, Netlify, or your choice)
6. **Set up Google Search Console** and Analytics
7. **Claim Google Business Profile** and begin citation building
8. **Launch SEO campaign** following the implementation roadmap

---

## 📌 Notes

- This is the initial mockup for Alpha Rigging
- Designed for internal review and client evaluation
- Not for public distribution or replication
- All content and structure subject to revision based on client feedback
- Contact information and images are placeholders

---

**📅 Last Updated:** February 16, 2026
**🏗️ Status:** Ready for Client Review
**🌐 Live URL:** [https://syncshepherd-main.github.io/alpha-rigging-website/](https://syncshepherd-main.github.io/alpha-rigging-website/)

*For team and client review purposes only. Not for public distribution or replication.*
