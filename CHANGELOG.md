# Alpha Rigging Website - Changelog

All notable changes to this project will be documented in this file.

## [2026-02-17] - Content & Structure Updates

### Added
- **New Contact Page (contact.html)**
  - Dedicated standalone contact page with full contact form
  - Complete contact information (phone, email, location)
  - Hero section with "Contact Us" heading
  - Professional design matching site branding
  - SEO-optimized meta tags
  - Added to sitemap with high priority (0.9)
  - URL: `/contact.html`

### Changed
- **Removed Crane Services**
  - Deleted `services/crane-services.html` page completely
  - Removed all crane services references from navigation menus (19 pages)
  - Removed crane services sections from all location pages (12 pages)
  - Updated meta descriptions and keywords to remove crane references
  - Removed crane services from homepage service cards
  - Removed crane services from contact form dropdown
  - Updated sitemap.xml to remove crane services entry
  - Reason: Company does not actively promote crane services
  - Files affected: 21 files (1 deleted, 20 modified)
  - Lines changed: -567 insertions, +43 deletions

- **Updated Availability from 24/7 to 24/6**
  - Changed all "24/7" references to "24/6" across entire website
  - Updated "7 days a week" to "6 days a week"
  - Modified meta descriptions to reflect 24/6 emergency service
  - Updated call-to-action buttons to "Call 24/6"
  - Changed stats bar display to "24/6 Emergency Service"
  - Updated emergency response descriptions throughout site
  - Reason: Company is not open on Saturdays and does not provide emergency service on Saturdays
  - Files affected: 24 files (19 HTML, 5 MD documentation)
  - Instances changed: 76 occurrences

- **Navigation Menu Updates**
  - Updated all navigation menus to link to new contact.html page
  - Changed all #contact anchor links to dedicated contact.html page
  - Updated CTA buttons throughout site to point to contact page
  - Updated footer "Contact" links across all pages
  - Files affected: All HTML pages (20 files)

- **Sitemap Updates**
  - Added about.html to sitemap (priority 0.8)
  - Added contact.html to sitemap (priority 0.9)
  - Updated homepage lastmod date to 2026-02-17
  - Removed crane services entry

### Summary Statistics
- **Total commits today:** 3
- **Total files changed:** 45 (across all commits)
- **New pages created:** 1 (contact.html)
- **Pages deleted:** 1 (crane-services.html)
- **Lines added:** ~896
- **Lines removed:** ~615

### Git Commit References
1. `dbea981` - Remove crane services from website
2. `b36773d` - Update availability from 24/7 to 24/6 (not open Saturdays)
3. `05061c9` - Add dedicated contact page

### Testing Recommendations
- [ ] Verify contact page loads correctly
- [ ] Test contact form functionality (forms currently HTML only, need backend)
- [ ] Check all navigation links point to correct pages
- [ ] Verify no broken links to crane services page
- [ ] Confirm 24/6 messaging is consistent across all pages
- [ ] Test mobile responsiveness on contact page

### Future Considerations
- Contact form needs backend integration (recommend Netlify Forms or FormSpree)
- Consider adding Privacy Policy and Terms of Service pages
- May want to add FAQ page in the future
- Consider blog section for SEO content marketing

---

## Live Website
- **URL:** https://syncshepherd-main.github.io/alpha-rigging-website/
- **GitHub Repo:** https://github.com/SyncShepherd-Main/alpha-rigging-website
- **Branch:** master
- **Last Updated:** 2026-02-17

---

## Contact Information (Current)
- **Phone:** (509) 555-0100
- **Emergency:** (509) 555-0911
- **Email:** info@alpharigging.com, trevor@alpharigging.com
- **Location:** Chehalis, Washington
- **Hours:** Mon-Fri: 7:00 AM - 6:00 PM
- **Availability:** 24/6 (not available Saturdays)

---

*Note: All changes co-authored with Claude Sonnet 4.5 AI assistant*
