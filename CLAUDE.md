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
**This is the approved design moving forward**
- Brand: Tempo
- Tagline: "Weight loss at your pace"
- Design: Caliber's clean minimalist layout
- Messaging: Tempo's rhythm/pace philosophy
- Colors: Pure white background, black primary
- ALL FUTURE DEVELOPMENT should be on fusion.html

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

### Required Messaging Elements
1. **Always emphasize MD monitoring** - Every patient is supervised by board-certified physicians
2. **Use clear "weight loss" language** - Not "metabolic health" or vague wellness terms
3. **Highlight continuous supervision** - Monthly lab reviews, dose adjustments, ongoing optimization
4. **Lead with medical legitimacy** - Board-certified MDs, not just "providers" or "clinicians"
5. **Speed + Safety** - "Start Now" but with proper medical evaluation

### Key Differentiators to Always Include
- **Continuous MD Monitoring**: Your board-certified physician reviews labs monthly
- **Personalized Treatment**: MD creates customized weight management protocol
- **Complete Medical Care**: Not just prescriptions - ongoing supervision and optimization
- **Direct MD Access**: Same physician throughout, available for questions

### Language Requirements
- Say "weight loss" or "weight management" NOT "metabolic transformation"
- Say "board-certified MD" or "physician" NOT just "doctor" or "provider"
- Say "medical supervision" NOT "support" or "guidance"
- Say "Start Now" NOT "Begin your journey" or other soft language

### The Closing Statement
**"Lasting change in weight and metabolism, guided by board-certified MDs"**
- Use this or variation as tagline/footer
- Emphasizes both outcome and medical authority