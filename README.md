# NXSys AI Landing Page - Maintenance & Customization Guide

## Table of Contents
1. [Overview](#overview)
2. [File Structure](#file-structure)
3. [Updating Text Content](#updating-text-content)
4. [Modifying Styling with Tailwind CSS](#modifying-styling-with-tailwind-css)
5. [Fixing and Managing Links](#fixing-and-managing-links)
6. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
7. [Common Customizations](#common-customizations)
8. [Troubleshooting](#troubleshooting)

---

## Overview

This landing page is built using:
- **HTML5** - The structure and content
- **Tailwind CSS** - A utility-first CSS framework for styling (loaded from CDN)
- **Font Awesome** - Icon library for visual elements
- **Vanilla JavaScript** - Interactive features like mobile menu and FAQ accordion

The page is fully responsive, meaning it automatically adapts to different screen sizes (mobile, tablet, desktop). All styling is done through CSS classes rather than traditional CSS files, making it easy to modify without touching separate stylesheets.

---

## File Structure

Your project should have the following files:

```
project-folder/
├── index.html              (Main landing page - the file provided)
├── privacy.html            (Privacy policy page - needs to be created)
├── terms.html              (Terms of service page - needs to be created)
└── blog.html               (Blog page - optional, already linked in footer)
```

**Important:** All HTML files should be in the same folder for links to work correctly.

---

## Updating Text Content

### Understanding the HTML Structure

The landing page is organized into clear sections. Here's how to find and update text:

#### 1. **Header/Navigation Section** (Lines 48-82)
Located at the top of the page with the logo and menu.

**Current text to update:**
```html
<span class="text-xl font-bold text-gray-900">NXSys AI</span>
```

**How to update:**
1. Open `index.html` in a text editor (like Notepad, VS Code, or Sublime Text)
2. Find the line with `NXSys AI` (around line 63)
3. Replace `NXSys AI` with your company name
4. Save the file

**Example:** Change to `MyCompany AI`
```html
<span class="text-xl font-bold text-gray-900">MyCompany AI</span>
```

---

#### 2. **Hero Section** (Lines 97-180)
This is the large banner at the top with the main headline and call-to-action buttons.

**Key text elements to update:**

**Main Headline:**
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight tracking-tight text-gray-900 mb-6">
    Unleash AI's Power for Your <span class="gradient-text">Business Growth</span>
</h1>
```

To update: Replace the entire text inside the `<h1>` tags, keeping the `<span class="gradient-text">` wrapper around the part you want colored.

**Description Text:**
```html
<p class="text-lg md:text-xl text-gray-600 leading-relaxed max-w-2xl">
    Automate the mundane, innovate the extraordinary. Transform your operations...
</p>
```

To update: Replace all text inside the `<p>` tags.

---

#### 3. **Features Section** (Lines 233-340)
Contains three feature cards with titles and descriptions.

**Structure of each feature card:**
```html
<div class="bg-white rounded-2xl p-8 border border-gray-100...">
    <h3 class="text-xl font-bold text-gray-900 mb-3">
        Intelligent Workflow Orchestration
    </h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Automate complex business processes...
    </p>
    <ul class="space-y-2 text-sm text-gray-600">
        <li class="flex items-center space-x-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Multi-step process automation</span>
        </li>
    </ul>
</div>
```

**To update a feature:**
1. Find the feature card you want to change
2. Update the `<h3>` text (the title)
3. Update the `<p>` text (the description)
4. Update each `<span>` inside the bullet points (`<li>` tags)

**Example - Changing the first feature:**
```html
<!-- BEFORE -->
<h3 class="text-xl font-bold text-gray-900 mb-3">
    Intelligent Workflow Orchestration
</h3>

<!-- AFTER -->
<h3 class="text-xl font-bold text-gray-900 mb-3">
    Smart Process Automation
</h3>
```

---

#### 4. **Benefits Section** (Lines 362-490)
Contains three benefit cards with icons and detailed information.

**Structure:**
```html
<h3 class="text-xl font-bold text-gray-900 mb-2">Boost Operational Efficiency</h3>
<p class="text-gray-600 leading-relaxed mb-4">
    Reduce manual workload by up to 80%...
</p>
<div class="bg-blue-50 rounded-lg p-4">
    <p class="text-sm font-semibold text-blue-900">Average Results:</p>
    <ul class="text-sm text-blue-800 mt-2 space-y-1">
        <li>• 80% reduction in manual tasks</li>
        <li>• 60% faster process execution</li>
        <li>• 90% error reduction</li>
    </ul>
</div>
```

**To update:** Replace text in `<h3>`, `<p>`, and `<li>` tags as needed.

---

#### 5. **Testimonials Section** (Lines 512-620)
Contains customer quotes and reviews.

**Structure of each testimonial:**
```html
<p class="text-gray-700 leading-relaxed mb-6 text-lg">
    "NXSys AI transformed our operations overnight..."
</p>
<div class="flex items-center space-x-4">
    <div class="w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-600 rounded-full 
    flex items-center justify-center text-white font-bold text-lg">
        SJ
    </div>
    <div>
        <p class="font-bold text-gray-900">Sarah Johnson</p>
        <p class="text-sm text-gray-600">VP of Operations, TechCorp Solutions</p>
    </div>
</div>
```

**To update a testimonial:**
1. Replace the quote text in the `<p>` tag
2. Replace the initials (SJ, MC, etc.) in the circle
3. Update the name in the first `<p>` under the circle
4. Update the job title and company in the second `<p>`

---

#### 6. **About Us Section** (Lines 642-710)
Contains company information and statistics.

**Main content:**
```html
<h3 class="text-2xl font-bold text-gray-900 mb-4">Our Story</h3>
<p class="text-gray-700 leading-relaxed text-lg">
    Founded in 2019 by a team of AI researchers...
</p>
```

**Statistics at the bottom:**
```html
<div class="grid grid-cols-3 gap-6 border-t border-gray-200 pt-8">
    <div class="text-center">
        <p class="text-4xl font-bold text-blue-600">500+</p>
        <p class="text-gray-600 mt-2">Enterprise Customers</p>
    </div>
    <!-- More stats... -->
</div>
```

---

#### 7. **FAQ Section** (Lines 732-855)
Frequently asked questions with expandable answers.

**Structure of each FAQ item:**
```html
<div class="faq-item bg-white rounded-2xl border border-gray-200...">
    <button class="faq-question w-full px-8 py-6...">
        <span class="text-lg font-semibold text-gray-900...">
            How long does implementation typically take?
        </span>
    </button>
    <div class="faq-answer hidden px-8 pb-6...">
        <p>
            Implementation timelines vary based on complexity...
        </p>
    </div>
</div>
```

**To update an FAQ:**
1. Replace the question text in the first `<span>`
2. Replace the answer text in the `<p>` inside `faq-answer`

---

#### 8. **Footer Section** (Lines 900-980)
Contains company information, links, and contact details.

**Company description:**
```html
<p class="text-gray-400 mb-6">
    Empowering businesses with intelligent automation...
</p>
```

**Contact email:**
```html
<a href="mailto:ecomm@nxsys.com.au" class="text-blue-400 hover:text-blue-300">
    ecomm@nxsys.com.au
</a>
```

**To update email:**
Replace `ecomm@nxsys.com.au` with your email address in both locations where it appears.

---

### Quick Reference: Text Update Locations

| Section | Line Numbers | What to Update |
|---------|-------------|-----------------|
| Logo/Brand Name | ~63 | Company name |
| Navigation Menu | ~66-70 | Menu link text (optional) |
| Hero Headline | ~110-114 | Main headline |
| Hero Description | ~115-120 | Tagline/description |
| CTA Button Text | ~127, ~133 | Button labels |
| Features (3 cards) | ~260-340 | Feature titles, descriptions, bullets |
| Benefits (3 cards) | ~390-480 | Benefit titles, descriptions, stats |
| Testimonials (4 cards) | ~550-620 | Quotes, names, titles |
| About Section | ~660-705 | Company story, mission, stats |
| FAQ Questions | ~755-855 | Questions and answers |
| Footer Email | ~950 | Contact email |

---

## Modifying Styling with Tailwind CSS

### Understanding Tailwind CSS Classes

Tailwind CSS uses utility classes instead of traditional CSS. Each class does one specific thing. Here are the most common ones used in this landing page:

#### Color Classes

**Text Colors:**
- `text-gray-900` - Dark gray text
- `text-blue-600` - Blue text
- `text-white` - White text
- `text-gray-600` - Medium gray text

**Background Colors:**
- `bg-white` - White background
- `bg-gradient-to-r from-blue-600 to-purple-600` - Gradient from blue to purple
- `bg-slate-50` - Very light gray background
- `bg-gray-900` - Dark gray background

**Border Colors:**
- `border-gray-100` - Light gray border
- `border-blue-300` - Light blue border

#### Sizing Classes

**Padding (spacing inside elements):**
- `p-4` - Small padding all sides
- `p-8` - Medium padding all sides
- `px-8` - Padding left and right only
- `py-4` - Padding top and bottom only

**Margin (spacing outside elements):**
- `m-4` - Small margin all sides
- `mb-6` - Margin bottom only
- `space-x-4` - Horizontal spacing between child elements

**Width and Height:**
- `w-full` - 100% width
- `w-96` - Fixed width
- `h-12` - Fixed height
- `max-w-7xl` - Maximum width (container constraint)

#### Layout Classes

**Flexbox (arranging items in rows):**
- `flex` - Enable flexbox layout
- `flex-col` - Stack items vertically
- `items-center` - Center items vertically
- `justify-between` - Space items apart
- `gap-4` - Space between flex items

**Grid (arranging items in columns):**
- `grid` - Enable grid layout
- `grid-cols-1` - 1 column (mobile)
- `grid-cols-3` - 3 columns (desktop)
- `gap-8` - Space between grid items

#### Responsive Classes

Tailwind uses prefixes to apply styles at different screen sizes:
- `md:` - Medium screens and up (tablets)
- `lg:` - Large screens and up (desktops)
- `sm:` - Small screens and up

**Example:**
```html
<div class="text-2xl md:text-4xl lg:text-5xl">
```
This means:
- Mobile: text size 2xl
- Tablet (md): text size 4xl
- Desktop (lg): text size 5xl

---

### Common Styling Changes

#### 1. **Change the Main Color Scheme**

The page uses blue and purple as primary colors. To change them:

**Find these color classes and replace:**

| Find | Replace With | Effect |
|------|-------------|--------|
| `from-blue-600` | `from-green-600` | Changes blue to green |
| `to-purple-600` | `to-indigo-600` | Changes purple to indigo |
| `text-blue-600` | `text-green-600` | Changes text color |
| `hover:text-blue-600` | `hover:text-green-600` | Changes hover color |

**Example - Change main gradient from blue-purple to green-teal:**

Find this (around line 127):
```html
<a href="https://test.com" class="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-8 py-4 rounded-full font-bold text-lg hover:shadow-xl smooth-transition hover:scale-105 text-center">
```

Change to:
```html
<a href="https://test.com" class="bg-gradient-to-r from-green-600 to-teal-600 text-white px-8 py-4 rounded-full font-bold text-lg hover:shadow-xl smooth-transition hover:scale-105 text-center">
```

---

#### 2. **Change Button Styling**

**Make buttons smaller:**
Find: `px-8 py-4` (padding)
Replace with: `px-6 py-2` (smaller)

**Make buttons larger:**
Find: `px-8 py-4`
Replace with: `px-10 py-5` (larger)

**Example - Smaller CTA button:**
```html
<!-- BEFORE -->
<a href="https://test.com" class="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-8 py-4 rounded-full font-bold text-lg...">

<!-- AFTER -->
<a href="https://test.com" class="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-6 py-2 rounded-full font-bold text-lg...">
```

---

#### 3. **Change Section Spacing**

**Add more space between sections:**
Find: `py-20 md:py-24` (vertical padding)
Replace with: `py-32 md:py-40` (more space)

**Example - Make hero section taller:**
Find (around line 88):
```html
<section class="relative bg-gradient-to-br from-slate-50 via-white to-slate-50 overflow-hidden pt-20 pb-20 md:pt-32 md:pb-32">
```

Change to:
```html
<section class="relative bg-gradient-to-br from-slate-50 via-white to-slate-50 overflow-hidden pt-32 pb-32 md:pt-48 md:pb-48">
```

---

#### 4. **Change Background Colors**

**Make a section darker:**
Find: `bg-white`
Replace with: `bg-gray-50` or `bg-slate-100`

**Example - Change benefits section background:**
Find (around line 352):
```html
<section id="benefits" class="py-20 md:py-24 bg-gradient-to-br from-slate-50 to-slate-100">
```

Change to:
```html
<section id="benefits" class="py-20 md:py-24 bg-gradient-to-br from-blue-50 to-purple-50">
```

---

#### 5. **Change Text Size**

Tailwind text sizes follow a scale. Here's the hierarchy:
- `text-sm` - Small (12px)
- `text-base` - Normal (16px)
- `text-lg` - Large (18px)
- `text-xl` - Extra large (20px)
- `text-2xl` - 2x large (24px)
- `text-3xl` - 3x large (30px)
- `text-4xl` - 4x large (36px)
- `text-5xl` - 5x large (48px)
- `text-6xl` - 6x large (60px)

**Example - Make feature titles smaller:**
Find (around line 268):
```html
<h3 class="text-xl font-bold text-gray-900 mb-3">
```

Change to:
```html
<h3 class="text-lg font-bold text-gray-900 mb-3">
```

---

#### 6. **Change Border Radius (Roundness)**

- `rounded-lg` - Slightly rounded corners
- `rounded-xl` - More rounded
- `rounded-2xl` - Very rounded
- `rounded-full` - Completely round (for circles)

**Example - Make cards less rounded:**
Find (around line 254):
```html
<div class="bg-white rounded-2xl p-8 border border-gray-100...">
```

Change to:
```html
<div class="bg-white rounded-lg p-8 border border-gray-100...">
```

---

#### 7. **Change Shadow Effects**

- `shadow-md` - Small shadow
- `shadow-lg` - Medium shadow
- `shadow-xl` - Large shadow
- `shadow-2xl` - Extra large shadow

**Example - Make cards have more shadow:**
Find (around line 387):
```html
<div class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl smooth-transition group">
```

Change to:
```html
<div class="bg-white rounded-2xl p-8 shadow-2xl hover:shadow-2xl smooth-transition group">
```

---

### Advanced: Creating a Custom Color Scheme

If you want to completely change the color scheme, follow these steps:

**Step 1:** Decide on your new colors (e.g., orange and red instead of blue and purple)

**Step 2:** Use Find & Replace (Ctrl+H or Cmd+H in most editors):

| Find | Replace |
|------|---------|
| `blue-600` | `orange-600` |
| `blue-400` | `orange-400` |
| `blue-100` | `orange-100` |
| `purple-600` | `red-600` |
| `purple-400` | `red-400` |
| `purple-100` | `red-100` |

**Step 3:** Save and refresh your browser to see the changes

---

## Fixing and Managing Links

### Understanding Links in HTML

A link in HTML looks like this:
```html
<a href="destination-url">Link Text</a>
```

- `<a>` = anchor tag (creates a clickable link)
- `href` = the destination (where the link goes)
- `Link Text` = what users see and click on

---

### All Links in This Landing Page

#### Navigation Menu Links (Lines 66-70)

These links help users jump to different sections of the page:

```html
<a href="#features" class="text-gray-700 hover:text-blue-600 smooth-transition font-medium">Features</a>
<a href="#benefits" class="text-gray-700 hover:text-blue-600 smooth-transition font-medium">Benefits</a>
<a href="#testimonials" class="text-gray-700 hover:text-blue-600 smooth-transition font-medium">Testimonials</a>
<a href="#faq" class="text-gray-700 hover:text-blue-600 smooth-transition font-medium">FAQ</a>
<a href="#about" class="text-gray-700 hover:text-blue-600 smooth-transition font-medium">About</a>
```

**These are internal links** (they point to sections on the same page). They use the `#` symbol followed by the section ID.

- `#features` points to the section with `id="features"` (line 234)
- `#benefits` points to the section with `id="benefits"` (line 352)
- `#testimonials` points to the section with `id="testimonials"` (line 512)
- `#faq` points to the section with `id="faq"` (line 732)
- `#about` points to the section with `id="about"` (line 642)

**Status:** ✅ These links are correctly set up and working.

---

#### Call-to-Action (CTA) Button Links

**Hero Section CTA Buttons (Lines 127 & 133):**
```html
<a href="https://test.com" class="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-8 py-4 rounded-full font-bold text-lg hover:shadow-xl smooth-transition hover:scale-105 text-center">
    Start Your AI Journey
</a>

<button class="border-2 border-gray-300 text-gray-900 px-8 py-4 rounded-full font-bold text-lg hover:border-blue-600 hover:text-blue-600 smooth-transition hover:bg-blue-50">
    <i class="fas fa-play mr-2"></i> Watch Demo
</button>
```

**Status:** ⚠️ `https://test.com` is a placeholder and needs to be updated.

**How to fix:**
Replace `https://test.com` with your actual signup/trial URL.

**Example:**
```html
<!-- BEFORE -->
<a href="https://test.com" class="...">Start Your AI Journey</a>

<!-- AFTER -->
<a href="https://www.yourcompany.com/signup" class="...">Start Your AI Journey</a>
```

---

**Footer CTA Buttons (Lines 877-883):**
```html
<a href="https://test.com" class="bg-white text-blue-600 px-8 py-4 rounded-full font-bold text-lg hover:shadow-xl smooth-transition hover:scale-105 text-center">
    Start Free Trial
</a>

<a href="mailto:ecomm@nxsys.com.au" class="border-2 border-white text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-white hover:text-blue-600 smooth-transition text-center">
    <i class="fas fa-envelope mr-2"></i> Contact Sales
</a>
```

**Status:** 
- ⚠️ `https://test.com` needs to be updated
- ⚠️ `ecomm@nxsys.com.au` should be your email

---

#### Mobile Menu Links (Lines 76-82)

These are the same navigation links but for mobile devices:

```html
<a href="#features" class="...">Features</a>
<a href="#benefits" class="...">Benefits</a>
<a href="#testimonials" class="...">Testimonials</a>
<a href="#faq" class="...">FAQ</a>
<a href="#about" class="...">About</a>
<a href="https://test.com" class="...">Get Started</a>
```

**Status:** ⚠️ `https://test.com` placeholder needs updating

---

#### Footer Links (Lines 915-940)

**Product Links:**
```html
<li><a href="#features" class="text-gray-400 hover:text-blue-400 smooth-transition">Features</a></li>
<li><a href="#benefits" class="text-gray-400 hover:text-blue-400 smooth-transition">Benefits</a></li>
<li><a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">Pricing</a></li>
<li><a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">Security</a></li>
<li><a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">Roadmap</a></li>
```

**Status:** ⚠️ Pricing, Security, and Roadmap links point to `#` (nowhere) - these need to be created or removed

**Company Links:**
```html
<li><a href="#about" class="...">About Us</a></li>
<li><a href="blog.html" class="...">Blog</a></li>
<li><a href="#" class="...">Careers</a></li>
<li><a href="#" class="...">Press</a></li>
<li><a href="#" class="...">Contact</a></li>
```

**Status:** 
- ✅ About Us works
- ⚠️ `blog.html` - file needs to exist
- ⚠️ Careers, Press, Contact point to `#` (need to be created or removed)

**Legal Links:**
```html
<li><a href="privacy.html" class="...">Privacy Policy</a></li>
<li><a href="terms.html" class="...">Terms of Service</a></li>
<li><a href="#" class="...">Cookie Policy</a></li>
<li><a href="#" class="...">Compliance</a></li>
<li><a href="#" class="...">Accessibility</a></li>
```

**Status:** 
- ⚠️ `privacy.html` and `terms.html` need to be created
- ⚠️ Cookie Policy, Compliance, Accessibility point to `#` (need to be created or removed)

---

#### Social Media Links (Lines 908-913)

```html
<a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">
    <i class="fab fa-linkedin text-lg"></i>
</a>
<a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">
    <i class="fab fa-twitter text-lg"></i>
</a>
<a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">
    <i class="fab fa-github text-lg"></i>
</a>
<a href="#" class="text-gray-400 hover:text-blue-400 smooth-transition">
    <i class="fab fa-facebook text-lg"></i>
</a>
```

**Status:** ⚠️ All social links point to `#` (need to be updated with your actual social media URLs)

---

### Step-by-Step: Update All Links

#### Step 1: Update Main CTA Links

**Find all instances of:**
```html
href="https://test.com"
```

**Replace with your signup URL:**
```html
href="https://www.yourcompany.com/get-started"
```

**Locations to update:**
- Line 127 (Hero button - "Start Your AI Journey")
- Line 133 (Hero button - "Watch Demo") - *optional, could link to video*
- Line 73 (Desktop nav "Get Started")
- Line 81 (Mobile nav "Get Started")
- Line 877 (Footer "Start Free Trial")

---

#### Step 2: Update Email Links

**Find:**
```html
href="mailto:ecomm@nxsys.com.au"
```

**Replace with your email:**
```html
href="mailto:your-email@yourcompany.com"
```

**Locations:**
- Line 883 (Footer "Contact Sales")
- Line 950 (Footer contact info)

---

#### Step 3: Update Social Media Links

**Find each social link and update:**

```html
<!-- LINKEDIN - Find and replace -->
<a href="#" class="..."><i class="fab fa-linkedin..."></i></a>

<!-- REPLACE WITH -->
<a href="https://linkedin.com/company/yourcompany" class="..."><i class="fab fa-linkedin..."></i></a>
```

**Do the same for:**
- Twitter: `https://twitter.com/yourhandle`
- GitHub: `https://github.com/yourprofile`
- Facebook: `https://facebook.com/yourpage`

---

#### Step 4: Remove or Update Non-Essential Links

**For links you don't need yet, you have two options:**

**Option A: Remove them completely**
```html
<!-- Delete this entire line -->
<li><a href="#" class="...">Pricing</a></li>
```

**Option B: Disable them temporarily**
```html
<!-- Change href to # and add disabled styling -->
<li><a href="#" class="text-gray-400 cursor-not-allowed...">Pricing (Coming Soon)</a></li>
```

---

### Quick Link Reference Table

| Link Purpose | Current Value | What to Change To | Priority |
|-------------|---------------|------------------|----------|
| Main signup | `https://test.com` | Your signup URL | 🔴 High |
| Contact email | `ecomm@nxsys.com.au` | Your email | 🔴 High |
| LinkedIn | `#` | Your LinkedIn URL | 🟡 Medium |
| Twitter | `#` | Your Twitter URL | 🟡 Medium |
| GitHub | `#` | Your GitHub URL | 🟡 Medium |
| Facebook | `#` | Your Facebook URL | 🟡 Medium |
| Privacy Policy | `privacy.html` | Create this file | 🔴 High |
| Terms of Service | `terms.html` | Create this file | 🔴 High |
| Blog | `blog.html` | Create this file or remove | 🟡 Medium |
| Careers | `#` | Remove or create page | 🟢 Low |
| Pricing | `#` | Remove or create page | 🟢 Low |

---

## Linking Privacy and Terms Pages

### Understanding the Requirement

Your landing page currently links to `privacy.html` and `terms.html` in the footer, but these files don't exist yet. We need to:

1. Create these two new HTML files
2. Add content to them
3. Ensure they're properly linked

---

### Step 1: Create the Privacy Policy Page

**Create a new file:**
1. Open your text editor (Notepad, VS Code, etc.)
2. Click **File → New File**
3. Save it as `privacy.html` in the same folder as `index.html`

**Copy and paste this template:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - NXSys AI">
    <title>Privacy Policy - NXSys AI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        * {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center space-x-2">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-600 to-purple-600 rounded-full flex items-center justify-center">
                    <i class="fas fa-brain text-white text-lg"></i>
                </div>
                <a href="index.html" class="text-xl font-bold text-gray-900">NXSys AI</a>
            </div>
            <a href="index.html" class="text-gray-700 hover:text-blue-600 font-medium">← Back to Home</a>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-20 md:py-24 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
            
            <div class="prose prose-lg max-w-none space-y-8 text-gray-700">
                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Introduction</h2>
                    <p>
                        NXSys AI ("we", "us", "our", or "Company") operates the website and services. This page informs you of our policies regarding the collection, use, and disclosure of personal data when you use our Service and the choices you have associated with that data.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Information Collection and Use</h2>
                    <p>
                        We collect several different types of information for various purposes to provide and improve our Service to you.
                    </p>
                    <h3 class="text-xl font-semibold text-gray-900 mt-4 mb-2">Types of Data Collected:</h3>
                    <ul class="list-disc list-inside space-y-2">
                        <li>Personal identification information (name, email address, phone number, etc.)</li>
                        <li>Cookies and usage data</li>
                        <li>Device information and browser type</li>
                        <li>IP address and location data</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">3. Use of Data</h2>
                    <p>
                        NXSys AI uses the collected data for various purposes:
                    </p>
                    <ul class="list-disc list-inside space-y-2">
                        <li>To provide and maintain our Service</li>
                        <li>To notify you about changes to our Service</li>
                        <li>To allow you to participate in interactive features of our Service</li>
                        <li>To provide customer support</li>
                        <li>To gather analysis or valuable information so that we can improve our Service</li>
                        <li>To monitor the usage of our Service</li>
                        <li>To detect, prevent and address technical issues</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Security of Data</h2>
                    <p>
                        The security of your data is important to us, but remember that no method of transmission over the Internet or method of electronic storage is 100% secure. While we strive to use commercially acceptable means to protect your Personal Data, we cannot guarantee its absolute security.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Changes to This Privacy Policy</h2>
                    <p>
                        We may update our Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy on this page and updating the "effective date" at the top of this Privacy Policy.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Contact Us</h2>
                    <p>
                        If you have any questions about this Privacy Policy, please contact us at:
                    </p>
                    <p class="text-blue-600 font-semibold">
                        <a href="mailto:ecomm@nxsys.com.au">ecomm@nxsys.com.au</a>
                    </p>
                </div>

                <div class="text-sm text-gray-600 pt-8 border-t border-gray-200">
                    <p>Last Updated: January 2025</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <p class="text-gray-400">
                &copy; 2025 NXSys AI. All rights reserved.
            </p>
        </div>
    </footer>
</body>
</html>
```

---

### Step 2: Create the Terms of Service Page

**Create a new file:**
1. Open your text editor
2. Click **File → New File**
3. Save it as `terms.html` in the same folder as `index.html`

**Copy and paste this template:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - NXSys AI">
    <title>Terms of Service - NXSys AI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        * {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center space-x-2">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-600 to-purple-600 rounded-full flex items-center justify-center">
                    <i class="fas fa-brain text-white text-lg"></i>
                </div>
                <a href="index.html" class="text-xl font-bold text-gray-900">NXSys AI</a>
            </div>
            <a href="index.html" class="text-gray-700 hover:text-blue-600 font-medium">← Back to Home</a>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-20 md:py-24 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Terms of Service</h1>
            
            <div class="prose prose-lg max-w-none space-y-8 text-gray-700">
                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Agreement to Terms</h2>
                    <p>
                        By accessing and using this website and service, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Use License</h2>
                    <p>
                        Permission is granted to temporarily download one copy of the materials (information or software) on NXSys AI's website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                    </p>
                    <ul class="list-disc list-inside space-y-2">
                        <li>Modifying or copying the materials</li>
                        <li>Using the materials for any commercial purpose or for any public display</li>
                        <li>Attempting to decompile or reverse engineer any software contained on the website</li>
                        <li>Removing any copyright or other proprietary notations from the materials</li>
                        <li>Transferring the materials to another person or "mirroring" the materials on any other server</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">3. Disclaimer</h2>
                    <p>
                        The materials on NXSys AI's website are provided on an 'as is' basis. NXSys AI makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Limitations</h2>
                    <p>
                        In no event shall NXSys AI or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on NXSys AI's website.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Accuracy of Materials</h2>
                    <p>
                        The materials appearing on NXSys AI's website could include technical, typographical, or photographic errors. NXSys AI does not warrant that any of the materials on its website are accurate, complete, or current. NXSys AI may make changes to the materials contained on its website at any time without notice.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Links</h2>
                    <p>
                        NXSys AI has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by NXSys AI of the site. Use of any such linked website is at the user's own risk.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">7. Modifications</h2>
                    <p>
                        NXSys AI may revise these terms of service for its website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">8. Governing Law</h2>
                    <p>
                        These terms and conditions are governed by and construed in accordance with the laws of the jurisdiction in which NXSys AI operates, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">9. Contact Information</h2>
                    <p>
                        If you have any questions about these Terms of Service, please contact us at:
                    </p>
                    <p class="text-blue-600 font-semibold">
                        <a href="mailto:ecomm@nxsys.com.au">ecomm@nxsys.com.au</a>
                    </p>
                </div>

                <div class="text-sm text-gray-600 pt-8 border-t border-gray-200">
                    <p>Last Updated: January 2025</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <p class="text-gray-400">
                &copy; 2025 NXSys AI. All rights reserved.
            </p>
        </div>
    </footer>
</body>
</html>
```

---

### Step 3: Verify Links Are Working

Now that you've created the files, the footer links should work automatically. Let's verify:

**In `index.html` (lines 932-933), you should already have:**
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-blue-400 smooth-transition">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-blue-400 smooth-transition">Terms of Service</a></li>
```

**These links are already correct!** They point to the files you just created.

---

### Step 4: Customize the Policy Pages

Both template pages include placeholder content. You should customize them with your actual policies:

**In `privacy.html`, update:**
- Email address in section 6
- "Last Updated" date

**In `terms.html`, update:**
- Email address in section 9
- "Last Updated" date
- Jurisdiction/governing law in section 8

---

### Step 5: Test the Links

1. Open `index.html` in your browser
2. Scroll to the footer
3. Click on "Privacy Policy" - should open `privacy.html`
4. Click on "Terms of Service" - should open `terms.html`
5. On those pages, click "← Back to Home" to return to `index.html`

**If links don't work:**
- Make sure all three files (`index.html`, `privacy.html`, `terms.html`) are in the same folder
- Check that filenames match exactly (case-sensitive on some systems)
- Try refreshing the browser (Ctrl+R or Cmd+R)

---

### File Structure After Completion

```
your-project-folder/
├── index.html          ✅ Main landing page (already exists)
├── privacy.html        ✅ Privacy policy (newly created)
├── terms.html          ✅ Terms of service (newly created)
└── blog.html           (Optional - create if you link to it)
```

---

## Common Customizations

### 1. Change Company Name Throughout the Page

**Search for "NXSys AI" and replace with your company name:**

Locations:
- Line 63: Logo text
- Line 906: Footer company name
- Line 911: Footer description
- Line 950: Footer copyright
- All `<title>` tags in HTML files

**Using Find & Replace (Ctrl+H):**
1. Find: `NXSys AI`
2. Replace with: `Your Company Name`
3. Click "Replace All"

---

### 2. Change the Logo Icon

**Current icon (line 64):**
```html
<i class="fas fa-brain text-white text-lg"></i>
```

**To change it, replace `fa-brain` with another Font Awesome icon:**

Popular alternatives:
- `fa-rocket` - Rocket
- `fa-bolt` - Lightning bolt
- `fa-star` - Star
- `fa-cube` - Cube
- `fa-cog` - Gear
- `fa-zap` - Zap

**Example - Change to rocket:**
```html
<i class="fas fa-rocket text-white text-lg"></i>
```

**Find all instances and replace:**
- Line 64 (header logo)
- Line 907 (footer logo)
- Also update in `privacy.html` and `terms.html` if created

---

### 3. Add New Feature Cards

**To add a 4th feature, copy this template and insert after the 3rd feature (around line 340):**

```html
<!-- Feature 4: New Feature -->
<div class="bg-white rounded-2xl p-8 border border-gray-100 hover:border-green-300 hover:shadow-xl smooth-transition hover:scale-105 group">
    <div class="w-14 h-14 bg-gradient-to-br from-green-100 to-green-50 rounded-2xl flex items-center justify-center mb-6 group-hover:from-green-200 group-hover:to-green-100 smooth-transition">
        <svg class="w-7 h-7 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
        </svg>
    </div>
    <h3 class="text-xl font-bold text-gray-900 mb-3">Your Feature Title</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Your feature description goes here. Explain what this feature does and how it benefits users.
    </p>
    <ul class="space-y-2 text-sm text-gray-600">
        <li class="flex items-center space-x-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Benefit 1</span>
        </li>
        <li class="flex items-center space-x-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Benefit 2</span>
        </li>
        <li class="flex items-center space-x-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Benefit 3</span>
        </li>
    </ul>
</div>
```

**Then update the grid to show 4 columns instead of 3 (line 247):**

```html
<!-- BEFORE -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">

<!-- AFTER -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
```

---

### 4. Change Hero Image/Visual

The hero section has a decorative box on the right (lines 160-189). To customize:

**Option A: Change the colors**
```html
<!-- BEFORE -->
<div class="absolute inset-0 bg-gradient-to-br from-blue-400 to-purple-600 rounded-3xl opacity-10 blur-2xl"></div>

<!-- AFTER - Change colors -->
<div class="absolute inset-0 bg-gradient-to-br from-green-400 to-teal-600 rounded-3xl opacity-10 blur-2xl"></div>
```

**Option B: Replace with your own image**
```html
<!-- Replace the entire decorative box with an image -->
<img src="your-image.png" alt="Dashboard Preview" class="w-full h-full object-cover rounded-3xl shadow-2xl">
```

---

### 5. Update Testimonials

**To update a testimonial, find the testimonial section (lines 512-620) and modify:**

```html
<!-- Find this testimonial -->
<p class="text-gray-700 leading-relaxed mb-6 text-lg">
    "NXSys AI transformed our operations overnight..."
</p>

<!-- Replace with your testimonial -->
<p class="text-gray-700 leading-relaxed mb-6 text-lg">
    "Your customer's quote goes here..."
</p>

<!-- Update the initials -->
<div class="w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-600 rounded-full...">
    SJ  <!-- Change these initials -->
</div>

<!-- Update the name and title -->
<p class="font-bold text-gray-900">Sarah Johnson</p>
<p class="text-sm text-gray-600">VP of Operations, TechCorp Solutions</p>
```

---

### 6. Add a New Section

**To add a new section (e.g., Pricing), copy this template:**

```html
<!-- Pricing Section -->
<section id="pricing" class="py-20 md:py-24 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
            <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-4">
                Simple, Transparent Pricing
            </h2>
            <p class="text-lg text-gray-600 max-w-3xl mx-auto">
                Choose the plan that fits your needs.
            </p>
        </div>

        <!-- Your pricing cards here -->
    </div>
</section>
```

**Then add the link to your navigation (line 70):**
```html
<a href="#pricing" class="text-gray-700 hover:text-blue-600 smooth-transition font-medium">Pricing</a>
```

---

### 7. Change Button Colors

**Find any button with:**
```html
class="bg-gradient-to-r from-blue-600 to-purple-600..."
```

**Change the colors:**
```html
<!-- Change to green-orange gradient -->
class="bg-gradient-to-r from-green-600 to-orange-600..."

<!-- Change to solid color -->
class="bg-blue-600..."
```

---

### 8. Modify Mobile Menu

The mobile menu is hidden by default and shows when the hamburger icon is clicked. To customize:

**Change the menu items (lines 76-82):**
```html
<div class="mobile-menu hidden absolute top-full left-0 right-0 bg-white shadow-lg md:hidden">
    <div class="flex flex-col space-y-4 p-6">
        <!-- Add or remove menu items here -->
    </div>
</div>
```

---

### 9. Update Meta Tags (SEO)

**For better search engine optimization, update these in the `<head>` section (lines 5-7):**

```html
<!-- BEFORE -->
<meta name="description" content="Unleash AI's Power for Your Business Growth...">
<meta name="keywords" content="AI, Business Growth, Automation, Analytics, Integration">
<meta name="author" content="NXSys">

<!-- AFTER - Your own content -->
<meta name="description" content="Your company description - make it compelling and under 160 characters">
<meta name="keywords" content="your, keywords, here, separated, by, commas">
<meta name="author" content="Your Company Name">
```

---

## Troubleshooting

### Problem: Links not working

**Symptoms:** Clicking links does nothing or shows 404 error

**Solutions:**
1. **Check file names** - Make sure `privacy.html`, `terms.html`, etc. exist in the same folder as `index.html`
2. **Check spelling** - Filenames must match exactly (case-sensitive on Mac/Linux)
3. **Check href attribute** - Make sure the `href` value matches the filename exactly
4. **Clear browser cache** - Press Ctrl+Shift+Delete and clear cache, then refresh

---

### Problem: Styling looks broken

**Symptoms:** Colors are wrong, layout is messed up, text is too big/small

**Solutions:**
1. **Check Tailwind CDN** - Make sure this line is in the `<head>`:
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```
2. **Check class names** - Make sure you didn't accidentally delete or misspell Tailwind classes
3. **Check for typos** - Look for missing hyphens in class names (e.g., `bg-blue-600` not `bg-blue600`)
4. **Refresh browser** - Press Ctrl+F5 (Cmd+Shift+R on Mac) for a hard refresh

---

### Problem: Mobile menu doesn't work

**Symptoms:** Hamburger icon doesn't open menu on mobile

**Solutions:**
1. **Check JavaScript** - Make sure the script section (lines 1006-1050) is intact
2. **Check selectors** - Make sure the `.mobile-menu-button` and `.mobile-menu` classes exist
3. **Test in browser** - Open browser developer tools (F12) and check for JavaScript errors in console

---

### Problem: Images or icons not showing

**Symptoms:** Blank spaces where icons should be, images don't appear

**Solutions:**
1. **Check Font Awesome CDN** - Make sure this line is in the `<head>`:
   ```html
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
   ```
2. **Check icon names** - Make sure icon classes like `fa-brain`, `fa-star` are spelled correctly
3. **Check image paths** - If using custom images, make sure the file path is correct

---

### Problem: Page looks different on mobile

**Symptoms:** Layout breaks on phone, text is too small/large

**Solutions:**
1. **Check viewport meta tag** - Should be in `<head>`:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
2. **Test responsive design** - Open browser developer tools (F12) and use device preview
3. **Check responsive classes** - Make sure `md:` and `lg:` prefixes are present for breakpoints

---

### Problem: Gradient colors not showing

**Symptoms:** Gradient backgrounds appear as solid colors

**Solutions:**
1. **Check class format** - Gradients need the full class:
   ```html
   <!-- CORRECT -->
   class="bg-gradient-to-r from-blue-600 to-purple-600"
   
   <!-- WRONG -->
   class="bg-gradient from-blue-600 to-purple-600"
   ```
2. **Check color names** - Make sure color names are valid Tailwind colors
3. **Check browser support** - Gradients work in all modern browsers

---

### Problem: FAQ accordion doesn't expand

**Symptoms:** Clicking FAQ questions doesn't show answers

**Solutions:**
1. **Check JavaScript** - Look for errors in browser console (F12)
2. **Check class names** - Make sure `.faq-item`, `.faq-question`, `.faq-answer` classes are correct
3. **Check HTML structure** - Each FAQ item must have the correct structure with question and answer divs

---

### Problem: Forms not submitting

**Symptoms:** Form submission doesn't work, no confirmation

**Solutions:**
1. **Note:** This landing page doesn't have a form. To add one, you'll need a backend service
2. **Use a form service** - Try Formspree, Netlify Forms, or EmailJS
3. **Contact your developer** - If you need form functionality, consult a developer

---

### Problem: Page loading slowly

**Symptoms:** Page takes a long time to load

**Solutions:**
1. **Check file size** - Optimize images (use JPG/WebP instead of PNG)
2. **Check CDN** - Make sure Tailwind and Font Awesome CDNs are loading (check in browser Network tab)
3. **Minimize custom images** - Reduce number of large images on page
4. **Enable caching** - If hosting on a server, enable browser caching

---

### Problem: Text content shows but styling doesn't apply

**Symptoms:** Can see words but colors/fonts are wrong

**Solutions:**
1. **Verify Tailwind is loading** - Check browser console for CDN errors
2. **Check class syntax** - Tailwind classes must be complete and exact
3. **Clear browser cache** - Ctrl+Shift+Delete to clear cache
4. **Check for conflicting CSS** - Make sure no other CSS files override Tailwind

---

## Summary Checklist

Before launching your landing page, ensure you've completed:

- [ ] Updated company name throughout
- [ ] Changed all placeholder links (`https://test.com`)
- [ ] Updated email address in footer and links
- [ ] Created `privacy.html` file
- [ ] Created `terms.html` file
- [ ] Updated social media links
- [ ] Customized hero headline and description
- [ ] Updated feature titles and descriptions
- [ ] Customized testimonials with real quotes
- [ ] Updated "About Us" section with your story
- [ ] Updated FAQ with your questions/answers
- [ ] Tested all links on desktop and mobile
- [ ] Tested FAQ accordion functionality
- [ ] Tested mobile menu
- [ ] Verified styling displays correctly
- [ ] Updated meta description for SEO
- [ ] Checked page speed
- [ ] Tested on multiple browsers

---

## Additional Resources

### Tailwind CSS Documentation
- **Official Docs:** https://tailwindcss.com/docs
- **Color Reference:** https://tailwindcss.com/docs/customizing-colors
- **Responsive Design:** https://tailwindcss.com/docs/responsive-design

### Font Awesome Icons
- **Icon Library:** https://fontawesome.com/icons
- **Search for icons:** https://fontawesome.com/search

### HTML & CSS Learning
- **MDN Web Docs:** https://developer.mozilla.org/
- **W3Schools:** https://www.w3schools.com/
- **Codecademy:** https://www.codecademy.com/

### Text Editors
- **VS Code:** https://code.visualstudio.com/ (Recommended)
- **Sublime Text:** https://www.sublimetext.com/
- **Notepad++:** https://notepad-plus-plus.org/

---

## Need Help?

If you encounter issues not covered in this guide:

1. **Check the HTML comments** - Look for `<!-- ... -->` comments in the code
2. **Use browser developer tools** - Press F12 to open and check console for errors
3. **Validate your HTML** - Use https://validator.w3.org/
4. **Search online** - Search for specific error messages
5. **Contact support** - Reach out to your developer or technical support

---

**Document Version:** 1.0  
**Last Updated:** January 2025  
**Compatible With:** All modern browsers (Chrome, Firefox, Safari, Edge)