# Granite Field Holdings, Ltd. Co. — Corporate Website

> Static corporate website for **Granite Field Holdings, Ltd. Co.**, a private holding company engaged in strategic asset and intellectual property management, registered in the State of New Mexico, USA.

---

## Overview

This repository contains the source code for the official corporate web presence of Granite Field Holdings, Ltd. Co. The site is a single-file, dependency-free static HTML page designed for institutional credibility, regulatory transparency, and professional presentation.

---

## Site Structure

The website is organized into five navigable sections rendered as discrete pages within a single HTML file — no page reloads, no backend required.

| Page | Description |
|---|---|
| **Overview** | Hero landing section with entity classification details |
| **About** | Corporate narrative, operational model, and foundational principles |
| **Governance** | Core operational areas: IP governance, capital allocation, strategic architecture, and compliance |
| **Compliance & Legal** | Regulatory disclosures, statutory citations, AML notice, securities disclaimer, and governing law |
| **Contact** | Corporate contact details and institutional engagement policy |

---

## Technical Details

| Property | Value |
|---|---|
| **File** | `granite-field-holdings.html` |
| **Type** | Static HTML — single file |
| **Dependencies** | None (zero npm packages, no build step) |
| **External Resources** | Google Fonts CDN (`Cormorant Garamond`, `Jost`) |
| **JavaScript** | Vanilla JS — page routing, mobile menu, copyright year |
| **CSS** | Embedded — CSS custom properties, Grid, Flexbox |
| **Accessibility** | ARIA roles, semantic HTML5, keyboard navigation, `<dl>/<dt>/<dd>` for structured data |
| **SEO** | `<meta description>`, `robots` directive, Open Graph tags |
| **Responsive** | Mobile-first breakpoints; hamburger nav below 900px |

---

## Deployment

### GitHub Pages (Recommended)

1. Fork or clone this repository.
2. Go to **Settings → Pages**.
3. Set source to the branch and root directory containing `granite-field-holdings.html`.
4. Rename the file to `index.html` if deploying to the root of the Pages site.

```bash
cp granite-field-holdings.html index.html
```

5. GitHub Pages will serve the site at:
   `https://<your-username>.github.io/<repository-name>/`

---

### Netlify

1. Drag and drop `granite-field-holdings.html` into the Netlify dashboard, **or**
2. Connect this repository and set:
   - **Build command:** *(leave blank)*
   - **Publish directory:** `.` (repository root)
3. Rename to `index.html` for root-path serving.

---

### Vercel

```bash
npx vercel --prod
```

No configuration file required. Vercel will detect the static HTML automatically.

---

### Self-Hosted / VPS (nginx example)

```nginx
server {
    listen 80;
    server_name granitefieldholdings.com www.granitefieldholdings.com;
    root /var/www/granite-field-holdings;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

Place `granite-field-holdings.html` (renamed to `index.html`) in `/var/www/granite-field-holdings/`.

---

### Custom Domain

After deployment, point your DNS records to your hosting provider:

| Record Type | Name | Value |
|---|---|---|
| `A` | `@` | Your host's IP address |
| `CNAME` | `www` | Your Pages/Netlify/Vercel domain |

---

## Customization

All content and styling is contained within the single HTML file. Key areas to update:

### Contact Information
Search for `legal@granitefieldholdings.com` and the mailing address block to update corporate contact details.

### Copyright Year
The copyright year is dynamically set via JavaScript:
```js
document.querySelectorAll('.year').forEach(el => el.textContent = new Date().getFullYear());
```
No manual update required.

### Colors & Typography
All design tokens are defined as CSS custom properties at the top of the `<style>` block:
```css
:root {
  --gold:       #b89456;
  --gold-light: #d4b07a;
  --bg:         #09090b;
  --serif:      'Cormorant Garamond', Georgia, serif;
  --sans:       'Jost', 'Helvetica Neue', sans-serif;
  /* ... */
}
```

### Adding a Page
1. Add a `<button>` entry to both `.nav-links` and `.mobile-menu`.
2. Register the page ID in the `pages` array in the `<script>` block.
3. Add a corresponding `<div id="page-<name>" class="page">` section.

---

## Legal & Compliance Notes

This website includes the following institutional disclosures in the **Compliance & Legal** section:

- New Mexico LLC Act registration notice (NMSA 1978, §§ 53-19-1 through 53-19-74)
- U.S. Copyright Act (17 U.S.C.) and Lanham Act (15 U.S.C.) IP compliance statements
- Anti-Money Laundering (AML) / Bank Secrecy Act policy notice
- Securities non-offering disclaimer
- General legal disclaimer with governing law clause (State of New Mexico, Bernalillo County)
- Privacy and data governance statement

> **Note:** Legal language included in this website was drafted for general institutional transparency. It does not constitute legal advice. Consult qualified legal counsel to ensure all disclosures meet the specific requirements of your jurisdiction and operational context.

---

## Repository Structure

```
/
├── granite-field-holdings.html   # Complete website (rename to index.html for deployment)
└── README.md                     # This file
```

---

## License

All website content, design, and copy are the property of **Granite Field Holdings, Ltd. Co.** All rights reserved. Unauthorized reproduction, distribution, or modification of this material is prohibited.

---

*Granite Field Holdings, Ltd. Co. · Albuquerque, NM · legal@granitefieldholdings.com*
