# 🎨 Landing Page Templates Guide

**Last Updated:** December 14, 2025

---

## 📁 Available Templates

### Portuguese Templates (In `/campaigns/aliexpress/`)

#### **Variant A: Ultra-Minimal Red**
- **File:** `variant-a.html`
- **Colors:** Red/White (AliExpress brand)
- **Style:** Bold red background, simple white card
- **Best For:** Direct coupon searches, high-intent traffic
- **Psychology:** Minimal friction, instant gratification
- **Currently:** ✅ LIVE on production

#### **Variant B: Modern Dark**
- **File:** `variant-b.html`
- **Colors:** Dark gradient, Red accents
- **Style:** Premium dark design, circular badge, social proof
- **Best For:** Link-only affiliates, trust-focused campaigns
- **Psychology:** Premium feel, trustworthy, authority
- **Currently:** Available for A/B testing

#### **Variant C: Reveal/Unlock** (Updated with AliExpress colors!)
- **File:** `variant-c.html`
- **Colors:** Red/Orange gradient (AliExpress brand) 🎨 NEW!
- **Style:** Interactive lock icon, click-to-reveal
- **Best For:** Creating engagement, gamification
- **Psychology:** Curiosity, exclusivity, micro-commitment
- **Currently:** Available for A/B testing

---

### English Templates (In `/templates/`)

#### **1. Split Screen Design**
- **File:** `template-split-screen.html`
- **Style:** Left = Dark with benefits, Right = White with code
- **Colors:** Black/White with red accents
- **Features:**
  - Full-height split layout
  - Feature list with checkmarks
  - Live countdown timer
  - Professional corporate feel
- **Best For:** B2B offers, professional brands, desktop traffic
- **Mobile:** Stacks vertically

#### **2. Countdown Urgency**
- **File:** `template-countdown-urgency.html`
- **Style:** Dark black background with neon accents
- **Colors:** Black, Red, Yellow (urgency colors)
- **Features:**
  - Large animated countdown (Hours:Minutes:Seconds)
  - Flash sale badge with shake animation
  - Pulsing border effect
  - Warning message: "Expires when timer reaches zero"
- **Best For:** Flash sales, limited-time offers, FOMO campaigns
- **Psychology:** Extreme urgency, scarcity

#### **3. Social Proof Heavy**
- **File:** `template-social-proof.html`
- **Style:** Clean white design with trust elements
- **Colors:** White, Red accents, Blue badges
- **Features:**
  - 5-star rating display
  - Social stats (50K+ customers, 98% success)
  - Customer testimonial with verification
  - Real-time activity counter ("347 people used this in last hour")
  - Trust badges (Verified, Secure)
- **Best For:** New brands, building trust, skeptical audiences
- **Psychology:** Social proof, testimonials, credibility

#### **4. Brutalist Minimal**
- **File:** `template-brutalist-minimal.html`
- **Style:** Bold, raw, brutalist web design
- **Colors:** Black, White, Red highlight
- **Features:**
  - Courier monospace font throughout
  - Giant typography (120px heading)
  - Neo-brutalist button with 3D shadow effect
  - Square brackets [ ] design element
  - Minimal decoration, maximum impact
- **Best For:** Fashion brands, Gen-Z audience, creative/artistic brands
- **Psychology:** Bold, confident, anti-establishment

#### **5. Glassmorphism Premium**
- **File:** `template-glassmorphism.html`
- **Style:** Modern glass effect with blur
- **Colors:** Purple/Pink gradient background, white glass cards
- **Features:**
  - Frosted glass (backdrop-filter blur)
  - Floating animated circles background
  - Sparkle emoji animation
  - Premium luxury feel
  - Smooth transitions
- **Best For:** Luxury brands, premium products, high-ticket items
- **Psychology:** Exclusive, premium, modern

---

## 🎯 Template Selection Guide

### Choose by Brand Type:

**E-commerce / Retail:**
- Split Screen (professional)
- Social Proof (builds trust)
- Ultra-Minimal (fastest conversion)

**Fashion / Lifestyle:**
- Brutalist Minimal (trendy)
- Glassmorphism (premium)
- Modern Dark (sophisticated)

**Flash Sales / Daily Deals:**
- Countdown Urgency (FOMO)
- Reveal/Unlock (engagement)

**Luxury / High-End:**
- Glassmorphism (exclusive feel)
- Split Screen (professional)

**New/Unknown Brand:**
- Social Proof (builds credibility)
- Modern Dark (trustworthy)

---

## 🎨 Customization Guide

### Quick Color Changes

**For AliExpress (Red/Orange):**
```css
Primary: #ff4747
Secondary: #ff6b35
Hover: #e63939
```

**For Nike (Black/White/Orange):**
```css
Primary: #000000
Secondary: #ff6b00
Hover: #333333
```

**For iHerb (Green/Natural):**
```css
Primary: #22c55e
Secondary: #16a34a
Hover: #15803d
```

**For Generic/Neutral:**
```css
Primary: #667eea
Secondary: #764ba2
Hover: #5568d3
```

### How to Change Colors

1. Open template file
2. Find all instances of color codes
3. Replace with brand colors
4. Test on mobile and desktop

**Common places colors appear:**
- Background gradients
- Button backgrounds
- Border colors
- Text highlights
- Hover states
- Shadow colors

---

## 📊 A/B Testing Recommendations

### Test #1: Psychology Approach
- **Variant A:** Ultra-Minimal (direct)
- **Variant B:** Social Proof (trust)
- **Metric:** Conversion rate

### Test #2: Urgency Level
- **Variant A:** Countdown Urgency (high FOMO)
- **Variant B:** Reveal/Unlock (moderate engagement)
- **Metric:** Time on page + conversion

### Test #3: Design Style
- **Variant A:** Glassmorphism (modern)
- **Variant B:** Brutalist (bold)
- **Metric:** Bounce rate + conversion

### Test #4: Trust vs Speed
- **Variant A:** Social Proof (trust-heavy)
- **Variant B:** Split Screen (balanced)
- **Metric:** New vs returning visitors performance

---

## 🔧 Implementation Steps

### 1. Choose Template
Select based on:
- Brand personality
- Target audience
- Product type
- Campaign goal

### 2. Customize
- Update brand name
- Change colors to match brand
- Replace placeholder code
- Add affiliate URL
- Adjust discount percentage

### 3. Update CONFIG
```javascript
const CONFIG = {
    code: 'YOUR_CODE_HERE',
    url: 'https://your-affiliate-url.com',
    autoRedirect: true,
    delay: 1500
};
```

### 4. Test
- Desktop browsers (Chrome, Safari, Firefox)
- Mobile devices (iOS, Android)
- Copy functionality
- Redirect behavior
- Timer/animations

### 5. Deploy
- Commit to `dev` branch
- Test preview URL
- Merge to `main` when ready
- Monitor conversion rates

---

## 📱 Mobile Optimization

All templates are mobile-responsive with:
- ✅ Large touch targets (44px minimum)
- ✅ Readable font sizes (16px+ body text)
- ✅ Simplified layouts for small screens
- ✅ Fast loading (<3 seconds)
- ✅ Works without JavaScript (fallback)

**Mobile breakpoints:**
- `@media (max-width: 968px)` - Tablet
- `@media (max-width: 480px)` - Mobile

---

## ⚡ Performance Tips

### Keep It Fast
- ✅ Inline CSS (no external files)
- ✅ No images (use emojis/text)
- ✅ Minimal JavaScript
- ✅ No external libraries
- ✅ Single HTML file

### Target Metrics
- **Load Time:** <1 second
- **File Size:** <15KB
- **Lighthouse Score:** 90+

---

## 🎯 Conversion Optimization

### What Works:
✅ Large, clear discount amount
✅ Single clear CTA
✅ Immediate code visibility (or 1 click reveal)
✅ Auto-copy functionality
✅ Trust signals (verified, tested)
✅ Urgency (timer, limited time)
✅ Mobile-first design

### What Doesn't Work:
❌ Multiple CTAs
❌ Email capture before code
❌ Complex forms
❌ Too much text
❌ Slow animations
❌ Broken copy button
❌ Redirect to wrong page

---

## 📈 Success Metrics

Track these for each template:
- **Bounce Rate:** <40% is good
- **Time on Page:** 15-45 seconds ideal
- **Copy Rate:** % who click copy button
- **Conversion Rate:** % who visit merchant
- **Mobile vs Desktop:** Compare performance

---

## 🚀 Next Steps

1. **Review all templates** - Open each HTML file in browser
2. **Choose 2-3 for testing** - Pick different styles
3. **Customize for your brand** - Update colors, text, code
4. **Deploy to dev branch** - Test before going live
5. **Run A/B test** - Equal traffic for 48-72 hours
6. **Analyze results** - Pick winner
7. **Scale** - Use winning template for more campaigns

---

## 📞 Template Support

**File Location:**
- Portuguese: `/campaigns/aliexpress/`
- English: `/templates/`

**Documentation:**
- Main Plan: `PROJECT-PLAN.md`
- Setup: `SETUP-REPORT.md`
- Quick Start: `START-HERE.md`

---

**Created:** December 14, 2025
**Total Templates:** 8 (3 Portuguese + 5 English)
**All Mobile-Optimized:** ✅
**All Conversion-Focused:** ✅

