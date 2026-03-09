---
name: landing-page-builder
description: Automated landing page creation for Webflow. Builds conversion-optimized pages with hero sections, feature showcases, and SEO metadata. Use when creating product landing pages, marketing pages, or campaign destinations.
---

# Landing Page Builder

Creates high-converting landing pages in Webflow with hero sections, feature showcases, CTAs, and SEO optimization. Designed for rapid iteration from 1 hour+ to under 5 minutes.

## Prerequisites

- Webflow site created (can be blank)
- Webflow MCP server configured
- Access to Webflow Designer

---

## Step 1: Gather Requirements with asktheuser

**CRITICAL:** Use the `asktheuser` tool to collect ALL information upfront. Do NOT make assumptions about business content, features, headlines, or company information.

### Required Information

Use this exact prompt with asktheuser:

```
Please provide the following information for your landing page:

═══════════════════════════════════════════════════════
1. BUSINESS BASICS
═══════════════════════════════════════════════════════
   - Business/Product name:
   - Industry/Category:
   - Target audience:
   - Primary goal (signups, demos, purchases, etc.):

═══════════════════════════════════════════════════════
2. HERO SECTION
═══════════════════════════════════════════════════════
   - Main headline (your core value proposition):
   - Supporting subheadline:
   - Primary CTA button text:
   - Secondary CTA button text (optional):
   - Hero image description or URL:

═══════════════════════════════════════════════════════
3. FEATURES/VALUE PROPOSITIONS (provide exactly 6)
═══════════════════════════════════════════════════════
   For EACH of the 6 features, provide:
   
   Feature 1:
   - Title:
   - Description (1-2 sentences):
   - Icon/visual suggestion:
   
   Feature 2:
   - Title:
   - Description:
   - Icon/visual suggestion:
   
   Feature 3:
   - Title:
   - Description:
   - Icon/visual suggestion:
   
   Feature 4:
   - Title:
   - Description:
   - Icon/visual suggestion:
   
   Feature 5:
   - Title:
   - Description:
   - Icon/visual suggestion:
   
   Feature 6:
   - Title:
   - Description:
   - Icon/visual suggestion:

═══════════════════════════════════════════════════════
4. SOCIAL PROOF (optional but recommended)
═══════════════════════════════════════════════════════
   - Customer testimonials (quote, name, company):
   - Company logos:
   - Statistics/metrics (e.g., "10,000+ customers"):
   - Trust badges (certifications, awards):

═══════════════════════════════════════════════════════
5. SEO & METADATA
═══════════════════════════════════════════════════════
   - Page title (50-60 characters):
   - Meta description (150-160 characters):
   - Primary keywords (3-5):
   - Target location/market:
   - URL slug:

═══════════════════════════════════════════════════════
6. DESIGN PREFERENCES
═══════════════════════════════════════════════════════
   - Brand colors (primary, secondary, accent):
   - Style direction (modern, minimal, bold, etc.):
   - Reference websites (optional):

═══════════════════════════════════════════════════════
7. WEBFLOW SPECIFICS
═══════════════════════════════════════════════════════
   - Webflow site name or ID:
   - Page name/location:
   - Using CMS collections? (yes/no)
```

**DO NOT PROCEED** until you have complete answers to all required sections (1-7).

---

## Step 2: Plan Page Structure

Based on gathered requirements, plan this standard landing page layout:

```
┌─────────────────────────────────────────────────────┐
│ HERO SECTION (full-width or contained)             │
├──────────────────────┬──────────────────────────────┤
│ Left Column (60%)    │ Right Column (40%)           │
│ • H1 Headline        │ • Hero Image                 │
│ • H2 Subheadline     │                              │
│ • Primary CTA        │                              │
│ • Secondary CTA      │                              │
└──────────────────────┴──────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│ FEATURES SECTION (grid layout)                      │
├────────────┬────────────┬────────────────────────────┤
│ Feature 1  │ Feature 2  │ Feature 3                 │
│ [Icon]     │ [Icon]     │ [Icon]                    │
│ Title      │ Title      │ Title                     │
│ Desc       │ Desc       │ Desc                      │
├────────────┼────────────┼────────────────────────────┤
│ Feature 4  │ Feature 5  │ Feature 6                 │
│ [Icon]     │ [Icon]     │ [Icon]                    │
│ Title      │ Title      │ Title                     │
│ Desc       │ Desc       │ Desc                      │
└────────────┴────────────┴────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│ SOCIAL PROOF SECTION (if provided)                  │
│ • Testimonials / Logos / Stats / Trust Badges       │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│ FINAL CTA SECTION (centered)                        │
│ • Compelling headline                               │
│ • CTA button                                        │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│ FOOTER                                              │
│ • Links / Copyright / Contact                       │
└─────────────────────────────────────────────────────┘
```

**Responsive Breakpoints:**
- Desktop: 3 columns × 2 rows (features)
- Tablet: 2 columns × 3 rows
- Mobile: 1 column × 6 rows (stacked)

---

## Step 3: Build in Webflow

### 3.1 Create/Access Page

```
1. Access Webflow site via MCP
2. Create new page or select existing page
3. Set page settings:
   - Title: [from requirements]
   - Slug: [from requirements]
```

### 3.2 Set SEO Metadata FIRST

```
In Page Settings:
- Meta Title: [50-60 chars from requirements]
- Meta Description: [150-160 chars from requirements]
- OG Title: [same as meta title]
- OG Description: [same as meta description]
- OG Image: [1200×630px image URL]
```

### 3.3 Build Hero Section

```
Structure:
<section class="section-hero">
  <div class="container">
    <div class="hero-grid">
      <div class="hero-content">
        <h1>[Main headline]</h1>
        <h2>[Subheadline]</h2>
        <div class="cta-buttons">
          <a class="btn-primary">[Primary CTA]</a>
          <a class="btn-secondary">[Secondary CTA]</a>
        </div>
      </div>
      <div class="hero-image">
        <img src="..." alt="[descriptive alt text]">
      </div>
    </div>
  </div>
</section>
```

**Styling Guidelines:**
- H1: 48-56px desktop, 32-40px mobile
- H2: 24-32px desktop, 18-24px mobile
- Primary CTA: High contrast, padding 16px 32px
- Hero image: Relevant to business, optimized

### 3.4 Build Features Grid

```
Structure:
<section class="section-features">
  <div class="container">
    <div class="features-grid">
      <!-- Repeat 6 times -->
      <div class="feature-card">
        <div class="feature-icon">[Icon]</div>
        <h3 class="feature-title">[Title]</h3>
        <p class="feature-description">[Description]</p>
      </div>
    </div>
  </div>
</section>
```

**Grid Styling:**
```
Desktop: display: grid; grid-template-columns: repeat(3, 1fr); gap: 2rem;
Tablet:  grid-template-columns: repeat(2, 1fr); gap: 1.5rem;
Mobile:  grid-template-columns: 1fr; gap: 1rem;
```

**Card Styling:**
- Icon: 48-64px, centered or left-aligned
- Title: H3, 20-24px, bold
- Description: 16-18px, line-height 1.6
- Consistent spacing: padding 2rem per card

### 3.5 Add Social Proof (if provided)

```
<section class="section-social-proof">
  <div class="container">
    <!-- Testimonials -->
    <div class="testimonials">
      <blockquote>
        <p>[Quote]</p>
        <cite>[Name, Company]</cite>
      </blockquote>
    </div>
    
    <!-- Stats -->
    <div class="stats">
      <div class="stat">
        <div class="stat-number">[Number]</div>
        <div class="stat-label">[Label]</div>
      </div>
    </div>
  </div>
</section>
```

### 3.6 Build Final CTA

```
<section class="section-cta">
  <div class="container-small">
    <h2>[Compelling headline]</h2>
    <a class="btn-primary-large">[CTA text]</a>
  </div>
</section>
```

### 3.7 Add Footer

```
<footer class="footer">
  <div class="container">
    <div class="footer-content">
      <div class="footer-links">[Links]</div>
      <div class="footer-copyright">© [Year] [Company]</div>
    </div>
  </div>
</footer>
```

---

## Step 4: Apply Styling & Optimization

### 4.1 Typography Scale

```
H1: 48-56px (desktop), 32-40px (mobile)
H2: 36-40px (desktop), 24-28px (mobile)
H3: 24-28px (desktop), 20-24px (mobile)
Body: 16-18px
Small: 14px
```

### 4.2 Spacing System

Use consistent spacing:
```
xs:  0.5rem (8px)  - Tight spacing
sm:  1rem   (16px) - Default spacing
md:  1.5rem (24px) - Medium spacing
lg:  2rem   (32px) - Large spacing
xl:  3rem   (48px) - Section spacing
xxl: 4rem   (64px) - Major sections
```

### 4.3 Color Application

```
Primary color: CTAs, links, accents
Secondary color: Backgrounds, highlights
Accent color: Icons, badges
Text: Dark gray (#2C3E50) on white
Background: White or light gray (#F8F9FA)
```

**CTA Button Requirements:**
- High contrast with background
- Minimum height: 48px (mobile touch-friendly)
- Clear hover state
- Action verbs ("Get Started", "Book Now", not "Submit")

### 4.4 Image Optimization

```
- Format: WebP (fallback to JPG)
- Hero image: Max 1920px wide
- Feature icons: 48-64px (SVG preferred)
- Compress before upload (TinyPNG, ImageOptim)
- All images MUST have descriptive alt text
```

### 4.5 Mobile Responsiveness

Test and adjust at each breakpoint:
```
Desktop: 1280px+
Tablet:  768px - 1279px
Mobile:  < 768px
```

**Mobile Adjustments:**
- Stack hero columns (image below text)
- Reduce font sizes
- Full-width CTAs
- Increase touch targets (min 44×44px)
- Check image scaling

---

## Step 5: Quality Checklist

Before publishing, verify:

### Content ✓
- [ ] All text from requirements is present
- [ ] No placeholder text remains
- [ ] Headings follow hierarchy (H1 → H2 → H3)
- [ ] CTAs are clear and actionable
- [ ] All links work

### SEO ✓
- [ ] One H1 per page (hero headline)
- [ ] Meta title is 50-60 characters
- [ ] Meta description is 150-160 characters
- [ ] All images have alt text
- [ ] URL slug is clean and keyword-rich
- [ ] OG tags set for social sharing

### Design ✓
- [ ] Brand colors applied correctly
- [ ] Typography is readable (size and contrast)
- [ ] Consistent spacing throughout
- [ ] Visual hierarchy is clear
- [ ] Images are optimized

### Technical ✓
- [ ] Mobile responsive (test all breakpoints)
- [ ] CTAs are touch-friendly (min 44×44px)
- [ ] No horizontal scrolling
- [ ] Page loads in < 3 seconds
- [ ] Forms connected (if applicable)

### Conversion ✓
- [ ] Primary CTA above the fold (visible without scrolling)
- [ ] At least 2 CTA placements (hero + final section)
- [ ] Social proof included (if available)
- [ ] Clear value proposition in hero
- [ ] Benefits are customer-focused

---

## Step 6: Publish

```
1. Save all changes in Webflow
2. Preview page on staging (if available)
3. Test on actual mobile device
4. Publish to production
5. Verify live URL works
6. Test all CTAs on live site
```

---

## Design Best Practices

### Hero Section
✅ **DO:**
- Clear value proposition in 5-10 words
- Primary CTA visible without scrolling
- Use relevant, high-quality hero image
- Action-oriented CTA text

❌ **DON'T:**
- Vague headlines ("Welcome to our site")
- Generic stock photos (handshakes, business people)
- Multiple competing CTAs
- Cluttered layout

### Features Section
✅ **DO:**
- Use consistent icon style/size
- Keep descriptions concise (1-2 sentences)
- Focus on benefits, not just features
- Balance visual weight across all 6

❌ **DON'T:**
- Mix icon styles (outline + solid)
- Write lengthy paragraphs
- Use jargon without explanation
- Overcrowd with too much text

### CTAs
✅ **DO:**
- Use action verbs ("Get Started", "Book Demo", "Try Free")
- Make buttons stand out (high contrast)
- Repeat CTA (hero + bottom of page minimum)
- Keep button text short (2-4 words)

❌ **DON'T:**
- Use passive text ("Submit", "Click Here")
- Hide CTAs in navigation
- Use too many CTA options
- Make CTAs look like ads

---

## Common Pitfalls to Avoid

1. **Information Overload**
   - Problem: Too many sections, too much text
   - Solution: One page, one goal. Keep it focused.

2. **Weak Headlines**
   - Problem: "Welcome" or vague statements
   - Solution: Clear benefit in the headline

3. **Hidden CTAs**
   - Problem: CTA below fold or low contrast
   - Solution: Primary CTA above fold, high contrast

4. **Slow Loading**
   - Problem: Unoptimized images
   - Solution: Compress images before upload, use WebP

5. **Broken Mobile Experience**
   - Problem: Fixed widths, tiny text, overlapping elements
   - Solution: Test every breakpoint, use relative units

6. **Missing Alt Text**
   - Problem: Images without descriptions
   - Solution: Add descriptive alt text to every image

7. **Inconsistent Spacing**
   - Problem: Random gaps and padding
   - Solution: Use spacing system (8px, 16px, 24px, 32px)

---

## Speed Optimization Tips

To achieve sub-5-minute builds:

1. **Get all requirements upfront** - Use asktheuser once comprehensively
2. **Use Webflow symbols** - Create reusable button, card, section symbols
3. **Build in order** - Top to bottom, don't jump around
4. **Apply styles in batches** - All headings at once, all cards at once
5. **Use class naming** - Consistent naming speeds up styling
6. **Test as you build** - Check mobile after each section
7. **Don't over-polish** - Get it working, then refine if needed

**Workflow:**
1. Requirements (2 min via asktheuser)
2. Build structure (2 min - sections, content)
3. Style & responsive (1 min - apply design)
4. Total: 5 minutes ✓

---

## Bulk SEO Management

For reviewing/updating meta descriptions across multiple pages:

### Process:
```
1. List all pages in Webflow site
2. Export current meta descriptions
3. Review for:
   - Length (150-160 characters)
   - Keyword inclusion
   - Uniqueness (no duplicates)
   - Call-to-action inclusion
   - Compelling copy
4. Update via:
   - Webflow CMS bulk edit (for collection pages)
   - Webflow API (for multiple static pages)
   - Manual review with checklist
5. Publish changes
6. Verify in browser
```

### SEO Audit Checklist:
- [ ] Every page has unique meta title
- [ ] Every page has unique meta description
- [ ] Titles include target keywords
- [ ] Descriptions include CTA
- [ ] No duplicate content
- [ ] All images have alt text
- [ ] Proper heading hierarchy
- [ ] Internal links are working

---

## Advanced: Template System

For recurring landing pages, set up templates:

### One-Time Setup:
```
1. Build master landing page with best structure
2. Create Webflow symbols for:
   - Header/navigation
   - Hero section container
   - Feature card component
   - CTA section
   - Footer
3. Save as template or duplicate page
```

### For Each New Landing Page:
```
1. Duplicate template page
2. Update content only:
   - Hero headline/subheadline
   - 6 feature cards (text + icons)
   - CTA text
   - SEO metadata
3. Publish
4. Time: 2-3 minutes ✓
```

---

## Troubleshooting

### Problem: Requirements gathering is incomplete
**Solution:** Use the exact asktheuser prompt provided in Step 1. Don't skip sections.

### Problem: Build taking too long (>5 minutes)
**Causes:** Incomplete requirements, complex customizations, first-time setup
**Solutions:**
- Get ALL requirements upfront
- Use simpler layouts initially
- Create templates for future speed
- Focus on content first, polish later

### Problem: Page not mobile responsive
**Solutions:**
- Check all breakpoints in Webflow designer
- Use percentage widths instead of fixed pixels
- Test flex/grid settings on tablet/mobile
- Stack elements vertically on mobile

### Problem: SEO metadata not appearing
**Solutions:**
- Check Page Settings (gear icon), not Project Settings
- Verify meta tags in published page source
- Clear browser cache
- Check Webflow publish status

### Problem: CTA not prominent enough
**Solutions:**
- Increase button size (min 48×48px mobile)
- Higher color contrast
- Add whitespace around button
- Place above the fold
- Use action verbs

### Problem: Images loading slowly
**Solutions:**
- Compress images before upload
- Use WebP format with JPG fallback
- Proper image dimensions (don't upload 4K for hero)
- Enable Webflow's lazy loading

---

## Quick Reference Checklists

### Pre-Build Checklist
- [ ] asktheuser completed with all 7 sections
- [ ] All 6 features defined
- [ ] SEO metadata prepared
- [ ] Brand colors documented
- [ ] Webflow site access confirmed

### Build Checklist
- [ ] Page created/accessed
- [ ] SEO settings applied
- [ ] Hero section built
- [ ] Features grid created (6 items)
- [ ] Social proof added (if provided)
- [ ] Final CTA section built
- [ ] Footer added

### Pre-Publish Checklist
- [ ] All content present
- [ ] No placeholder text
- [ ] All images have alt text
- [ ] Mobile responsive tested
- [ ] CTAs work
- [ ] Page loads fast
- [ ] SEO complete

---

## Example: Complete Requirements

Here's an example of well-prepared requirements for a London cleaning service:

**Business:** Sparkle & Shine London (home cleaning)
**Hero Headline:** "Your Time is Precious. Let Us Handle the Cleaning."
**Subheadline:** "Professional home cleaning services across London. Eco-friendly products, vetted cleaners, and a spotless guarantee."
**Primary CTA:** "Book Your First Clean"

**6 Features:**
1. Fully Vetted Cleaners - Background-checked, insured professionals
2. Eco-Friendly Products - Non-toxic, safe for family and pets
3. Flexible Scheduling - Weekly, fortnightly, or one-off cleans
4. Satisfaction Guarantee - We'll return within 24 hours or you don't pay
5. Same-Day Availability - Book before noon for same-day service
6. Transparent Pricing - Instant online quote, no hidden fees

**SEO:**
- Title: "Professional Home Cleaning Services London | Sparkle & Shine"
- Description: "Top-rated home cleaning service in London. Vetted cleaners, eco-friendly products, flexible scheduling. Same-day availability. Book today!"

This level of detail enables 5-minute builds.

---

## Success Criteria

A successful landing page build should achieve:

| Metric | Target |
|--------|--------|
| Build time | < 5 minutes |
| Page load | < 3 seconds |
| Mobile responsive | 100% |
| SEO metadata | Complete |
| CTA visibility | Above fold + footer |
| Quality | Ready to publish |

---

## Final Notes

**Remember:**
1. ✅ Always use asktheuser - never assume business content
2. ✅ Get complete requirements before building
3. ✅ Follow the standard structure (hero + 6 features + CTA)
4. ✅ Test mobile responsiveness at each breakpoint
5. ✅ Complete SEO metadata is non-negotiable
6. ✅ Speed comes from preparation, not rushing

**The goal:** Transform landing page creation from a 1-hour frustrating process into a streamlined 5-minute workflow.
