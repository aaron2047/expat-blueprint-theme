# Expat Blueprint Theme — Quick Start (5 minutes)

## For the Impatient: Deploy in 5 Steps

### 1. Install Shopify CLI
```bash
npm install -g @shopify/cli
```

### 2. Authenticate to Your Store
```bash
cd expat-blueprint-theme
shopify theme dev
# ↳ Pick your store: expatblueprint.store
# ↳ Get preview link
```

### 3. Preview Locally
Visit the localhost URL to see your theme live.
Edit sections in the Shopify Theme Editor (browser-based).

### 4. Link Your Products
In the **Pricing Tiers** section settings:
- Entry Manual → The Expat Blueprint — Healthcare & Skilled Trades Edition ($27)
- Bundle → The Expat Blueprint — Personalized Blueprint Report ($97)
- Concierge → The Expat Blueprint — Concierge ($297)

### 5. Deploy Live
```bash
shopify theme push
# ✓ Your theme goes live at expatblueprint.store
```

---

## That's It

Your Lovable design is now a live Shopify store.

**What you get:**
- ✓ Mobile responsive
- ✓ Navy/gold aesthetic from your prototype
- ✓ All sections wired to your products
- ✓ Fast, clean code
- ✓ Easy to customize (no code required)

---

## Troubleshooting in 30 Seconds

**Theme won't load?**
```bash
shopify auth logout
shopify theme dev
```

**Products not showing in pricing?**
→ Make sure products are **Published** (not Draft) in Shopify admin.

**Want to customize colors?**
→ Go to **Shopify Admin > Themes > Customize > Hero section** and change colors in the browser editor. No code required.

---

## Next: Email Integration

Your checklist form is ready for Klaviyo/Kit integration.
Once you're live, we can wire the email capture in 2 minutes.

---

**Ready to go live?** Run step 5 above.
