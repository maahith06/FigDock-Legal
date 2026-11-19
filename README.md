# FigDock — Public Legal & Privacy Documentation Portal

Official legal documentation, privacy policy, and account deletion portal for **FigDock** (`app.figdock.financial`), an Android-first, multi-tenant financial tracking application.

---

## Purpose & Scope

This repository provides publicly accessible, zero-cost static web pages required for Google Play Store compliance, user transparency, and data protection regulations (UK GDPR / EU GDPR):

1. **Privacy Policy** (`/privacy/`): Transparent disclosure of data collection, processing lawful bases, third-party sub-processors (Firebase Auth, Cloud Firestore, Cloud Storage, Google Play Billing), statutory retention schedules (Companies Act 2006 s.388 & HMRC 6-year retention), pseudonymization to "Former Member", and user rights.
2. **Account & Data Deletion Portal** (`/account-deletion/`): Compliant external account deletion mechanism satisfying Google Play's requirement that users be able to request account and data deletion outside the mobile app without requiring reinstallation.
3. **Legal Portal Home** (`/`): Directory index linking to all official compliance resources.
4. **Custom 404 Handler** (`404.html`): Branded, responsive fallback directing visitors to valid documentation endpoints.

---

## Zero-Cost Architecture & Strict Independence

- **No Cloudflare Dependencies**: This repository does not use Cloudflare Workers, Cloudflare D1, or Cloudflare KV.
- **CheekyCycle Isolation**: This repository is strictly independent from CheekyCycle infrastructure, accounts, and domains.
- **Static Only**: Implemented with pure, standards-compliant static HTML5 and CSS. No dynamic backend runtime, database, or server maintenance required.
- **Zero Recurring Cost**: Hosted exclusively using GitHub Pages free static site hosting.

---

## Directory Structure

```text
figdock-legal/
├── .nojekyll                 # Disables Jekyll processing on GitHub Pages
├── 404.html                  # Branded 404 error page
├── README.md                 # Repository documentation & deployment instructions
├── index.html                # Legal portal landing directory
├── account-deletion/
│   └── index.html            # Google Play account & data deletion portal
└── privacy/
    └── index.html            # Comprehensive FigDock privacy policy
```

---

## Deployment & Setup Guide (GitHub Pages)

### 1. Repository Creation
Create a new **public** repository named `figdock-legal` under your personal/FigDock GitHub account (do **not** create under `cheekycycle`):

```bash
cd ~/Developer/figdock-legal
git init -b main
git add .
git commit -m "feat: initial static legal site for FigDock (app.figdock.financial)"
git remote add origin https://github.com/<YOUR_FIGDOCK_GITHUB_USERNAME>/figdock-legal.git
git push -u origin main
```

### 2. Enable GitHub Pages
1. Navigate to your repository settings: `https://github.com/<YOUR_FIGDOCK_GITHUB_USERNAME>/figdock-legal/settings/pages`.
2. Under **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`
   - **Folder**: `/ (root)`
3. Click **Save**.
4. GitHub Pages will build and deploy the site within 1–2 minutes.

### 3. Public URLs
Once deployed, the live endpoints will be accessible at:
- **Portal Index**: `https://<YOUR_FIGDOCK_GITHUB_USERNAME>.github.io/figdock-legal/`
- **Privacy Policy**: `https://<YOUR_FIGDOCK_GITHUB_USERNAME>.github.io/figdock-legal/privacy/`
- **Account Deletion**: `https://<YOUR_FIGDOCK_GITHUB_USERNAME>.github.io/figdock-legal/account-deletion/`

---

## Play Console Declaration Updates

When GitHub Pages is live and verified, update the following fields in the Google Play Console (`app.figdock.financial`):

1. **Policy and Programs > Privacy Policy**:
   `https://<YOUR_FIGDOCK_GITHUB_USERNAME>.github.io/figdock-legal/privacy/`
2. **App Content > Data Safety > Account Deletion**:
   `https://<YOUR_FIGDOCK_GITHUB_USERNAME>.github.io/figdock-legal/account-deletion/`

---

## License & Attribution

Copyright &copy; 2026 FigDock. All rights reserved.
