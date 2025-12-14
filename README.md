# MegaDescontos.pt

Landing page system for affiliate marketing campaigns targeting Portugal market.

## 🚀 Quick Start

This project is deployed on Vercel and connected to GitHub for automatic deployments.

- **Production:** https://megadescontos.pt
- **GitHub:** https://github.com/waleedpersonal/megadescontos

## 📁 Project Structure

```
megadescontos/
├── public/                  # Static pages (homepage, about, etc.)
├── campaigns/               # Landing pages organized by merchant
│   └── aliexpress/
│       ├── config.json     # Configuration for codes/URLs
│       ├── live.html       # Currently live page
│       ├── variant-a.html  # Test variation A
│       ├── variant-b.html  # Test variation B
│       └── variant-c.html  # Test variation C
├── templates/              # Reusable templates
├── vercel.json            # Vercel routing configuration
├── CAMPAIGNS.md           # Track active campaigns
└── PROJECT-PLAN.md        # Detailed project documentation
```

## 🔧 How to Add a New Campaign

### 1. Create folder structure
```bash
mkdir -p campaigns/new-merchant
```

### 2. Copy a template or create new landing page
```bash
cp templates/template-minimal.html campaigns/new-merchant/variant-a.html
cp campaigns/new-merchant/variant-a.html campaigns/new-merchant/live.html
```

### 3. Create config.json
```json
{
  "merchant": "New Merchant",
  "live_variant": "variant-a",
  "variants": {
    "variant-a": {
      "code": "CODE123",
      "discount": "50%",
      "affiliate_url": "https://...",
      "auto_redirect": true
    }
  }
}
```

### 4. Update vercel.json
Add routing rule:
```json
{ "source": "/new-merchant", "destination": "/campaigns/new-merchant/live.html" }
```

### 5. Test and Deploy
```bash
git checkout dev
git add .
git commit -m "Add new-merchant campaign"
git push origin dev
# Test on preview URL
# Merge to main when ready
```

## 🔄 How to Switch Live Variant (A/B Testing)

### Step 1: Update config.json
Change the `live_variant` field:
```json
{
  "live_variant": "variant-b"  // Changed from variant-a
}
```

### Step 2: Update the live.html file
```bash
cp campaigns/aliexpress/variant-b.html campaigns/aliexpress/live.html
```

### Step 3: Commit and push
```bash
git add campaigns/aliexpress/
git commit -m "Switch AliExpress to variant-b"
git push origin main
```

**Live in seconds!**

## 🌿 Git Workflow

### Branches
- `main` - Production (auto-deploys to megadescontos.pt)
- `dev` - Development (auto-deploys to preview URL)

### Workflow
1. Work in `dev` branch
2. Test on preview URL
3. Create PR to `main`
4. Merge when ready

## 📊 URL Structure

- `/` - Homepage
- `/sobre` - About us
- `/privacidade` - Privacy policy
- `/termos` - Terms of service
- `/contacto` - Contact
- `/aliexpress` - AliExpress campaign
- `/[merchant-name]` - Other campaigns

## 🔐 Environment Variables

No environment variables needed for basic setup. Add analytics IDs directly in HTML files if needed.

## 📈 Analytics

To add Google Analytics:
1. Get your GA4 Measurement ID
2. Add tracking code to all HTML files before `</head>`

To add Facebook Pixel:
1. Get your Pixel ID
2. Add pixel code to all HTML files before `</head>`

## 🆘 Troubleshooting

**Problem:** Changes not showing
- Clear browser cache
- Check if you're on the right branch
- Verify Vercel deployment status

**Problem:** 404 on new campaign URL
- Check vercel.json routing rules
- Verify file paths are correct
- Redeploy on Vercel

## 📞 Support

- Full documentation: See `PROJECT-PLAN.md`
- Campaign tracker: See `CAMPAIGNS.md`

---

**Last Updated:** December 14, 2025

