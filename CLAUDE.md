# GLP Clinic Website - Project Guidelines

## Design Philosophy
Modern, minimalist, hipster-inspired aesthetic with a focus on readability and user comfort. The design prioritizes clean lines, ample whitespace, and subtle sophistication without overwhelming visual elements.

## Color Palette

### Primary Colors
- **Background**: `#fafafa` - Warm off-white (easier on eyes than pure white)
- **Text Primary**: `#2d2d2d` - Soft charcoal (gentler than pure black)
- **Text Secondary**: `#777` - Light gray for supporting text
- **Accent**: `#6366f1` - Indigo (used sparingly for highlights)

### Button Colors
- **Primary Button Background**: `#1a1a1a` - Near black
- **Primary Button Text**: `#ffffff` - Pure white
- **Button Hover**: `#333` - Lighter black
- **Button Shadow**: `rgba(0, 0, 0, 0.15)` - Subtle depth

### Borders & Dividers
- **Border Color**: `rgba(45, 45, 45, 0.06)` - Very subtle borders
- **Divider**: `#e5e5e5` - Light gray for form underlines
- **Input Underline**: `#ddd` → `#e5e5e5` (even softer)

## Typography

### Font Stack
```css
font-family: -apple-system, BlinkMacSystemFont, 'Inter', 'Helvetica Neue', sans-serif;
```

### Font Weights
- **Light**: 300 - Body text
- **Regular**: 400 - Default, headers
- **Medium**: 500 - Emphasis
- **Semibold**: 600 - Buttons, strong emphasis

### Font Sizes
- **Body**: 15px-16px
- **Small**: 13px-14px (labels, captions)
- **Large**: 18px-20px (headlines)
- **Hero**: 48px-64px (main headline)

### Line Heights
- **Body Text**: 1.6-1.7
- **Headers**: 1.2-1.3
- **Compact**: 1.4 (navigation, buttons)

## Forms & Inputs

### Input Field Styling
```css
/* Text Inputs */
- Background: transparent
- Border: none (use bottom border only)
- Border-bottom: 1px solid #e5e5e5
- Padding: 8px 0
- Font-size: 15px
- Color: #2d2d2d
- Transition: border-color 0.3s ease

/* Focus State */
- Border-bottom: 2px solid #1a1a1a
- Outline: none

/* Labels */
- Font-size: 13px
- Color: #aaa
- Text-transform: uppercase
- Letter-spacing: 0.5px
- Font-weight: 500
```

### Form Layout
- **Field Spacing**: 24px between form groups
- **Label Position**: Above input field
- **Helper Text**: Below input, 12px font, #999 color
- **Error Messages**: #e74c3c color, 12px font
- **Success Messages**: #27ae60 color, 12px font

### Buttons in Forms
```css
/* Submit Button */
- Background: #1a1a1a
- Color: white
- Padding: 14px 32px
- Border-radius: 8px
- Font-size: 16px
- Font-weight: 600
- No border
- Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15)
- Hover: background #333, transform translateY(-2px)

/* Secondary Button */
- Same as primary but consider ghost style:
- Background: transparent
- Color: #1a1a1a
- Border: 1px solid #1a1a1a
- Hover: background #1a1a1a, color white
```

## Layout Principles

### Spacing System
```css
--space-xs: 8px
--space-sm: 16px
--space-md: 24px
--space-lg: 32px
--space-xl: 48px
--space-2xl: 64px
--space-3xl: 96px
```

### Container Widths
- **Max Width**: 1200px
- **Content Width**: 720px (for text-heavy sections)
- **Form Width**: 400-500px
- **Padding**: 16px mobile, 24px tablet, 32px desktop

### Grid System
- **Desktop**: 12 columns
- **Tablet**: 8 columns
- **Mobile**: 4 columns
- **Gutter**: 24px

## Component Patterns

### Navigation Header
- **Height**: 72px
- **Background**: rgba(250, 250, 250, 0.95) with backdrop blur
- **Position**: Fixed top
- **Shadow**: None (use subtle border instead)
- **Logo**: 20px font size, font-weight 400

### Cards
- **Background**: White or very light gray
- **Border**: None (use shadow for depth)
- **Shadow**: 0 2px 4px rgba(0, 0, 0, 0.05)
- **Padding**: 24px-32px
- **Border-radius**: 8px-12px

### Hero Sections
- **Min Height**: 60vh
- **Text Align**: Center
- **Headline Size**: 48px mobile, 64px desktop
- **Subtitle Size**: 18px mobile, 20px desktop
- **CTA Button**: Prominent, centered

### Footer
- **Background**: Same as body (#fafafa)
- **Border Top**: 1px solid rgba(45, 45, 45, 0.06)
- **Padding**: 48px 0
- **Text Color**: #777
- **Link Color**: #2d2d2d

## Animation & Interactions

### Transitions
- **Default Duration**: 0.2s - 0.3s
- **Easing**: ease or ease-out
- **Properties**: Limit to opacity, transform, background-color
- **Hover Effects**: Subtle - translateY(-1px) or (-2px)

### Loading States
- **Skeleton Screens**: Preferred over spinners
- **Placeholder Color**: #f0f0f0
- **Animation**: Subtle pulse or shimmer

### Feedback
- **Success**: Green accent (#27ae60)
- **Error**: Red accent (#e74c3c)
- **Warning**: Orange accent (#f39c12)
- **Info**: Blue accent (#3498db)

## Responsive Design

### Breakpoints
```css
- Mobile: 0-640px
- Tablet: 641px-1024px
- Desktop: 1025px+
- Large Desktop: 1440px+
```

### Mobile-First Approach
- Start with mobile design
- Progressive enhancement
- Touch-friendly tap targets (min 44px)
- Thumb-reachable navigation

## Best Practices

### Performance
- Lazy load images below the fold
- Use system fonts when possible
- Minimize custom font weights
- Optimize images (WebP with fallbacks)
- Minimize CSS animations on mobile

### Accessibility
- **Color Contrast**: Minimum 4.5:1 for body text
- **Focus Indicators**: Visible but subtle
- **Alt Text**: Descriptive for all images
- **ARIA Labels**: For interactive elements
- **Keyboard Navigation**: Full support

### Code Style
- Use CSS variables for all colors
- Component-based CSS organization
- Mobile-first media queries
- Consistent naming convention (BEM or similar)
- Comment major sections

## Form Implementation Examples

### Simple Contact Form
```html
<form class="contact-form">
  <div class="form-group">
    <label for="name">Name</label>
    <input type="text" id="name" required>
    <div class="underline"></div>
  </div>
  
  <div class="form-group">
    <label for="email">Email</label>
    <input type="email" id="email" required>
    <div class="underline"></div>
  </div>
  
  <div class="form-group">
    <label for="message">Message</label>
    <textarea id="message" rows="4" required></textarea>
    <div class="underline"></div>
  </div>
  
  <button type="submit" class="btn-primary">Send Message</button>
</form>
```

### Styling
```css
.form-group {
  position: relative;
  margin-bottom: 24px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 8px 0;
  font-size: 15px;
  color: #2d2d2d;
  background: transparent;
  border: none;
  border-bottom: 1px solid #e5e5e5;
  transition: border-color 0.3s;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-bottom-color: #1a1a1a;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  font-size: 13px;
  color: #aaa;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  font-weight: 500;
}
```

## Project-Specific Notes

### GLP Clinic Context
- Medical/healthcare focus requires extra clarity
- Trust and professionalism through minimalism
- Avoid overly playful elements
- Maintain HIPAA compliance considerations
- Clear CTAs for appointment booking
- Accessible to all age groups

### Content Guidelines
- Clear, jargon-free language
- Short paragraphs (3-4 lines max)
- Bullet points for benefits/features
- Prominent contact information
- Trust signals (certifications, testimonials)

## File Structure
```
glp-clinic-website/
├── fusion.html (DEFAULT - PRIMARY DEVELOPMENT FILE)
├── modern.html (archived - original GLP Clinic design)
├── caliber.html (variant - pure minimalist)
├── meridian.html (variant - warm medical)
├── index-variant.html (variant - data-driven)
├── tempo.html (variant - soft modern)
├── variants.html (comparison page)
├── css/
│   └── (component styles)
├── js/
│   └── (minimal interactions)
└── assets/
    └── (images, icons)
```

## PRIMARY DEVELOPMENT FILE: fusion.html
**This is the FINAL approved design - DO NOT MODIFY WITHOUT EXPLICIT USER PERMISSION**
- Brand: Cadence Health LLC
- Tagline: "Board-Certified Physicians. Evidence-Based Results. At Your Cadence."
- Design: Premium medical practice with extensive physician credentials
- Messaging: Evidence-based medicine with detailed institutional affiliations
- Pricing: Premium positioning ($249 initial, $199 follow-up)
- Colors: Pure white background, black primary
- Status: **LOCKED FOR PRODUCTION** - Commit 8110a79 (Sept 4, 2025)

⚠️ **CRITICAL: This file is now PRODUCTION-READY and should NOT be modified without explicit user approval**

## Final Layout Structure

### Navigation (6 Tabs)
1. **Overview** - Core value propositions with rhythm indicator
2. **Science** - "Profound Change, Expertly Monitored" education
3. **Method** - The 3-step Tempo approach
4. **Pricing** - Simple $149/month transparent pricing
5. **FAQ** - 4 essential questions (concise answers)
6. **Start** - Simple assessment form

### Design System

#### Feature Cards
- **Background**: White (#ffffff)
- **Shadow**: Layered (0 1px 3px rgba(0,0,0,0.04), 0 4px 6px rgba(0,0,0,0.02))
- **Border Radius**: 8px
- **Padding**: 36px
- **Hover**: Lifts with translateY(-4px) and enhanced shadow
- **Accent**: Hidden gradient bar appears on hover
- **Numbers**: Small circular badges (1,2,3) for step indicators

#### Grid Layout
- **Desktop**: 3 columns (fixed) for perfect alignment
- **Tablet/Mobile**: Single column stack
- **Gap**: 48px between cards

### Key Messaging
- **Core Theme**: "Profound change requires profound care"
- **Success Stat**: 70% quit without MDs vs 87% succeed with monitoring
- **Weight Loss**: 15-20% average body weight loss
- **Differentiation**: Medical practice, not pill mill

### FAQ Content Structure

#### Quick FAQ (Overview Section)
Three cards displayed on the Overview tab for immediate answers to top concerns:
1. **Is this covered by insurance?** - Coverage varies by plan. Many require prior authorization. Our $149/month cash price often beats copays, with no delays or denials.
2. **How much weight will I lose?** - Clinical trials show 15-22% body weight loss over 12-18 months. Most notice appetite changes within weeks.
3. **Why do I need a physician?** - GLP-1s are powerful. With MD guidance, you get safe dosing, side effect management, and better success rates.

#### Full FAQ (Accordion on FAQ Tab)
**Top 3 Questions (Expanded by Default):**
1. **Is this covered by insurance?**
   - Coverage depends on your plan. Many insurers require prior authorization and certain criteria (BMI + health conditions). Medicare usually only covers GLP-1s for diabetes, not weight loss. Medicaid coverage is very limited. If not covered, we'll guide you to cash-pay programs like Wegovy® (~$499/month) and Zepbound™ ($349–$499/month). Our $149 monthly fee covers all physician services.

2. **How much weight will I lose?**
   - Results vary, but clinical trials with lifestyle support show 15–22% body weight loss over 12–18 months. Most people notice appetite changes within a few weeks, with steady progress as doses increase. Your physician will optimize your dosing based on your individual response and tolerance.

3. **Why do I need a physician?**
   - GLP-1s are powerful medications that affect multiple organ systems. Without medical guidance, many people stop early due to side effects or access issues. With physician-led care, you get safe dose titration, side-effect management, and lab monitoring when needed—improving both safety and success rates from 30% to over 87%.

**Additional Questions (Collapsed by Default):**
- What is prior authorization (PA)?
- What if my insurance denies coverage?
- Do I need lab tests?
- How will follow-ups work?
- What if I miss a dose?
- Can I use GoodRx or compounding pharmacies?
- What if my pharmacy is out of stock?

## Version Control
- Commit message format: "Component: Brief description"
- Always test responsive design before committing
- Keep experimental designs in separate HTML files
- Document significant style changes in commit messages

## CRITICAL MESSAGING REQUIREMENTS

### Core Positioning
**"Find your rhythm in weight loss"**
- Brand Name: **Tempo**
- Tagline: "Weight loss at your pace"
- Philosophy: Sustainable weight loss guided by board-certified MDs, adapted to each patient's natural pace
- Focus on MD supervision with emphasis on sustainable, pressure-free progress

### FINAL APPROVED MESSAGING (LOCKED - DO NOT CHANGE)

**Official Tagline:** "Board-Certified Physicians. Evidence-Based Results. At Your Cadence."

**Hero Headline:** "Find Your Rhythm in Weight Loss."

**Physician Credentials:** "Guided by board-certified internal medicine physicians with 20+ years of hospitalist and faculty experience at leading institutions including Mayo Clinic, UCSF, University of Minnesota, Allina Health, and PeaceHealth."

**Pricing Structure:**
- Initial Consultation: $249 (comprehensive metabolic evaluation)
- Follow-Up Visits: $199 (dose titration and monitoring)

**Key Statistics:** 30% success rate without MD supervision vs 87% with physician care

**Core Messaging Themes:**
- Premium medical practice positioning
- Extensive institutional credentials (Mayo, UCSF, etc.)
- Evidence-based medicine approach  
- "Profound metabolic change requires profound care"
- Sustainable, physician-supervised results

⚠️ **DO NOT MODIFY THESE MESSAGING ELEMENTS WITHOUT EXPLICIT USER APPROVAL**

## Netlify Deployment & Troubleshooting

### 🚀 Deployment Architecture

#### Normal Flow
1. **Local changes** → `git add` → `git commit` → `git push origin main`
2. **GitHub webhook** → Triggers Netlify build
3. **Netlify auto-deploy** → Updates live site
4. **Live URL**: https://cadencehealth.netlify.app

#### Key Configuration
- **Main file**: `index.html` (confirmed by `netlify.toml` redirect)
- **Publish directory**: `.` (root directory)
- **Build command**: None (static HTML)
- **Repository**: https://github.com/manisahni/cadencehealth.git

### ⚠️ Common Deployment Issues

#### Issue: Changes Not Deploying (September 2025 Case Study)
**Symptoms:**
- Local files updated correctly ✅
- Changes committed and pushed to GitHub ✅  
- Live site serving old content ❌

**Root Causes:**
- Netlify auto-deployment failure (silent)
- GitHub webhook disconnection
- Netlify build cache issues
- Branch mismatch in Netlify settings

**Solution Hierarchy:**
1. **Force manual deployment**: `netlify deploy --prod`
2. **Check Netlify dashboard**: Look for failed builds
3. **Clear Netlify cache**: If available in dashboard
4. **Verify GitHub connection**: Ensure correct repo/branch

### 🛠️ Troubleshooting Workflow

#### Step 1: Verify Local Changes
```bash
# Check specific changes exist locally
grep -n "your-change" index.html
```

#### Step 2: Verify Git Status  
```bash
# Check commits are pushed
git status
git log --oneline -3
```

#### Step 3: Test Live Site
```bash
# Check if changes are live
curl -s https://cadencehealth.netlify.app/ | grep "your-change"
```

#### Step 4: Force Deploy (if needed)
```bash
# Manual deployment via CLI
netlify status  # Verify connection
netlify deploy --prod  # Force fresh deployment
```

#### Step 5: Verification
```bash
# Wait 30 seconds, then verify
sleep 30
curl -s https://cadencehealth.netlify.app/ | grep "your-change"
```

### 📋 Deployment Checklist

Before considering a deployment "complete":
- [ ] Local changes tested and committed
- [ ] Changes pushed to GitHub successfully
- [ ] Live site checked for updates (don't assume!)
- [ ] Form functionality tested (if form changes made)
- [ ] Critical user paths verified working

### 🔧 Netlify CLI Setup

#### Installation & Authentication
```bash
# Install Netlify CLI globally
npm install -g netlify-cli

# Login to your Netlify account  
netlify login

# Link to project (run in project directory)
netlify link --id 85c63b0d-534b-46db-aac2-3b0b2a8a23f7
```

#### Essential Commands
```bash
netlify status          # Check connection & project info
netlify deploy --prod   # Force production deployment  
netlify open            # Open project in browser
netlify env:list       # Check environment variables
```

### 🚨 Critical Lessons Learned

#### Never Assume Deployment Worked
- **Bad**: Push code → assume it's live
- **Good**: Push code → verify it's live → test functionality

#### Keep CLI as Backup
- GitHub integration can fail silently
- Manual deployment via CLI bypasses webhook issues
- Always have `netlify-cli` installed and authenticated

#### Document Recurring Issues
- If deployment fails twice, document the pattern
- Note specific error messages for future reference
- Update this troubleshooting guide with new solutions

### 📝 Historical Issues Log

#### September 5, 2025: Auto-Deployment Failure
- **Issue**: Phone number removal and FAQ reordering not deploying
- **Duration**: ~45 minutes of debugging
- **Root Cause**: Netlify auto-deployment stuck/failing silently
- **Solution**: `netlify deploy --prod` worked immediately
- **Prevention**: Always verify deployment with curl test

*Add new issues here to build institutional knowledge*