# 📋 MegaDescontos.pt - Project Plan & Documentation

**Date Created:** December 14, 2025  
**Domain:** megadescontos.pt  
**Purpose:** Scalable affiliate landing page system for Google Ads campaigns  
**Stack:** GitHub + Vercel + Cursor IDE

---

## 🎯 Project Overview

Building a robust, yet simple affiliate marketing system that allows:
- Easy management of multiple landing page campaigns
- A/B testing without breaking live pages
- Config-driven updates (no code changes needed for URLs/codes)
- Google Ads compliant pages
- Clean URL structure
- Production-ready infrastructure

---

## 📁 Folder Structure

```
megadescontos/
│
├── public/                          # Static pages
│   ├── index.html                   # Homepage
│   ├── sobre.html                   # About us page
│   ├── privacidade.html             # Privacy policy (GDPR compliant)
│   ├── termos.html                  # Terms of service
│   └── contacto.html                # Contact page
│
├── campaigns/                       # All landing pages organized by merchant
│   │
│   ├── aliexpress/
│   │   ├── config.json             # Configuration file (codes, URLs, settings)
│   │   ├── live.html               # Currently live page (shown to visitors)
│   │   ├── variant-a.html          # Test variation A
│   │   ├── variant-b.html          # Test variation B
│   │   └── variant-c.html          # Test variation C
│   │
│   ├── iherb/
│   │   ├── config.json
│   │   ├── live.html
│   │   └── variant-a.html
│   │
│   ├── nike/
│   │   ├── config.json
│   │   └── live.html
│   │
│   └── [add-more-merchants-here]/
│
├── templates/                       # Reusable template files
│   ├── template-minimal.html       # Ultra-minimal red design
│   ├── template-reveal.html        # Interactive reveal/unlock design
│   ├── template-modern.html        # Dark modern design
│   └── README.md                   # Template usage guide
│
├── vercel.json                      # Vercel routing & configuration
├── README.md                        # Main documentation
├── CAMPAIGNS.md                     # Track active campaigns & ad spend
└── .gitignore                       # Git ignore rules
```

---

## 🌐 URL Structure

| URL | Page | Description |
|-----|------|-------------|
| `megadescontos.pt` | Homepage | Main landing page |
| `megadescontos.pt/sobre` | About Us | Company information |
| `megadescontos.pt/privacidade` | Privacy Policy | GDPR compliant privacy policy |
| `megadescontos.pt/termos` | Terms of Service | Legal terms |
| `megadescontos.pt/contacto` | Contact | Contact information |
| `megadescontos.pt/aliexpress` | AliExpress Campaign | Live AliExpress landing page |
| `megadescontos.pt/iherb` | iHerb Campaign | Live iHerb landing page |
| `megadescontos.pt/nike` | Nike Campaign | Live Nike landing page |

**Clean URLs** - No `.html` extensions, SEO friendly

---

## ⚙️ Config-Driven System

### How It Works

Each campaign has a `config.json` file that controls all settings. You can update codes, URLs, and switch live variants **without touching HTML**.

### Example: `campaigns/aliexpress/config.json`

```json
{
  "merchant": "AliExpress",
  "market": "Portugal",
  "live_variant": "variant-a",
  "variants": {
    "variant-a": {
      "name": "Minimal Red",
      "code": "PT70OFF",
      "discount": "70%",
      "affiliate_url": "https://aliexpress.com/?aff=your_id_here",
      "auto_redirect": true,
      "redirect_delay": 1200,
      "timer_hours": 6,
      "verified_text": "Verificado Hoje",
      "urgent_text": "Expira em 6 horas"
    },
    "variant-b": {
      "name": "Modern Dark",
      "code": "MEGA50",
      "discount": "50%",
      "affiliate_url": "https://aliexpress.com/?aff=your_id_here",
      "auto_redirect": true,
      "redirect_delay": 1500,
      "timer_hours": 3,
      "verified_text": "Funciona 100%",
      "urgent_text": "Oferta expira em 3 horas"
    },
    "variant-c": {
      "name": "Reveal Style",
      "code": "PT70DEAL",
      "discount": "70%",
      "affiliate_url": "https://aliexpress.com/?aff=your_id_here",
      "auto_redirect": true,
      "redirect_delay": 1500,
      "timer_hours": 4,
      "verified_text": "100% Verificado",
      "urgent_text": "Código expira em 4 horas"
    }
  }
}
```

### How to Switch Live Variant

**Before:**
```json
"live_variant": "variant-a"
```

**After:**
```json
"live_variant": "variant-b"
```

Commit → Push → Live in seconds!

---

## 🔀 Git Branching Strategy

```
main (production)
  │
  ├── Protected branch - cannot push directly
  ├── Deploys to: megadescontos.pt
  ├── Only merge after testing
  └── Live traffic goes here
  
dev (development/staging)
  │
  ├── Development branch - work here
  ├── Deploys to: megadescontos-git-dev.vercel.app
  ├── Test all changes before merging
  └── Safe playground
```

### Workflow

1. **Create new page or make changes in `dev` branch**
2. **Push to GitHub** → Vercel automatically creates preview URL
3. **Test on preview URL** → Make sure everything works
4. **Create Pull Request** from `dev` to `main`
5. **Merge to main** → Goes live instantly
6. **Monitor performance** → Check conversions

### Why This Works

✅ **Safety** - Live pages never break  
✅ **Testing** - Preview before going live  
✅ **Rollback** - Git history = instant undo  
✅ **Isolation** - Multiple people can work safely

---

## 🚀 Vercel Configuration

### `vercel.json` - Routing Rules

```json
{
  "rewrites": [
    { "source": "/", "destination": "/public/index.html" },
    { "source": "/sobre", "destination": "/public/sobre.html" },
    { "source": "/privacidade", "destination": "/public/privacidade.html" },
    { "source": "/termos", "destination": "/public/termos.html" },
    { "source": "/contacto", "destination": "/public/contacto.html" },
    { "source": "/aliexpress", "destination": "/campaigns/aliexpress/live.html" },
    { "source": "/iherb", "destination": "/campaigns/iherb/live.html" },
    { "source": "/nike", "destination": "/campaigns/nike/live.html" }
  ],
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "X-Frame-Options", "value": "DENY" },
        { "key": "X-Content-Type-Options", "value": "nosniff" },
        { "key": "X-XSS-Protection", "value": "1; mode=block" }
      ]
    }
  ]
}
```

### Deployment Settings

- **Framework Preset:** Other (static HTML)
- **Build Command:** None
- **Output Directory:** `.` (root)
- **Install Command:** None
- **Node Version:** 18.x (default)

---

## ✅ Google Ads Compliance

### Required Pages

To get Google Ads approval, you need:

1. ✅ **Homepage** (`index.html`)
   - Professional design
   - Clear explanation of service
   - Navigation to all pages
   
2. ✅ **About Us** (`sobre.html`)
   - Who you are
   - What you do
   - Why users should trust you
   
3. ✅ **Privacy Policy** (`privacidade.html`)
   - GDPR compliant
   - Cookie policy
   - Data collection disclosure
   - User rights
   
4. ✅ **Terms of Service** (`termos.html`)
   - Legal terms
   - Affiliate disclosure
   - Limitations of liability
   
5. ✅ **Contact** (`contacto.html`)
   - Email address
   - Contact form (optional)
   - Physical address (if required)

### Content Guidelines

- ✅ All in Portuguese (Portugal)
- ✅ Clear affiliate disclosure
- ✅ Professional tone
- ✅ No misleading claims
- ✅ Working navigation
- ✅ Mobile responsive

---

## 📊 Campaign Management

### CAMPAIGNS.md - Tracking File

Keep track of what's live to avoid accidents:

```markdown
# Active Campaigns - MegaDescontos.pt

Last Updated: 2025-12-14

## 🟢 Live Campaigns (DO NOT MODIFY WITHOUT BACKUP)

### AliExpress
- **URL:** megadescontos.pt/aliexpress
- **Live Variant:** variant-a (Minimal Red)
- **Code:** PT70OFF
- **Status:** ✅ Live
- **Ad Spend:** €500/day
- **Started:** 2025-12-10
- **Notes:** High conversion rate, keep as is

### iHerb
- **URL:** megadescontos.pt/iherb
- **Live Variant:** variant-b (Modern Dark)
- **Code:** IHERB30
- **Status:** ✅ Live
- **Ad Spend:** €300/day
- **Started:** 2025-12-12
- **Notes:** Testing social proof elements

## 🟡 In Testing

### Nike
- **URL:** megadescontos-git-dev.vercel.app/nike
- **Variant:** variant-a
- **Code:** NIKE20
- **Status:** 🧪 Testing
- **Ad Spend:** €0 (not live)
- **Notes:** Launch planned for 2025-12-18

## 🔴 Archived

### Old Campaign Example
- **Ended:** 2025-12-01
- **Reason:** Low conversion rate
- **Files:** Moved to /archive/ folder
```

---

## 🛠️ A/B Testing Strategy

### How to Run A/B Tests

1. **Create variants** - Make 2-3 different designs for same merchant
2. **Update config** - Point to variant-a initially
3. **Launch ads** - Run for 48-72 hours
4. **Switch variant** - Change to variant-b in config
5. **Compare results** - Check which converts better
6. **Pick winner** - Keep best performing variant live

### Testing Checklist

- [ ] Create at least 2 variants
- [ ] Same code/offer, different design
- [ ] Equal time for each variant (48h minimum)
- [ ] Same ad copy/targeting
- [ ] Track conversions separately
- [ ] Document results

### Example Test

```
Test: AliExpress Landing Page
Period: Dec 10-16, 2025

Variant A (Minimal Red):
- Traffic: 5,000 clicks
- Conversions: 450
- Rate: 9.0%

Variant B (Modern Dark):
- Traffic: 5,000 clicks
- Conversions: 550
- Rate: 11.0%

Winner: Variant B (+2% conversion)
Action: Set "live_variant": "variant-b"
```

---

## 🎨 Design Templates

### Template 1: Ultra-Minimal
**File:** `template-minimal.html`  
**Style:** Bold colors, simple layout, code front-and-center  
**Best for:** High-intent coupon searches  
**Psychology:** Direct, no friction

### Template 2: Modern Dark
**File:** `template-modern.html`  
**Style:** Dark gradient, premium feel, circular badge  
**Best for:** Link-only affiliates, trust-focused  
**Psychology:** Premium, trustworthy, social proof

### Template 3: Reveal/Unlock
**File:** `template-reveal.html`  
**Style:** Interactive, lock icon, click-to-reveal  
**Best for:** Creating engagement  
**Psychology:** Curiosity, exclusivity, gamification

---

## 📝 How to Add a New Campaign

### Step 1: Create Folder Structure
```bash
campaigns/
  new-merchant/
    ├── config.json
    ├── live.html
    └── variant-a.html
```

### Step 2: Copy Template
Choose a template from `/templates/` and customize it

### Step 3: Create Config
```json
{
  "merchant": "New Merchant",
  "market": "Portugal",
  "live_variant": "variant-a",
  "variants": {
    "variant-a": {
      "code": "CODE123",
      "discount": "50%",
      "affiliate_url": "https://...",
      "auto_redirect": true,
      "timer_hours": 6
    }
  }
}
```

### Step 4: Update Vercel.json
Add routing rule:
```json
{ "source": "/new-merchant", "destination": "/campaigns/new-merchant/live.html" }
```

### Step 5: Test & Deploy
1. Test in `dev` branch
2. Verify preview URL works
3. Merge to `main`
4. Launch ads!

---

## 🔐 Security & Best Practices

### Repository Protection

- ✅ Protect `main` branch - require PR approval
- ✅ Add `.gitignore` - exclude sensitive files
- ✅ Never commit API keys or credentials
- ✅ Use environment variables for secrets

### Performance

- ✅ Single-file HTML pages (no dependencies)
- ✅ Inline CSS for speed
- ✅ Optimize for mobile first
- ✅ Target <3 second load time
- ✅ Use Vercel CDN for global delivery

### SEO

- ✅ Add meta descriptions to all pages
- ✅ Use semantic HTML
- ✅ Mobile responsive design
- ✅ HTTPS (automatic with Vercel)
- ✅ Clean URL structure

---

## 📊 Analytics Integration

### Google Analytics

Add to all pages before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Facebook Pixel

Add for Meta Ads tracking:

```html
<!-- Facebook Pixel -->
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', 'YOUR_PIXEL_ID');
  fbq('track', 'PageView');
</script>
```

### Conversion Tracking

Track when users copy codes:

```javascript
function trackConversion() {
  // Google Analytics
  if (typeof gtag !== 'undefined') {
    gtag('event', 'coupon_copy', {
      'merchant': 'AliExpress',
      'code': CONFIG.code
    });
  }
  
  // Facebook Pixel
  if (typeof fbq !== 'undefined') {
    fbq('track', 'Lead', {
      content_name: CONFIG.code
    });
  }
}
```

---

## 🚀 Deployment Checklist

### Pre-Launch

- [ ] All pages created and tested
- [ ] Config files set up correctly
- [ ] Vercel.json routing configured
- [ ] Google Ads compliance pages complete
- [ ] Privacy policy GDPR compliant
- [ ] Analytics installed
- [ ] Mobile responsive verified
- [ ] Load time < 3 seconds

### Launch Day

- [ ] Domain connected to Vercel
- [ ] SSL certificate active
- [ ] All URLs working
- [ ] Forms tested (if any)
- [ ] Analytics tracking verified
- [ ] Submit to Google Ads for approval

### Post-Launch

- [ ] Monitor conversion rates
- [ ] Check for errors
- [ ] Set up A/B tests
- [ ] Document results
- [ ] Scale winning campaigns

---

## 🆘 Troubleshooting

### Common Issues

**Problem:** URL returns 404  
**Solution:** Check vercel.json routing, verify file paths

**Problem:** Config changes not reflecting  
**Solution:** Clear browser cache, check config.json syntax

**Problem:** Page not deploying  
**Solution:** Check GitHub Actions, verify Vercel connection

**Problem:** Slow load times  
**Solution:** Optimize images, inline CSS, check CDN

---

## 📞 Support & Resources

### Documentation
- [Vercel Docs](https://vercel.com/docs)
- [GitHub Docs](https://docs.github.com)
- [Google Ads Policy](https://support.google.com/adspolicy)

### Project Files
- Main Plan: `PROJECT-PLAN.md` (this file)
- Campaign Tracker: `CAMPAIGNS.md`
- Setup Guide: `README.md`
- Templates: `/templates/README.md`

---

## 📈 Success Metrics

### Track These KPIs

- **Click-through rate** (CTR) - Google Ads to landing page
- **Conversion rate** - Landing page to merchant click
- **Cost per conversion** - Ad spend / conversions
- **Revenue per click** - Commission / clicks
- **ROI** - Revenue / ad spend

### Goal Benchmarks

- CTR: >5%
- Conversion Rate: >8%
- Cost per Conversion: <€2
- ROI: >200%

---

## 🎯 Next Steps

1. ✅ Review and approve this plan
2. ⏳ Create GitHub repository
3. ⏳ Initialize folder structure
4. ⏳ Deploy to Vercel
5. ⏳ Connect domain (megadescontos.pt)
6. ⏳ Create compliance pages
7. ⏳ Migrate landing pages to system
8. ⏳ Test everything
9. ⏳ Launch first campaign
10. ⏳ Monitor and optimize

---

**Last Updated:** December 14, 2025  
**Status:** 📝 Planning Phase  
**Next Action:** Await approval to begin implementation

---

*This is a living document. Update as the project evolves.*

