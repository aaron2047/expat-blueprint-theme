# Expat Blueprint Shopify Theme — Deployment Guide

## Overview
This is a custom Shopify theme built from your Lovable prototype. It includes 6 reusable liquid sections, responsive CSS, and is fully wired to your products.

---

## What's Included

### Sections
- `hero.liquid` — Hero banner with headline, description, and CTA
- `pillars.liquid` — Three-pillar framework section
- `checklist-cta.liquid` — Email opt-in section
- `pricing.liquid` — Dynamic pricing tiers pulling your Shopify products
- `eeat.liquid` — Verification/trust section
- `header.liquid` — Sticky navigation header
- `footer.liquid` — Footer with disclaimer

### Templates
- `index.json` — Home page assembles all sections

### Assets
- `theme.css` — Complete styling with responsive design
- `settings_data.json` — Color and typography configuration

---

## Prerequisites

1. **Shopify CLI** installed locally
   ```bash
   npm install -g @shopify/cli
   ```

2. Access to your Shopify store admin (aaron@woolph.marketing)

3. Git (optional, but recommended)

---

## Step 1: Clone or Copy Theme to Local Directory

```bash
# If you have the theme directory locally, navigate to it:
cd expat-blueprint-theme
```

---

## Step 2: Connect to Your Shopify Store

```bash
# From inside the theme directory, authenticate:
shopify theme dev

# When prompted, enter:
# - Store: expatblueprint.store
# - Password: Your Shopify API token (or generate one in Shopify admin)
```

This starts a local dev server. Open the provided localhost URL to see a preview.

---

## Step 3: Configure Products in Shopify Admin

Before deploying, link your products in the Pricing section:

1. Go to **Shopify Admin** > **Sales channels** > **Online Store** > **Themes**
2. Find the theme you're deploying
3. Click **Customize**
4. In the theme editor, navigate to **Home** page
5. Click on the **Pricing Tiers** section
6. Under **Settings**:
   - **Entry Manual Product** → Select "The Expat Blueprint — Healthcare & Skilled Trades Edition" ($27)
   - **Blueprint Bundle Product** → Select "The Expat Blueprint — Personalized Blueprint Report" ($97)
   - **Concierge Product** → Select "The Expat Blueprint — Concierge" ($297)

---

## Step 4: Customize Sections (Optional)

All sections are fully customizable in the **Shopify Theme Editor**:

- Change headlines, descriptions, colors
- Modify button text and links
- Reorder sections by dragging
- Add or remove sections

**No code changes required** — all customization happens in the admin.

---

## Step 5: Deploy to Live Store

### Option A: Via Shopify CLI (Recommended)

```bash
# From theme directory:
shopify theme push

# When prompted to confirm:
#   Enter 'y' to push to live theme
# Or specify the theme:
shopify theme push --unpublished
# (This keeps it as a draft until you publish manually)
```

### Option B: Via Shopify Admin

1. Go to **Online Store** > **Themes**
2. Click **Add theme** > **Upload theme**
3. Zip the entire `expat-blueprint-theme` directory
4. Upload the `.zip` file
5. Once uploaded, click **Publish**

---

## Step 6: Verify Live Store

1. Visit **https://expatblueprint.store**
2. Verify all sections render correctly
3. Test the CTAs:
   - Hero button → Checkout for first product
   - Checklist email form → Works (you can integrate with email service)
   - Pricing buttons → Each links to correct product checkout

---

## Step 7: Integrate Email Service (Optional)

The checklist form (`checklist-cta.liquid`) is currently a static form. To capture emails:

### Option A: Shopify Email (Built-in)
- Use Shopify Email app
- Modify form action in `checklist-cta.liquid` to post to a Shopify email list

### Option B: External Service (Klaviyo, Kit, Substack)
1. Get the form action URL from your email platform
2. Edit `checklist-cta.liquid`
3. Change: `<form class="checklist-form" action="#" method="POST">`
4. To: `<form class="checklist-form" action="YOUR_EMAIL_SERVICE_ENDPOINT" method="POST">`

---

## Troubleshooting

### Products not showing in pricing section?
- Confirm products are published (not Draft)
- Make sure you've selected the correct product GID in theme settings
- Clear browser cache and refresh

### Styling looks broken?
- Check that `theme.css` is in `/assets/`
- Verify CSS file is loading: Inspect → Network tab
- Check browser console for errors

### Form not working?
- Email form is currently static (no backend)
- To make it functional, integrate with Shopify Email or external service

### Theme won't deploy?
- Confirm Shopify CLI is authenticated: `shopify auth list`
- Check store name: `shopify theme info`
- Try: `shopify theme push --development`

---

## File Structure

```
expat-blueprint-theme/
├── layout/
│   └── theme.liquid
├── sections/
│   ├── header.liquid
│   ├── hero.liquid
│   ├── pillars.liquid
│   ├── checklist-cta.liquid
│   ├── pricing.liquid
│   ├── eeat.liquid
│   └── footer.liquid
├── templates/
│   └── index.json
├── assets/
│   └── theme.css
├── config/
│   └── settings_data.json
└── README.md (this file)
```

---

## Customization Reference

### Colors
Edit in `theme.css` `:root` section:
```css
--color-navy: #1a1f3a;
--color-gold: #d4af37;
--color-cream: #f9f7f3;
--color-text: #2d3142;
```

### Typography
All fonts are system fonts (fast) + Georgia serif for headers.
Change in CSS or via theme settings.

### Sections
Each section is independent and can be:
- Duplicated
- Reordered
- Hidden (via theme editor)
- Customized via settings (no code change needed)

---

## Next Steps

1. **Email Integration** — Wire the checklist form to Klaviyo or your email platform
2. **Analytics** — Add Google Analytics or Shopify Analytics
3. **Checkout Optimization** — Test checkout flow, optimize for conversions
4. **SEO** — Configure meta descriptions, open graph, schema markup
5. **Images** — Add product images/mockups to sections as needed

---

## Support

For theme customization beyond these docs:
- Shopify Theme Development: https://shopify.dev/docs/themes
- Liquid Documentation: https://shopify.dev/docs/api/liquid
- Shopify Community: https://community.shopify.com

---

**Built for Woolph Marketing — Expat Blueprint Edition 2026**
