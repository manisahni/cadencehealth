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

## Local Development Environment

### 🏗️ Development Philosophy

**ALWAYS develop and test locally before pushing to production!**

- **Bad**: Edit code → Git push → Hope it works on live site
- **Good**: Edit code → Test locally → Verify functionality → Git push → Deploy

### 🚀 Quick Start

#### Method 1: Node.js Live Server (Recommended)
```bash
# Start development server with auto-reload
npm run dev
# Opens http://localhost:3000 automatically
```

#### Method 2: Python Simple Server (Backup)
```bash
# Start simple HTTP server (no auto-reload)
npm run serve
# Manual navigation to http://localhost:8000
```

### 📋 Available Development Commands

```bash
npm run dev      # Start dev server (no browser auto-open)
npm run start    # Start dev server with browser auto-open
npm run preview  # Start server with overview.html (development file)
npm run serve    # Python fallback server
```

### 🎯 Development Workflow

#### Step 1: Start Local Server
```bash
cd /Users/nish_macbook/glp-clinic-website
npm run dev
```

#### Step 2: Make Changes
- Edit `index.html`, CSS, or JavaScript
- Changes auto-reload in browser (with live-server)
- Test all functionality locally

#### Step 3: Test Critical Paths
- **Form Assessment Flow**: BMI calculator → Basic info → Safety checks
- **FAQ Interaction**: Accordion expand/collapse
- **Responsive Design**: Test mobile/desktop layouts
- **Form Validation**: Test required fields

#### Step 4: Deploy When Ready
```bash
git add .
git commit -m "Description of changes"
git push origin main
# If auto-deploy fails: netlify deploy --prod
```

### 🔧 Form Development Strategy

#### Local Form Testing Limitation
**Issue**: Netlify Forms (`data-netlify="true"`) only work in production
**Solution**: Test form structure locally, functionality in production

#### Local Testing Checklist
- [ ] Form fields display correctly
- [ ] Required field validation works
- [ ] Assessment flow logic functions
- [ ] Form styling matches design
- [ ] All form steps are accessible

#### Production Form Testing
Use Netlify Deploy Preview for actual form submission testing:
```bash
netlify deploy  # Creates preview URL for testing
```

### 🐛 Local Development Troubleshooting

#### Common Issues

**Port Already in Use**
```bash
# Find process using port 3000
lsof -i :3000
# Kill the process
kill -9 <PID>
```

**Live-server Not Found**
```bash
# Reinstall globally
npm install -g live-server
```

**Form Doesn't Work Locally**
- **Expected**: Forms won't submit locally (Netlify dependency)
- **Solution**: Test form structure locally, submission in production/preview

### 🎨 File Development Priorities

#### Primary Development File
- **index.html** - Main production file served by Netlify
- Always test changes in this file locally

#### Secondary Files
- **overview.html** - Development/experimental file
- Use `npm run preview` to test overview.html changes

### 📁 Development File Structure
```
glp-clinic-website/
├── index.html          # Primary production file
├── overview.html       # Development/experimental
├── package.json        # Development scripts
├── netlify.toml        # Netlify configuration
├── CLAUDE.md           # Project documentation
└── thank-you.html      # Form success page
```

### 🚨 Before Every Git Push

#### Pre-Deployment Checklist
- [ ] **Tested locally**: All changes work on localhost
- [ ] **Critical paths verified**: Form flow, navigation, responsive design
- [ ] **No console errors**: Check browser dev tools
- [ ] **Form structure intact**: All required fields present
- [ ] **Content accurate**: No typos or formatting issues

#### Git Workflow
```bash
# 1. Test locally first
npm run dev

# 2. Verify everything works
# Test forms, navigation, responsive design

# 3. Commit with descriptive message
git add .
git commit -m "Specific description of what changed"

# 4. Push to production
git push origin main

# 5. Verify deployment (wait 1-2 minutes)
curl -s https://cadencehealth.netlify.app/ | grep "your-change"

# 6. If deployment failed, force deploy
netlify deploy --prod
```

This workflow prevents deployment issues and ensures professional development practices.

## Form Handling with Web3Forms

### 🚀 Current Form Solution: Web3Forms

The website uses Web3Forms for lead collection - a simple, free service that works both locally and in production.

#### Why Web3Forms?
- ✅ **Works locally**: Test on localhost immediately
- ✅ **Free**: Unlimited form submissions  
- ✅ **Simple setup**: 2 minutes to get running
- ✅ **No account needed**: Just email verification
- ✅ **Email notifications**: Direct to your inbox
- ✅ **No CORS issues**: Works everywhere

#### Configuration Location
```javascript
// In index.html, line 1896
const WEB3FORMS_ACCESS_KEY = 'YOUR_ACCESS_KEY_HERE';
```

#### Quick Setup (2 minutes)
1. Go to https://web3forms.com
2. Enter your email to get access key
3. Replace `YOUR_ACCESS_KEY_HERE` in index.html
4. Done! Test locally with `npm run dev`

Full guide: See `WEB3FORMS_SETUP.md`

#### How It Works
1. User fills out form on website
2. JavaScript sends data to Web3Forms API
3. Web3Forms sends email notification
4. Success message shown to user
5. You receive email with submission details

#### Testing Locally
```bash
# Start local server
npm run dev

# Open http://localhost:3000
# Submit form
# Check email for submission
```

#### Data Received
Each submission includes:
- Name and Email
- Timestamp (EST/EDT)
- Subject line for easy filtering
- Can add more fields as needed

### 📋 Alternative Form Solutions

#### Previous Implementation: Google Forms
- Setup guide available in `GOOGLE_FORMS_SETUP.md`
- More complex setup but provides Google Sheets integration
- Requires creating Google Form and extracting field IDs

#### Other Options Considered
- **Netlify Forms**: Only works on Netlify deployment (not locally)
- **Formspree**: Requires account, limited free tier
- **EmailJS**: 200 emails/month limit
- **Basin**: Requires account setup

---

## 📚 Project Change Log & Institutional Memory

### September 9, 2025: Major Messaging Overhaul

#### Changes Made
1. **Physician Messaging Refinement**
   - Problem: Repetitive "board-certified MD" felt forced
   - Solution: Varied terminology (physician, medical supervision, real doctors)
   - Result: More natural, readable content
   
2. **Disease Prevention Focus**
   - Added: Diabetes, prediabetes, NASH, cardiovascular, stroke, kidney, cancer risk
   - Statistics: 68% prediabetes reversal, 20% CVD reduction, 39% NASH improvement
   - Rationale: Specific health outcomes > generic "weight loss"

3. **Pricing Corrections**
   - Fixed: FAQ pricing ($149/$149 → $249/$199)
   - Standardized: Zepbound pricing ($349-$549/month)
   - Removed: Duplicate "pill mills" FAQ entry

4. **Health Monitoring Reframe**
   - Old: Generic categories (Metabolic, Cardiovascular, Safety)
   - New: Condition-specific (Diabetes & NASH Prevention, Heart Attack & Stroke Risk)
   - Impact: Clearer value proposition for patients

#### Lessons Learned
- **Messaging**: Natural language variation improves readability
- **Specificity**: Name conditions explicitly (NASH, not "liver health")
- **Statistics**: Lead with prevention percentages, not just weight loss
- **Consistency**: Always grep for pricing across entire file
- **Duplicates**: Check for repeated FAQ entries after edits

#### Technical Notes
- Web3Forms key: f99cde71-9245-490c-af96-3dab554e8ca5
- All health statistics from peer-reviewed studies
- Biomarkers emphasized: HOMA-IR, hsCRP, ApoB, eGFR

---

## 🎯 Content Strategy & Design Patterns

### Messaging Hierarchy
1. **Prevention First**: "Prevent diabetes" > "Treat obesity"
2. **Specific Conditions**: "68% reverse prediabetes" > "Improve health"
3. **Economic Value**: "$13k/year savings" validates investment
4. **Differentiation**: "Not a pill mill" throughout

### Page Section Strategy
- **Hero**: Biggest health fear (diabetes prevention)
- **Science**: Back up with clinical statistics
- **Method**: Show medical rigor
- **Pricing**: Frame as prevention investment
- **FAQ**: Address specific health concerns

### Health Claims Guidelines
- Always cite "studies show" or "clinical trials"
- Use ranges for statistics (15-20%, not 17.3%)
- Include biomarkers (HOMA-IR, hsCRP)
- Say "may reduce" not "will prevent"
- Emphasize monitoring over guarantees

### Pricing Philosophy
- Lead with value (prevention savings)
- Separate service fees from medication costs
- Emphasize physician expertise
- Compare to complication costs
- Transparent about cash-pay model

---

## 🔧 Technical Quirks & Maintenance

### Known Issues & Solutions
1. **Netlify Auto-Deploy**: Sometimes fails silently
   - Solution: `netlify deploy --prod`
   
2. **Form Validation**: Continue button was hidden
   - Solution: Always visible, validate on click
   
3. **Pricing Consistency**: Multiple locations
   - Check: Hero, Pricing section, FAQ, Form
   
4. **FAQ Duplicates**: Copy-paste errors
   - Prevention: Search before adding new items

### Regular Maintenance Tasks
- [ ] Monthly: Verify all statistics are current
- [ ] Weekly: Test form submission flow
- [ ] Per Edit: Search all pricing mentions
- [ ] Per Deploy: Curl verify changes went live

### Before Major Changes
1. Document current state in CLAUDE.md
2. Note specific problems being solved
3. Test locally with multiple browsers
4. Verify mobile responsiveness
5. Check form still submits correctly

---

## 🚀 Future Development Roadmap

### Near-term Opportunities
- [ ] Testimonials section with before/after stories
- [ ] Interactive BMI/risk calculator
- [ ] Comparison table (us vs pill mills)
- [ ] Educational blog about biomarkers
- [ ] Insurance navigation guide

### Potential Enhancements
- Landing pages for specific conditions (prediabetes, NASH)
- Chat widget for immediate questions
- Video testimonials from success stories
- Automated email follow-up sequence
- A/B testing different headlines

### Content Expansion Ideas
- "What is NASH?" educational content
- "Understanding Your HOMA-IR Score"
- "Why ApoB Matters More Than LDL"
- "Preventing Diabetes: A Timeline"
- Insurance appeal letter templates

---

## 📋 Quick Reference

### Key Statistics Used
- 68% prediabetes reversal
- 20% cardiovascular event reduction
- 39% liver fat reduction (NASH)
- 52% insulin resistance improvement
- 15-20% average weight loss
- 85% program completion (vs 30% pill mills)

### Pricing Structure
- Initial consultation: $249
- Follow-ups: $199
- Essential monitoring: $99/month
- Advanced monitoring: $149/month
- Devices: ~$200 one-time

### Important Files
- `index.html` - Main production file
- `CLAUDE.md` - This documentation
- `WEB3FORMS_SETUP.md` - Form configuration
- `.gitignore` - Deployment exclusions
- `netlify.toml` - Deployment config

### Emergency Contacts
- Netlify site ID: 85c63b0d-534b-46db-aac2-3b0b2a8a23f7
- GitHub repo: https://github.com/manisahni/cadencehealth.git
- Production URL: https://cadencehealth.netlify.app

---

## 🎓 Institutional Knowledge

### Why These Decisions Were Made

**Web3Forms over alternatives**: 
- Works locally (unlike Netlify Forms)
- Free unlimited (unlike EmailJS)  
- No account needed (unlike Formspree)

**Physician messaging variation**:
- SEO benefits from semantic variety
- Reduces reader fatigue
- Sounds more natural/conversational

**Disease-specific focus**:
- Patients search for conditions, not treatments
- Insurance more likely to cover disease prevention
- Creates urgency (prevention window)

**Monitoring emphasis**:
- Differentiates from pill mills
- Justifies pricing
- Builds trust through transparency

This documentation preserves not just what we built, but WHY we built it this way.