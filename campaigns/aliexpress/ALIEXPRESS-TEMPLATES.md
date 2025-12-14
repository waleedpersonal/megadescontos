# 🎨 AliExpress Landing Page Templates

**Brand:** AliExpress  
**Colors:** Red (#ff4747), Orange (#ff6b35)  
**Total Templates:** 13 (3 Portuguese + 10 English)

---

## 📁 Template Inventory

### ✅ Portuguese Templates (Original)

| # | File | Type | Language | Status |
|---|------|------|----------|--------|
| 1 | `variant-a.html` | Code | Portuguese | ✅ LIVE |
| 2 | `variant-b.html` | Link | Portuguese | Ready |
| 3 | `variant-c.html` | Code | Portuguese | Ready |

---

### ✅ English Templates - CODE VERSIONS

| # | File | Design Style | Best For |
|---|------|--------------|----------|
| 4 | `split-screen-code.html` | Professional Split | Desktop, B2B |
| 5 | `countdown-code.html` | Dark Urgency | Flash Sales, FOMO |
| 6 | `social-proof-code.html` | Trust Heavy | New brands, Skeptical audience |
| 7 | `brutalist-code.html` | Bold Minimal | Fashion, Gen-Z |
| 8 | `glassmorphism-code.html` | Premium Frosted Glass | Luxury products |

---

### ✅ English Templates - LINK-ONLY VERSIONS

| # | File | Design Style | Best For |
|---|------|--------------|----------|
| 9 | `split-screen-link.html` | Professional Split | Desktop, B2B |
| 10 | `countdown-link.html` | Dark Urgency | Flash Sales, FOMO |
| 11 | `social-proof-link.html` | Trust Heavy | New brands, Skeptical audience |
| 12 | `brutalist-link.html` | Bold Minimal | Fashion, Gen-Z |
| 13 | `glassmorphism-link.html` | Premium Frosted Glass | Luxury products |

---

## 🎯 Template Details

### 1. Split Screen Design

**CODE VERSION:** `split-screen-code.html`
- Left: Dark with feature list
- Right: White with code box
- Timer: 24-hour countdown
- **Copy button** + auto-redirect
- Professional feel

**LINK VERSION:** `split-screen-link.html`
- Left: Dark with feature list
- Right: White with discount badge
- Timer: 24-hour countdown
- **"Activate Deal" button** (no code)
- Text: "No code needed - auto-applied"

---

### 2. Countdown Urgency

**CODE VERSION:** `countdown-code.html`
- Black background
- Large countdown timer (Hours:Minutes:Seconds)
- Flash sale badge with shake animation
- **Copy code button**
- Warning: "Expires when timer reaches zero"

**LINK VERSION:** `countdown-link.html`
- Black background
- Large countdown timer (Hours:Minutes:Seconds)
- Flash sale badge with shake animation
- **"Activate Deal" button**
- Text: "No code needed - auto-applied at checkout"

---

### 3. Social Proof Heavy

**CODE VERSION:** `social-proof-code.html`
- White clean design
- Trust badges: Verified, Secure
- 5-star rating
- Social stats: 50K+ customers, 98% success
- Customer testimonial
- **Copy code button**
- Live activity counter

**LINK VERSION:** `social-proof-link.html`
- White clean design
- Trust badges: Verified, Secure
- 5-star rating
- Social stats: 50K+ customers, 98% success
- Customer testimonial
- **"Get Deal" button**
- Text: "Auto-applied through exclusive link"

---

### 4. Brutalist Minimal

**CODE VERSION:** `brutalist-code.html`
- White background
- Courier monospace font
- Giant 120px typography
- Red code box with black border
- 3D button shadow effect (neo-brutalist)
- **Copy code button**
- Bold, raw design

**LINK VERSION:** `brutalist-link.html`
- White background
- Courier monospace font
- Giant 120px typography
- Red deal box with black border
- 3D button shadow effect
- **"Get Deal" button**
- Text: "Auto-applied automatically"

---

### 5. Glassmorphism Premium

**CODE VERSION:** `glassmorphism-code.html`
- Red/Orange gradient background
- Frosted glass (backdrop-filter blur)
- Floating animated circles
- Sparkle emoji animation
- **Copy code button**
- Premium luxury feel

**LINK VERSION:** `glassmorphism-link.html`
- Red/Orange gradient background
- Frosted glass (backdrop-filter blur)
- Floating animated circles
- Sparkle emoji animation
- **"Get Deal" button**
- Text: "No code needed - exclusive link"

---

## 🔄 Code vs Link-Only: Key Differences

### CODE VERSION Features:
```html
✅ Coupon code displayed (e.g., "SAVE70NOW")
✅ Dashed border code box
✅ "Copy Code" button
✅ One-click clipboard copy
✅ "✓ Verified Today" badge
✅ Auto-opens merchant after copy
```

### LINK-ONLY VERSION Features:
```html
✅ No coupon code shown
✅ Discount badge (e.g., "UP TO 70% OFF")
✅ "Activate Deal" or "Get Deal" button
✅ Direct redirect to merchant
✅ "No code needed" messaging
✅ "Auto-applied at checkout" text
```

---

## ⚙️ Configuration

### For CODE Versions:
```javascript
const CONFIG = {
    code: 'SAVE70NOW',              // Your coupon code
    url: 'https://www.aliexpress.com',  // Your affiliate link
    autoRedirect: true,              // Open store after copy
    delay: 1500                      // Delay before opening (ms)
};
```

### For LINK-ONLY Versions:
```javascript
const CONFIG = {
    url: 'https://www.aliexpress.com'  // Your affiliate link only
};
```

---

## 📊 When to Use Each Type

### Use CODE VERSION When:
- ✅ You have actual coupon codes
- ✅ Merchant requires code at checkout
- ✅ You want to track code usage
- ✅ Code provides better discount than link
- ✅ Testing coupon vs link conversion

### Use LINK-ONLY VERSION When:
- ✅ No coupon code available
- ✅ Affiliate program is link-only
- ✅ Discount auto-applies through link
- ✅ Want faster user flow (one click less)
- ✅ A/B testing simplified flow

---

## 🎨 Brand Colors (AliExpress)

```css
/* Primary Colors */
--aliexpress-red: #ff4747;
--aliexpress-orange: #ff6b35;
--aliexpress-red-dark: #e63939;

/* Gradients */
background: linear-gradient(135deg, #ff4747 0%, #ff6b35 100%);

/* Success States */
--success-green: #22c55e;

/* Urgency */
--warning-yellow: #ffd93d;
--warning-orange: #d97706;
```

---

## 🚀 Deployment Strategy

### Phase 1: Initial Launch
1. Start with **1 Portuguese template** (variant-a - already live)
2. Run for 48 hours
3. Collect baseline metrics

### Phase 2: Portuguese A/B Test
1. Test `variant-a` vs `variant-c` (reveal style)
2. Split traffic 50/50
3. Measure conversion rates
4. Pick winner

### Phase 3: English Expansion
1. Deploy winning style in English
2. Test **CODE vs LINK-ONLY** versions
3. Measure which converts better
4. Scale winner

### Phase 4: Style Testing
1. Test different design styles:
   - Split Screen vs Countdown
   - Social Proof vs Brutalist
   - Glassmorphism vs Minimal
2. Run each for minimum 72 hours
3. Scale top 2 performers

---

## 📈 A/B Testing Matrix

| Test | Variant A | Variant B | Measure |
|------|-----------|-----------|---------|
| **Portuguese Style** | variant-a (minimal) | variant-c (reveal) | Conversion rate |
| **Code Type** | CODE version | LINK-ONLY version | Click-through rate |
| **Design Style** | Split Screen | Countdown | Engagement time |
| **Trust Factor** | Social Proof | Brutalist | Bounce rate |
| **Premium Feel** | Glassmorphism | Minimal | Average order value |

---

## 🎯 Recommended Starting Lineup

### High-Intent Keywords (Coupon searches):
→ Use **CODE versions**
- split-screen-code.html
- social-proof-code.html

### General Deal Keywords:
→ Use **LINK-ONLY versions**
- countdown-link.html
- glassmorphism-link.html

### Mobile Traffic:
→ Use **Minimal designs**
- variant-a.html (Portuguese)
- brutalist-link.html (English)

### Desktop Traffic:
→ Use **Rich designs**
- split-screen-code.html
- social-proof-code.html

---

## 📱 Mobile Optimization

All templates include:
- ✅ Responsive breakpoints (@media queries)
- ✅ Large touch targets (44px minimum)
- ✅ Readable fonts (16px+ body)
- ✅ Simplified mobile layouts
- ✅ Fast loading (<3 seconds)
- ✅ Works without JavaScript

**Test on:**
- iPhone (Safari)
- Android (Chrome)
- Tablet (iPad)

---

## 🔧 Quick Customization Guide

### Change Discount Percentage:
Search for: `70%`
Replace with: `50%`, `60%`, etc.

### Change Coupon Code:
1. Find `CONFIG` object in JavaScript
2. Update `code:` value
3. Update code display in HTML (search for code text)

### Change Affiliate URL:
1. Find `CONFIG` object
2. Update `url:` value
3. Test redirect works

### Change Timer Duration:
Look for: `timeLeft = 24 * 60 * 60` (24 hours)
Change to: `4 * 60 * 60` (4 hours)

---

## ✅ Pre-Launch Checklist

Before launching any template:

**Configuration**
- [ ] Update CONFIG with your affiliate URL
- [ ] Update code (if using CODE version)
- [ ] Set correct discount percentage
- [ ] Test timer duration

**Testing**
- [ ] Copy button works (CODE versions)
- [ ] Redirect works to correct URL
- [ ] Mobile responsive (test on real device)
- [ ] Timer counts down correctly
- [ ] All text is readable

**Tracking**
- [ ] Add Google Analytics code (optional)
- [ ] Add Facebook Pixel (optional)
- [ ] Test conversion tracking

**Deployment**
- [ ] Test in dev branch first
- [ ] Verify preview URL works
- [ ] Merge to main
- [ ] Verify production URL
- [ ] Update CAMPAIGNS.md with details

---

## 📞 File Locations

```
/campaigns/aliexpress/
├── README (this file)
├── config.json (campaign configuration)
├── variant-a.html (Portuguese - Minimal Red - CODE)
├── variant-b.html (Portuguese - Modern Dark - LINK)
├── variant-c.html (Portuguese - Reveal - CODE - Updated colors!)
├── split-screen-code.html
├── split-screen-link.html
├── countdown-code.html
├── countdown-link.html
├── social-proof-code.html
├── social-proof-link.html
├── brutalist-code.html
├── brutalist-link.html
├── glassmorphism-code.html
└── glassmorphism-link.html
```

---

## 🎊 Summary

✅ **13 Total Templates** ready to deploy  
✅ **5 Design Styles** for different audiences  
✅ **CODE + LINK versions** for maximum flexibility  
✅ **AliExpress branded** with proper colors  
✅ **Mobile-optimized** for all devices  
✅ **Conversion-focused** design principles  

**You're ready to launch and test!** 🚀

---

**Last Updated:** December 14, 2025  
**Status:** ✅ All templates complete and ready to deploy

