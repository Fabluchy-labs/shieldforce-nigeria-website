# ShieldForce Nigeria Website

## Overview

This repository contains the website files for **ShieldForce Nigeria**, a website presenting enterprise cybersecurity solutions and related products and insights for Nigerian businesses.

The supplied website package is a collection of static HTML pages and assets. It does **not** appear to be a complete WordPress installation: it does not contain the usual WordPress core directories (`wp-admin`, `wp-includes`) or a WordPress database export. If the live website is running WordPress, obtain a separate full WordPress files-and-database backup before treating this package as the complete website.

## Website pages

| File | Purpose |
|---|---|
| `index.html` | Main homepage |
| `standard.html` | ShieldForce Standard product/edition page |
| `blog.html` | Blog listing page |
| `blog-post02ee.html` | Blog post page |
| `index18de.html`, `index1fe3.html`, `indexc523.html`, `index-2.html` | Additional homepage variants or copies; confirm which, if any, are in use before deleting them |

## Assets and supporting files

- `assets/images/` — logo-related and product/licence images.
- `shieldforceWhite.png` — ShieldForce logo image used by the HTML pages.
- `cdnjs.cloudflare.com/` — a local copy of Font Awesome CSS included in the package.
- `cdn-cgi/` — Cloudflare email-decoding script found in the package.
- `php.ini` — PHP configuration file included in the archive; verify whether your hosting setup needs it before deploying.
- `cgi-bin/` — directory included in the archive.

The pages reference Google Fonts and use Font Awesome icons. Those external services or local assets must remain available for the site to render as intended.

## Requirements

- A web host that can serve HTML, CSS, JavaScript and image files.
- A domain configured to point to the hosting account.
- HTTPS enabled for the domain.
- A modern web browser for testing.

The supplied package appears to be primarily static HTML. A database or PHP application is not evident from the page files inspected, but hosting configuration and any server-side functionality should be verified before deployment.

## Local preview on Windows

1. Extract the website ZIP into a working folder.
2. Open `index.html` in a browser to preview the homepage.
3. Navigate through the homepage links and test the blog and product pages.
4. If any fonts, icons or images are missing, check the relative file paths and browser developer console.

Some pages in this package use relative paths such as `../assets/...` and `../../cdnjs.cloudflare.com/...`. Because the archive places HTML files and asset folders at the same top level, verify these paths before publishing. Correct any paths that do not match the actual deployment directory structure.

## Deployment to cPanel / Truehost

1. Make a full backup of the current live website before replacing any files.
2. Test the package on a staging subdomain first.
3. In cPanel File Manager, open the correct document root for the domain (often `public_html`, but it can differ).
4. Upload the approved website files and folders, preserving the directory structure.
5. Confirm that `index.html` is in the document root if it is intended to be the homepage.
6. Check HTTPS, navigation, images, icons, contact links and responsive layouts on desktop and mobile.
7. Only replace the live site after staging tests pass.

**Do not overwrite an existing WordPress installation with this package unless you intentionally plan to replace WordPress with this static site and have verified the migration requirements.**

## GitHub maintenance workflow

Use a **private GitHub repository** for collaboration and code history.

1. Keep a separate, dated backup of the full production site.
2. Review the files before the first commit.
3. Do not commit passwords, API keys, database credentials, private customer information, or production database dumps.
4. Use branches for changes, for example `feature/update-homepage`.
5. Submit pull requests and have another team member review changes.
6. Deploy to staging first; test the site before deploying approved changes to production.
7. Keep a deployment/rollback note for each production release.

### Suggested `.gitignore`

```gitignore
# Secrets and local configuration
wp-config.php
.env
.env.*

# Database exports and backups
*.sql
*.sql.gz
*.sql.zip
*.bak
*.zip

# Logs and temporary files
*.log
*.tmp
.DS_Store
Thumbs.db
```

Review the ignore rules before using them: do not exclude required source assets, and do not assume `.gitignore` removes a file that was already committed.

## Backup and recovery

For the live website, store backups separately from GitHub:

- A full files/account backup.
- A database export if the live site uses WordPress or another database-backed application.
- Any required uploads, certificates or configuration files.

Test restoration periodically. Git history can restore tracked source files, but it does not restore an untracked database, user uploads, or hosting configuration.

## Pre-release checklist

- [ ] Full live-site backup completed.
- [ ] Confirmed whether the live site is static HTML or WordPress.
- [ ] Confirmed the correct document root.
- [ ] Verified all relative image, stylesheet and script paths.
- [ ] Tested navigation, blog links and product links.
- [ ] Tested contact/email links.
- [ ] Checked the site on desktop and mobile.
- [ ] Verified HTTPS.
- [ ] Reviewed for secrets and private data before pushing to GitHub.
- [ ] Tested staging and documented rollback steps.

## Notes

This README is based on inspection of the supplied `Shieldforce.zip` archive. Confirm the live website's actual hosting structure and active pages before deleting duplicate-looking files or deploying changes.
