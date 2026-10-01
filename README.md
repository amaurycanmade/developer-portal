# THE AMAURYCAN PULSE // HTML5 GITHUB PAGES DEPLOYMENT
**DEV Assembly Key:** `THE_AMAURYCAN_PULSE_HTML5_GITHUB_RELEASE-[TRCH0100]-90.90.md`  
**State Designation:** `STATE MADE` (v5.0 Release Lock)  
**Custom Domain:** `www.theamaurycanpulse.com`  

## 1. Executive Overview
This repository hosts the official production build of **THE AMAURYCAN PULSE** running on custom domain **`www.theamaurycanpulse.com`**. It is built as a single-file, zero-dependency, security-hardened HTML5 Single Page Application (SPA).

## 2. Cybersecurity & Hardening Controls
- **Content Security Policy (CSP)**: RESTRICTS script execution to local origins and trusted Google Fonts domains.
- **XSS Protection**: ALL dynamic JavaScript DOM elements use strict HTML escaping (`sanitizeInput`).
- **HTTP Security Headers**: Includes `X-Content-Type-Options: nosniff`, `X-Frame-Options: DENY`, `Referrer-Policy: strict-origin-when-cross-origin`, and `Permissions-Policy`.
- **HTTPS Enforcement**: Automatic HTTP-to-HTTPS redirect enforced via GitHub Pages settings.
- **Backwards Compatibility**: Includes HTML5 Shiv polyfill and responsive CSS flexbox/grid fallbacks for retro mobile compatibility.

## 3. GitHub Pages Deployment Steps
1. Push `index.html`, `CNAME`, `.nojekyll`, and `.github/workflows/deploy.yml` to the `main` branch.
2. In GitHub Repository Settings -> **Pages**:
   - Source: `GitHub Actions`
   - Custom domain: `www.theamaurycanpulse.com`
   - Enforce HTTPS: Checked
3. Verify site at `https://www.theamaurycanpulse.com`.
GitHub Actions Workflow (.github/workflows/deploy.yml [DSNRA:00.10.20.00]):
name: Deploy THE AMAURYCAN PULSE to GitHub Pages

on:
  push:
    branches:
      - main

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: true

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Setup Pages
        uses: actions/configure-pages@v4

      - name: Upload Artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'

      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
