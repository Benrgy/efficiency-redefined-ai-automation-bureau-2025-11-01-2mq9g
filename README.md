# AI Automation Bureau Landing Page - Maintenance & Customization Guide

A comprehensive guide for maintaining, updating, and customizing your AI Automation Bureau landing page.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Understanding the Page Structure](#understanding-the-page-structure)
3. [Updating Text Content](#updating-text-content)
4. [Modifying Styles with Tailwind CSS](#modifying-styles-with-tailwind-css)
5. [Fixing and Managing Links](#fixing-and-managing-links)
6. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
7. [Common Tasks & Troubleshooting](#common-tasks--troubleshooting)
8. [Best Practices](#best-practices)

---

## Getting Started

### What You Need to Know

This landing page is built with:
- **HTML**: The structure and content of the page
- **Tailwind CSS**: A utility-first CSS framework that controls styling (colors, spacing, fonts, etc.)
- **Font Awesome**: An icon library (the small graphics you see throughout)
- **Vanilla JavaScript**: Simple interactions like mobile menu toggle and FAQ accordion

### Files You'll Work With

```
your-project/
├── index.html          ← Main landing page (what you're editing)
├── privacy.html        ← Privacy policy page (you'll create this)
├── terms.html          ← Terms of service page (you'll create this)
├── blog.html           ← Blog page (optional)
└── assets/             ← Folder for images (if needed)
```

### How to Edit Files

1. **Open in a Text Editor**: Use a code editor like:
   - Visual Studio Code (free, recommended)
   - Sublime Text
   - Notepad++ (Windows)
   - Or even basic Notepad (not ideal, but works)

2. **Save Changes**: After editing, save the file with `Ctrl+S` (Windows) or `Cmd+S` (Mac)

3. **View Changes**: Open the HTML file in your web browser to see updates immediately

---

## Understanding the Page Structure

### Main Sections of Your Landing Page

Your landing page is organized into distinct sections. Here's what each contains:

```
1. HEADER NAVIGATION (Lines 67-110)
   ├── Logo and brand name
   ├── Desktop navigation menu
   ├── CTA button ("Get Started")
   └── Mobile menu (hidden on small screens)

2. HERO SECTION (Lines 112-177)
   ├── Main headline ("Efficiency Redefined")
   ├── Subheading
   ├── Call-to-action buttons
   └── Decorative illustration area

3. FEATURES SECTION (Lines 179-275)
   ├── Three feature cards:
   │   ├── Task Automation
   │   ├── Intelligent Document Processing
   │   └── Virtual Assistants

4. BENEFITS SECTION (Lines 277-361)
   ├── Three benefit cards:
   │   ├── Free Up Staff Time
   │   ├── Improve Accuracy
   │   └── Accelerate Workflows

5. CTA SECTION (Lines 363-385)
   └── Large call-to-action with background image

6. TESTIMONIALS SECTION (Lines 387-500)
   ├── Four customer testimonials
   └── Star ratings and customer info

7. ABOUT SECTION (Lines 502-535)
   └── Company background information

8. FAQ SECTION (Lines 537-706)
   ├── Five expandable FAQ items
   └── JavaScript-powered accordion

9. FOOTER (Lines 708-805)
   ├── Footer navigation
   ├── Contact information
   └── Social media links
```

### Key Concept: HTML Structure

Think of HTML like a document outline:
- `<section>` = A major section of content
- `<div>` = A container holding content
- `<h1>, <h2>, <h3>` = Headings (h1 is largest, h3 is smaller)
- `<p>` = Paragraph of text
- `<a>` = A link
- `<button>` = A clickable button

---

## Updating Text Content

### 1. Changing the Page Title & Meta Description

**Location**: Lines 7-9 (inside the `<head>` section)

**Current Code**:
```html
<meta name="description" content="Efficiency Redefined: AI Automation Bureau - Empower your team with intelligent automation solutions">
<meta name="keywords" content="AI automation, document processing, virtual assistants, workflow automation">
<title>Efficiency Redefined: AI Automation Bureau</title>
```

**What These Do**:
- `description`: Appears in Google search results (160 characters max)
- `keywords`: Helps search engines understand your page topic
- `title`: Appears in browser tab and search results

**How to Update**:
1. Find these three lines
2. Replace the text in the `content="..."` sections with your own
3. Keep the quotation marks and structure the same

**Example**:
```html
<meta name="description" content="Transform your business with intelligent automation solutions">
<meta name="keywords" content="workflow automation, AI solutions, business efficiency">
<title>Your Company Name - Automation Solutions</title>
```

---

### 2. Updating the Logo & Brand Name

**Location**: Lines 79-84 (Header section)

**Current Code**:
```html
<div class="flex items-center space-x-2">
    <div class="w-10 h-10 bg-green-500 rounded-lg flex items-center justify-center transform -rotate-12">
        <i class="fas fa-bolt text-white text-lg font-bold"></i>
    </div>
    <span class="text-xl font-bold text-gray-900 hidden sm:inline">AI Automation Bureau</span>
</div>
```

**How to Update**:

**Option 1: Change the Text Only**
```html
<span class="text-xl font-bold text-gray-900 hidden sm:inline">Your Company Name</span>
```

**Option 2: Change the Icon**
The `<i class="fas fa-bolt">` is a Font Awesome icon. Find other icons at [fontawesome.com](https://fontawesome.com/icons). Replace `fa-bolt` with any other icon name:
```html
<i class="fas fa-rocket text-white text-lg font-bold"></i>  <!-- Rocket icon -->
<i class="fas fa-star text-white text-lg font-bold"></i>    <!-- Star icon -->
<i class="fas fa-zap text-white text-lg font-bold"></i>     <!-- Zap icon -->
```

---

### 3. Updating the Hero Section (Main Headline)

**Location**: Lines 131-157

**Current Code**:
```html
<h1 class="text-5xl sm:text-6xl lg:text-7xl font-black text-gray-900 mb-6 leading-tight tracking-tight">
    Efficiency <span class="text-green-600">Redefined</span>
</h1>

<p class="text-xl sm:text-2xl text-gray-700 mb-8 leading-relaxed font-light">
    Say goodbye to repetitive tasks. Our AI automation bureau empowers your team to focus on what truly matters—growing your business and delivering exceptional value.
</p>
```

**How to Update**:
1. Change the text inside `<h1>` to your main headline
2. The `<span class="text-green-600">` makes text green - keep this for emphasis or remove it
3. Update the paragraph text below

**Example**:
```html
<h1 class="text-5xl sm:text-6xl lg:text-7xl font-black text-gray-900 mb-6 leading-tight tracking-tight">
    Transform Your <span class="text-green-600">Business Today</span>
</h1>

<p class="text-xl sm:text-2xl text-gray-700 mb-8 leading-relaxed font-light">
    Automate your workflows and boost productivity with our intelligent solutions.
</p>
```

---

### 4. Updating Feature Cards

**Location**: Lines 197-275 (Features Section)

Each feature card has this structure:

**Current Code** (Feature 1 example):
```html
<div class="feature-card p-8 rounded-2xl retro-border hover-lift">
    <div class="w-16 h-16 bg-green-100 rounded-xl flex items-center justify-center mb-6 border-2 border-green-400">
        <i class="fas fa-cogs text-green-600 text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-4">Task Automation</h3>
    <p class="text-gray-700 leading-relaxed mb-4">
        Automate repetitive tasks with intelligent workflows...
    </p>
    <ul class="space-y-3">
        <li class="flex items-start">
            <i class="fas fa-check text-green-600 mt-1 mr-3 font-bold"></i>
            <span class="text-gray-700">Intelligent workflow orchestration</span>
        </li>
        <!-- More list items -->
    </ul>
</div>
```

**How to Update**:

1. **Change the Icon**: Replace `fa-cogs` with another Font Awesome icon
   ```html
   <i class="fas fa-cogs text-green-600 text-2xl"></i>
   ```

2. **Change the Title**:
   ```html
   <h3 class="text-2xl font-bold text-gray-900 mb-4">Task Automation</h3>
   ```

3. **Change the Description**:
   ```html
   <p class="text-gray-700 leading-relaxed mb-4">
       Your new description here...
   </p>
   ```

4. **Update the Bullet Points**: Each list item is inside `<li>` tags
   ```html
   <li class="flex items-start">
       <i class="fas fa-check text-green-600 mt-1 mr-3 font-bold"></i>
       <span class="text-gray-700">Your bullet point text</span>
   </li>
   ```

**Complete Example**:
```html
<div class="feature-card p-8 rounded-2xl retro-border hover-lift">
    <div class="w-16 h-16 bg-green-100 rounded-xl flex items-center justify-center mb-6 border-2 border-green-400">
        <i class="fas fa-rocket text-green-600 text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-4">Speed Optimization</h3>
    <p class="text-gray-700 leading-relaxed mb-4">
        Process tasks faster than ever before with our optimized algorithms.
    </p>
    <ul class="space-y-3">
        <li class="flex items-start">
            <i class="fas fa-check text-green-600 mt-1 mr-3 font-bold"></i>
            <span class="text-gray-700">Lightning-fast processing</span>
        </li>
    </ul>
</div>
```

---

### 5. Updating Benefit Cards

**Location**: Lines 296-361 (Benefits Section)

**Current Code** (Benefit 1 example):
```html
<div class="benefit-item bg-white p-8 rounded-2xl border-3 border-green-400 retro-shadow hover-lift">
    <div class="flex items-start mb-6">
        <div class="w-14 h-14 bg-green-500 rounded-full flex items-center justify-center mr-4 flex-shrink-0">
            <i class="fas fa-clock text-white text-xl"></i>
        </div>
        <h3 class="text-2xl font-bold text-gray-900">Free Up Staff Time</h3>
    </div>
    <p class="text-gray-700 leading-relaxed mb-6">
        Reclaim an average of 15-20 hours per employee per week...
    </p>
    <div class="bg-green-50 p-4 rounded-lg border-l-4 border-green-500">
        <p class="text-green-900 font-semibold text-lg">Up to 40% productivity increase</p>
        <p class="text-green-700 text-sm mt-1">Average client improvement in first 90 days</p>
    </div>
</div>
```

**How to Update**:

1. **Change the Icon**:
   ```html
   <i class="fas fa-clock text-white text-xl"></i>
   ```

2. **Change the Title**:
   ```html
   <h3 class="text-2xl font-bold text-gray-900">Free Up Staff Time</h3>
   ```

3. **Change the Main Description**:
   ```html
   <p class="text-gray-700 leading-relaxed mb-6">
       Your new description...
   </p>
   ```

4. **Update the Highlight Box** (the colored box at the bottom):
   ```html
   <p class="text-green-900 font-semibold text-lg">Your main stat</p>
   <p class="text-green-700 text-sm mt-1">Your supporting text</p>
   ```

---

### 6. Updating Testimonials

**Location**: Lines 420-500 (Testimonials Section)

**Current Code** (Testimonial 1 example):
```html
<div class="testimonial-card p-8 rounded-2xl hover-lift">
    <div class="flex items-center mb-4">
        <div class="star-rating flex gap-1">
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
        </div>
    </div>
    <p class="text-gray-700 leading-relaxed mb-6 text-lg">
        "The AI Automation Bureau completely transformed our document processing workflow..."
    </p>
    <div class="flex items-center">
        <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mr-4 border-2 border-green-400">
            <i class="fas fa-user text-green-600 text-lg"></i>
        </div>
        <div>
            <p class="font-bold text-gray-900">Sarah Mitchell</p>
            <p class="text-gray-600 text-sm">Finance Director, TechFlow Inc.</p>
        </div>
    </div>
</div>
```

**How to Update**:

1. **Change Star Rating**: Remove or add `<i class="fas fa-star text-lg"></i>` lines (5 = 5 stars)
   ```html
   <!-- 4 stars instead of 5 -->
   <i class="fas fa-star text-lg"></i>
   <i class="fas fa-star text-lg"></i>
   <i class="fas fa-star text-lg"></i>
   <i class="fas fa-star text-lg"></i>
   ```

2. **Change Quote Text**:
   ```html
   <p class="text-gray-700 leading-relaxed mb-6 text-lg">
       "Your customer's quote here..."
   </p>
   ```

3. **Change Customer Name & Title**:
   ```html
   <p class="font-bold text-gray-900">John Smith</p>
   <p class="text-gray-600 text-sm">CEO, Company Name</p>
   ```

---

### 7. Updating FAQ Items

**Location**: Lines 569-706 (FAQ Section)

**Current Code** (FAQ Item 1 example):
```html
<div class="faq-item bg-white border-2 border-gray-200 rounded-xl overflow-hidden hover:border-green-400 transition-all duration-300">
    <div class="faq-question p-6 sm:p-8 cursor-pointer hover:bg-green-50 transition-colors duration-300">
        <div class="flex items-center justify-between">
            <h3 class="text-lg sm:text-xl font-bold text-gray-900">How long does it take to implement the AI automation platform?</h3>
            <i class="faq-icon fas fa-chevron-down text-green-600 text-lg font-bold transition-transform duration-300"></i>
        </div>
    </div>
    <div class="faq-answer hidden px-6 sm:px-8 pb-6 sm:pb-8 border-t-2 border-gray-200 bg-gray-50">
        <p class="text-gray-700 leading-relaxed">
            Most implementations are completed within 2-4 weeks...
        </p>
    </div>
</div>
```

**How to Update**:

1. **Change the Question**:
   ```html
   <h3 class="text-lg sm:text-xl font-bold text-gray-900">Your new question?</h3>
   ```

2. **Change the Answer**:
   ```html
   <div class="faq-answer hidden px-6 sm:px-8 pb-6 sm:pb-8 border-t-2 border-gray-200 bg-gray-50">
       <p class="text-gray-700 leading-relaxed">
           Your answer here...
       </p>
   </div>
   ```

3. **Keep the `hidden` class** - it hides the answer until clicked

---

### 8. Updating Footer Information

**Location**: Lines 808-900 (Footer Section)

**Current Code** (Contact section example):
```html
<div class="flex items-start">
    <i class="fas fa-envelope text-green-500 mr-3 mt-1"></i>
    <div>
        <p class="text-gray-400 text-sm">Email</p>
        <a href="mailto:bengrauwde@hotmail.com" class="text-white font-semibold hover:text-green-500 transition-colors duration-300">bengrauwde@hotmail.com</a>
    </div>
</div>
```

**How to Update**:

1. **Change Email Address**:
   ```html
   <a href="mailto:your-email@example.com">your-email@example.com</a>
   ```

2. **Change Phone Number**:
   ```html
   <p class="text-white font-semibold">+1 (555) 987-6543</p>
   ```

3. **Change Office Location**:
   ```html
   <p class="text-white font-semibold">New York, NY</p>
   ```

4. **Update Copyright Year**:
   ```html
   <p class="text-gray-400 text-sm mb-4 sm:mb-0">
       &copy; 2025 Your Company Name. All rights reserved.
   </p>
   ```

---

## Modifying Styles with Tailwind CSS

### Understanding Tailwind CSS

Tailwind CSS uses **utility classes** to style elements. Instead of writing custom CSS, you add class names directly to HTML elements.

### Common Tailwind Classes Explained

**Text Styling**:
```html
<!-- Font sizes -->
<h1 class="text-5xl">Large heading (5xl)</h1>
<p class="text-lg">Large paragraph</p>
<span class="text-sm">Small text</span>

<!-- Font weight -->
<p class="font-light">Light weight (thin)</p>
<p class="font-bold">Bold weight</p>
<p class="font-black">Extra bold weight</p>

<!-- Text color -->
<p class="text-gray-900">Dark gray text</p>
<p class="text-green-600">Green text</p>
<p class="text-white">White text</p>
```

**Spacing**:
```html
<!-- Margin (space outside) -->
<div class="mb-6">Margin bottom of 6 units</div>
<div class="mt-4">Margin top of 4 units</div>
<div class="ml-8">Margin left of 8 units</div>

<!-- Padding (space inside) -->
<div class="p-8">Padding all sides</div>
<div class="px-6">Padding left and right</div>
<div class="py-4">Padding top and bottom</div>
```

**Background Colors**:
```html
<!-- Background color -->
<div class="bg-white">White background</div>
<div class="bg-green-500">Green background</div>
<div class="bg-gray-50">Light gray background</div>
```

**Sizing**:
```html
<!-- Width and height -->
<div class="w-16 h-16">16x16 unit square</div>
<div class="w-full">Full width</div>
<div class="max-w-4xl">Maximum width of 4xl</div>
```

**Borders**:
```html
<!-- Border styling -->
<div class="border-2 border-green-400">2px green border</div>
<div class="rounded-lg">Rounded corners (large)</div>
<div class="rounded-2xl">Rounded corners (extra large)</div>
```

### Common Customization Tasks

#### Task 1: Change the Primary Color (Green to Blue)

The landing page uses green (`#22c55e`) throughout. To change it to blue:

1. **Find the CSS custom styles** (Lines 15-64)
2. **Replace all green color codes**:

**Current**:
```css
.retro-border {
    border: 3px solid #22c55e;
    box-shadow: 6px 6px 0px rgba(34, 197, 94, 0.2);
}

.cta-button {
    background-color: #22c55e;
    border: 3px solid #22c55e;
}
```

**Changed to Blue**:
```css
.retro-border {
    border: 3px solid #3b82f6;  /* Blue instead of green */
    box-shadow: 6px 6px 0px rgba(59, 130, 246, 0.2);
}

.cta-button {
    background-color: #3b82f6;  /* Blue instead of green */
    border: 3px solid #3b82f6;
}
```

3. **Replace Tailwind color classes**: Change `text-green-600` to `text-blue-600`, `bg-green-500` to `bg-blue-500`, etc.

**Example**:
```html
<!-- Before (Green) -->
<h1 class="text-green-600">Efficiency Redefined</h1>

<!-- After (Blue) -->
<h1 class="text-blue-600">Efficiency Redefined</h1>
```

**Color Reference**:
- Green: `#22c55e`, `#16a34a`, `#dcfce7`
- Blue: `#3b82f6`, `#1d4ed8`, `#dbeafe`
- Red: `#ef4444`, `#b91c1c`, `#fee2e2`
- Purple: `#a855f7`, `#6d28d9`, `#f3e8ff`

---

#### Task 2: Change Text Size

**Current**:
```html
<h1 class="text-5xl sm:text-6xl lg:text-7xl">Efficiency Redefined</h1>
```

This means:
- `text-5xl` = 5xl size on mobile
- `sm:text-6xl` = 6xl size on small screens
- `lg:text-7xl` = 7xl size on large screens

**To make it smaller**:
```html
<h1 class="text-3xl sm:text-4xl lg:text-5xl">Efficiency Redefined</h1>
```

**Size Scale** (from smallest to largest):
- `text-xs`, `text-sm`, `text-base`, `text-lg`, `text-xl`
- `text-2xl`, `text-3xl`, `text-4xl`, `text-5xl`, `text-6xl`, `text-7xl`

---

#### Task 3: Add More Spacing Between Sections

**Current**:
```html
<section class="py-20 sm:py-24 lg:py-32">
```

This means: padding top and bottom of 20 units (mobile), 24 units (small screens), 32 units (large screens).

**To add more space**:
```html
<section class="py-24 sm:py-32 lg:py-40">
```

---

#### Task 4: Change Button Styling

**Current Button**:
```html
<a href="https://test.com" class="cta-button px-8 py-4 rounded-lg font-bold text-lg">
    Start Your Automation Journey
</a>
```

**To make it wider**:
```html
<a href="https://test.com" class="cta-button px-12 py-4 rounded-lg font-bold text-lg">
    Start Your Automation Journey
</a>
```

**To make it taller**:
```html
<a href="https://test.com" class="cta-button px-8 py-6 rounded-lg font-bold text-lg">
    Start Your Automation Journey
</a>
```

**To make corners more rounded**:
```html
<a href="https://test.com" class="cta-button px-8 py-4 rounded-2xl font-bold text-lg">
    Start Your Automation Journey
</a>
```

---

### Responsive Design Explained

Tailwind uses **breakpoints** for responsive design:

```html
<div class="hidden md:flex">
    This is hidden on mobile, visible on medium screens and up
</div>

<p class="text-lg md:text-xl lg:text-2xl">
    Large on mobile, extra large on medium screens, 2xl on large screens
</p>
```

**Breakpoints**:
- No prefix = Mobile (default)
- `sm:` = 640px and up (small tablets)
- `md:` = 768px and up (tablets)
- `lg:` = 1024px and up (desktops)
- `xl:` = 1280px and up (large desktops)

---

## Fixing and Managing Links

### Understanding Links in Your Page

Links connect your pages together. There are two types:

1. **Internal Links**: Point to pages on your own website
   ```html
   <a href="privacy.html">Privacy Policy</a>
   ```

2. **External Links**: Point to other websites
   ```html
   <a href="https://example.com">External Site</a>
   ```

---

### Finding All Links in Your Page

Here are all the links in your landing page that need checking/updating:

#### Header Navigation Links (Lines 86-94)

**Current Code**:
```html
<a href="#features" class="text-gray-700 font-semibold hover:text-green-600">Features</a>
<a href="#benefits" class="text-gray-700 font-semibold hover:text-green-600">Benefits</a>
<a href="#testimonials" class="text-gray-700 font-semibold hover:text-green-600">Testimonials</a>
<a href="#faq" class="text-gray-700 font-semibold hover:text-green-600">FAQ</a>
```

**What These Do**: These links jump to sections on the same page using the `#` symbol
- `#features` jumps to the Features section
- `#benefits` jumps to the Benefits section
- etc.

**Status**: ✅ These are correct and don't need changes

---

#### CTA Buttons (Multiple Locations)

**Location 1**: Header - Line 99
```html
<a href="https://test.com" class="cta-button px-6 py-2 rounded-lg">Get Started</a>
```

**Location 2**: Hero Section - Line 149
```html
<a href="https://test.com" class="cta-button px-8 py-4 rounded-lg">Start Your Automation Journey</a>
```

**Location 3**: Mobile Menu - Line 108
```html
<a href="https://test.com" class="cta-button px-6 py-2 rounded-lg mt-4 w-full text-center">Get Started</a>
```

**Location 4**: CTA Section - Line 374
```html
<a href="https://test.com" class="bg-white text-green-600 px-8 py-4 rounded-lg">Start Free Trial</a>
```

**What These Do**: These buttons currently point to `https://test.com`, which is a placeholder

**How to Fix**:
1. Replace `https://test.com` with your actual URL
2. Keep the `https://` part
3. Make sure to update ALL instances

**Example**:
```html
<!-- Before -->
<a href="https://test.com" class="cta-button px-8 py-4 rounded-lg">Start Your Automation Journey</a>

<!-- After -->
<a href="https://your-website.com/signup" class="cta-button px-8 py-4 rounded-lg">Start Your Automation Journey</a>
```

---

#### Footer Navigation Links

**Location**: Lines 740-786 (Footer)

**Product Links** (Line 745):
```html
<li><a href="#features" class="text-gray-400 hover:text-green-500">Features</a></li>
<li><a href="#benefits" class="text-gray-400 hover:text-green-500">Benefits</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Pricing</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Security</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Roadmap</a></li>
```

**Status**: ⚠️ Some need updating
- `#features` and `#benefits` = ✅ Correct (internal links)
- `#` = ❌ Placeholder links (need URLs)

**How to Fix**:
```html
<!-- Before -->
<li><a href="#" class="text-gray-400 hover:text-green-500">Pricing</a></li>

<!-- After -->
<li><a href="/pricing.html" class="text-gray-400 hover:text-green-500">Pricing</a></li>
```

---

**Company Links** (Lines 755-761):
```html
<li><a href="#" class="text-gray-400 hover:text-green-500">About Us</a></li>
<li><a href="blog.html" class="text-gray-400 hover:text-green-500">Blog</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Careers</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Contact</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Partners</a></li>
```

**Status**: ⚠️ Most need updating
- `blog.html` = ✅ Correct (if file exists)
- `#` = ❌ Placeholder links

**How to Fix**:
```html
<li><a href="/about.html" class="text-gray-400 hover:text-green-500">About Us</a></li>
<li><a href="/careers.html" class="text-gray-400 hover:text-green-500">Careers</a></li>
<li><a href="/contact.html" class="text-gray-400 hover:text-green-500">Contact</a></li>
<li><a href="/partners.html" class="text-gray-400 hover:text-green-500">Partners</a></li>
```

---

**Legal Links** (Lines 768-772):
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-green-500">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-green-500">Terms of Service</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Cookie Policy</a></li>
<li><a href="#" class="text-gray-400 hover:text-green-500">Compliance</a></li>
```

**Status**: ⚠️ Partially complete
- `privacy.html` = ✅ Correct (if file exists)
- `terms.html` = ✅ Correct (if file exists)
- `#` = ❌ Placeholder links

---

**Contact Links** (Lines 778-799):
```html
<a href="mailto:bengrauwde@hotmail.com" class="text-white font-semibold hover:text-green-500">bengrauwde@hotmail.com</a>
```

**Status**: ⚠️ Needs updating
- This email is a placeholder

**How to Fix**:
```html
<a href="mailto:your-email@example.com" class="text-white font-semibold hover:text-green-500">your-email@example.com</a>
```

---

**Bottom Footer Links** (Lines 808-815):
```html
<a href="privacy.html" class="text-gray-400 hover:text-green-500 text-sm">Privacy</a>
<a href="terms.html" class="text-gray-400 hover:text-green-500 text-sm">Terms</a>
<a href="blog.html" class="text-gray-400 hover:text-green-500 text-sm">Blog</a>
```

**Status**: ⚠️ Needs file verification
- These link to `privacy.html`, `terms.html`, and `blog.html`
- You need to create these files if they don't exist

---

### Step-by-Step: Update All Links

**Step 1: Create a List**

Make a document with all your URLs:
```
Home: /index.html
About: /about.html
Pricing: /pricing.html
Blog: /blog.html
Contact: /contact.html
Privacy: /privacy.html
Terms: /terms.html
Careers: /careers.html
Signup: https://signup.yoursite.com
Email: your-email@yourcompany.com
```

**Step 2: Find and Replace**

Use your text editor's Find & Replace feature (`Ctrl+H` or `Cmd+H`):

1. Find: `href="https://test.com"`
2. Replace with: `href="https://your-actual-url.com"`
3. Click "Replace All"

**Step 3: Update Email**

1. Find: `href="mailto:bengrauwde@hotmail.com"`
2. Replace with: `href="mailto:your-email@example.com"`

**Step 4: Verify All Links**

1. Save the file
2. Open in browser
3. Click each link to verify it works
4. Check that internal links (like `#features`) scroll to correct sections

---

### Link Best Practices

**Do**:
- ✅ Use `/` at the start of internal links: `/about.html`
- ✅ Use `https://` for external links: `https://example.com`
- ✅ Use `mailto:` for email links: `mailto:email@example.com`
- ✅ Test all links after updating

**Don't**:
- ❌ Mix `http://` and `https://` (always use `https://`)
- ❌ Leave `#` as placeholder links
- ❌ Use relative paths like `../about.html` (unless necessary)
- ❌ Update links without testing

---

## Adding Privacy and Terms Pages

### Why You Need These Pages

Privacy and Terms pages are legally important for:
- Protecting your business
- Explaining how you collect/use data
- Setting rules for service use
- Building trust with customers

### Step 1: Create the Privacy Policy Page

**File Name**: `privacy.html`

**Location**: Same folder as `index.html`

**Basic Template**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - AI Automation Bureau">
    <title>Privacy Policy - AI Automation Bureau</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            scroll-behavior: smooth;
        }
        
        body {
            background-color: #f8f7f4;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-900">
    <!-- Header Navigation (Copy from index.html) -->
    <header class="header-sticky">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 bg-green-500 rounded-lg flex items-center justify-center transform -rotate-12">
                        <i class="fas fa-bolt text-white text-lg font-bold"></i>
                    </div>
                    <a href="index.html" class="text-xl font-bold text-gray-900 hidden sm:inline">AI Automation Bureau</a>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="index.html#features" class="text-gray-700 font-semibold hover:text-green-600">Features</a>
                    <a href="index.html#benefits" class="text-gray-700 font-semibold hover:text-green-600">Benefits</a>
                    <a href="index.html" class="text-gray-700 font-semibold hover:text-green-600">Home</a>
                </div>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-20 sm:py-24 lg:py-32">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-black text-gray-900 mb-8">Privacy Policy</h1>
            <p class="text-gray-600 mb-8">Last updated: January 2025</p>

            <div class="space-y-8">
                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">1. Introduction</h2>
                    <p class="text-gray-700 leading-relaxed">
                        AI Automation Bureau ("we," "us," or "our") operates the website and services. This page informs you of our policies regarding the collection, use, and disclosure of personal data when you use our service and the choices you have associated with that data.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">2. Information Collection and Use</h2>
                    <p class="text-gray-700 leading-relaxed mb-4">
                        We collect several different types of information for various purposes to provide and improve our service to you:
                    </p>
                    <ul class="list-disc list-inside space-y-2 text-gray-700">
                        <li>Personal Data: Name, email address, phone number, company information</li>
                        <li>Usage Data: Pages visited, time spent on site, clicks, and interactions</li>
                        <li>Device Data: Browser type, operating system, device type</li>
                        <li>Location Data: General geographic information based on IP address</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">3. Use of Data</h2>
                    <p class="text-gray-700 leading-relaxed">
                        AI Automation Bureau uses the collected data for various purposes:
                    </p>
                    <ul class="list-disc list-inside space-y-2 text-gray-700 mt-4">
                        <li>To provide and maintain our service</li>
                        <li>To notify you about changes to our service</li>
                        <li>To allow you to participate in interactive features</li>
                        <li>To provide customer support</li>
                        <li>To gather analysis or valuable information to improve our service</li>
                        <li>To monitor the usage of our service</li>
                        <li>To detect, prevent and address technical issues</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">4. Security of Data</h2>
                    <p class="text-gray-700 leading-relaxed">
                        The security of your data is important to us but remember that no method of transmission over the Internet or method of electronic storage is 100% secure. While we strive to use commercially acceptable means to protect your Personal Data, we cannot guarantee its absolute security.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">5. Changes to This Privacy Policy</h2>
                    <p class="text-gray-700 leading-relaxed">
                        We may update our Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy on this page and updating the "effective date" at the top of this Privacy Policy.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">6. Contact Us</h2>
                    <p class="text-gray-700 leading-relaxed">
                        If you have any questions about this Privacy Policy, please contact us at:
                    </p>
                    <p class="text-gray-700 mt-4">
                        Email: <a href="mailto:privacy@yourcompany.com" class="text-green-600 hover:text-green-700">privacy@yourcompany.com</a>
                    </p>
                </section>
            </div>
        </div>
    </section>

    <!-- Footer (Copy from index.html) -->
    <footer class="bg-gray-900 text-gray-300 py-16 sm:py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="border-t border-gray-700 pt-8 flex flex-col sm:flex-row justify-between items-center">
                <p class="text-gray-400 text-sm mb-4 sm:mb-0">
                    &copy; 2025 AI Automation Bureau. All rights reserved.
                </p>
                <div class="flex space-x-6">
                    <a href="privacy.html" class="text-gray-400 hover:text-green-500 transition-colors duration-300 text-sm">Privacy</a>
                    <a href="terms.html" class="text-gray-400 hover:text-green-500 transition-colors duration-300 text-sm">Terms</a>
                    <a href="index.html" class="text-gray-400 hover:text-green-500 transition-colors duration-300 text-sm">Home</a>
                </div>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Step 2: Create the Terms of Service Page

**File Name**: `terms.html`

**Location**: Same folder as `index.html`

**Basic Template**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - AI Automation Bureau">
    <title>Terms of Service - AI Automation Bureau</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            scroll-behavior: smooth;
        }
        
        body {
            background-color: #f8f7f4;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-900">
    <!-- Header Navigation -->
    <header class="header-sticky">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 bg-green-500 rounded-lg flex items-center justify-center transform -rotate-12">
                        <i class="fas fa-bolt text-white text-lg font-bold"></i>
                    </div>
                    <a href="index.html" class="text-xl font-bold text-gray-900 hidden sm:inline">AI Automation Bureau</a>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="index.html#features" class="text-gray-700 font-semibold hover:text-green-600">Features</a>
                    <a href="index.html#benefits" class="text-gray-700 font-semibold hover:text-green-600">Benefits</a>
                    <a href="index.html" class="text-gray-700 font-semibold hover:text-green-600">Home</a>
                </div>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-20 sm:py-24 lg:py-32">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-black text-gray-900 mb-8">Terms of Service</h1>
            <p class="text-gray-600 mb-8">Last updated: January 2025</p>

            <div class="space-y-8">
                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">1. Agreement to Terms</h2>
                    <p class="text-gray-700 leading-relaxed">
                        By accessing and using this website and service, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">2. Use License</h2>
                    <p class="text-gray-700 leading-relaxed mb-4">
                        Permission is granted to temporarily download one copy of the materials (information or software) on AI Automation Bureau's website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                    </p>
                    <ul class="list-disc list-inside space-y-2 text-gray-700">
                        <li>Modifying or copying the materials</li>
                        <li>Using the materials for any commercial purpose or for any public display</li>
                        <li>Attempting to decompile or reverse engineer any software contained on the website</li>
                        <li>Removing any copyright or other proprietary notations from the materials</li>
                        <li>Transferring the materials to another person or "mirroring" the materials on any other server</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">3. Disclaimer</h2>
                    <p class="text-gray-700 leading-relaxed">
                        The materials on AI Automation Bureau's website are provided on an 'as is' basis. AI Automation Bureau makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">4. Limitations</h2>
                    <p class="text-gray-700 leading-relaxed">
                        In no event shall AI Automation Bureau or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on AI Automation Bureau's website.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">5. Accuracy of Materials</h2>
                    <p class="text-gray-700 leading-relaxed">
                        The materials appearing on AI Automation Bureau's website could include technical, typographical, or photographic errors. AI Automation Bureau does not warrant that any of the materials on its website are accurate, complete, or current.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">6. Links</h2>
                    <p class="text-gray-700 leading-relaxed">
                        AI Automation Bureau has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by AI Automation Bureau of the site. Use of any such linked website is at the user's own risk.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">7. Modifications</h2>
                    <p class="text-gray-700 leading-relaxed">
                        AI Automation Bureau may revise these terms of service for its website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">8. Governing Law</h2>
                    <p class="text-gray-700 leading-relaxed">
                        These terms and conditions are governed by and construed in accordance with the laws of [Your Jurisdiction] and you irrevocably submit to the exclusive jurisdiction of the courts located in that location.
                    </p>
                </section>

                <section>
                    <h2 class="text-3xl font-bold text-gray-900 mb-4">9. Contact Information</h2>
                    <p class="text-gray-700 leading-relaxed">
                        If you have any questions about these Terms of Service, please contact us at:
                    </p>
                    <p class="text-gray-700 mt-4">
                        Email: <a href="mailto:legal@yourcompany.com" class="text-green-600 hover:text-green-700">legal@yourcompany.com</a>
                    </p>
                </section>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-16 sm:py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="border-t border-gray-700 pt-8 flex flex-col sm:flex-row justify-between items-center">
                <p class="text-gray-400 text-sm mb-4 sm:mb-0">
                    &copy; 2025 AI Automation Bureau. All rights reserved.
                </p>
                <div class="flex space-x-6">
                    <a href="privacy.html" class="text-gray-400 hover:text-green-500 transition-colors duration-300 text-sm">Privacy</a>
                    <a href="terms.html" class="text-gray-400 hover:text-green-500 transition-colors duration-300 text-sm">Terms</a>
                    <a href="index.html" class="text-gray-400 hover:text-green-500 transition-colors duration-300 text-sm">Home</a>
                </div>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Step 3: Verify Links Work

After creating the files, verify the links in your `index.html` work:

**In index.html footer (Lines 768-772)**:
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-green-500">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-green-500">Terms of Service</a></li>
```

**In index.html footer bottom (Lines 813-815)**:
```html
<a href="privacy.html" class="text-gray-400 hover:text-green-500 text-sm">Privacy</a>
<a href="terms.html" class="text-gray-400 hover:text-green-500 text-sm">Terms</a>
```

**These links should now work!** ✅

---

### Step 4: Customize Your Policy Content

The templates above are generic. You should customize them with:

**In privacy.html**:
- Your actual company name (replace "AI Automation Bureau")
- Your actual email address
- Specific data collection practices
- Your jurisdiction for GDPR compliance
- Information about cookies if you use them

**In terms.html**:
- Your actual company name
- Your actual jurisdiction (replace `[Your Jurisdiction]`)
- Your actual email address
- Specific limitations relevant to your service
- Payment terms if applicable

---

### Step 5: Test Everything

1. **Save all files** in the same folder
2. **Open index.html** in your browser
3. **Click the privacy link** in the footer - should load privacy.html
4. **Click the terms link** in the footer - should load terms.html
5. **From privacy.html**, click "Home" link - should return to index.html
6. **From terms.html**, click "Home" link - should return to index.html

---

## Common Tasks & Troubleshooting

### Common Task 1: Add a New Feature Card

**Location**: Lines 197-275 (Features Section)

**Steps**:

1. **Find the last feature card** (Virtual Assistants - Lines 257-275)

2. **Copy the entire `<div class="feature-card">` block**

3. **Paste it right after** the closing `</div>` of the last feature card

4. **Update the content**:
   - Change the icon
   - Change the title
   - Change the description
   - Update the bullet points

**Example** (Adding a 4th feature):

```html
<!-- New Feature Card -->
<div class="feature-card p-8 rounded-2xl retro-border hover-lift">
    <div class="w-16 h-16 bg-green-100 rounded-xl flex items-center justify-center mb-6 border-2 border-green-400">
        <i class="fas fa-chart-line text-green-600 text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-4">Analytics & Insights</h3>
    <p class="text-gray-700 leading-relaxed mb-4">
        Get real-time insights into your automation performance with comprehensive dashboards and detailed reporting.
    </p>
    <ul class="space-y-3">
        <li class="flex items-start">
            <i class="fas fa-check text-green-600 mt-1 mr-3 font-bold"></i>
            <span class="text-gray-700">Real-time performance metrics</span>
        </li>
        <li class="flex items-start">
            <i class="fas fa-check text-green-600 mt-1 mr-3 font-bold"></i>
            <span class="text-gray-700">Custom reports and dashboards</span>
        </li>
        <li class="flex items-start">
            <i class="fas fa-check text-green-600 mt-1 mr-3 font-bold"></i>
            <span class="text-gray-700">Data export capabilities</span>
        </li>
    </ul>
</div>
```

**Note**: The Features section uses a 3-column grid. Adding a 4th card will wrap to a new row on desktop.

---

### Common Task 2: Change All Button Colors

**Scenario**: You want all buttons to be blue instead of green

**Solution**: Use Find & Replace

1. Open your text editor
2. Press `Ctrl+H` (Windows) or `Cmd+H` (Mac)
3. Find: `text-green-600`
4. Replace with: `text-blue-600`
5. Click "Replace All"

**Repeat for**:
- `bg-green-500` → `bg-blue-500`
- `bg-green-600` → `bg-blue-600`
- `border-green-400` → `border-blue-400`
- `border-green-500` → `border-blue-500`
- `hover:text-green-500` → `hover:text-blue-500`
- etc.

---

### Common Task 3: Add a New Testimonial

**Location**: Lines 420-500 (Testimonials Section)

**Steps**:

1. **Find a testimonial card** (any of the 4 existing ones)

2. **Copy the entire `<div class="testimonial-card">` block**

3. **Paste it after the last testimonial**

4. **Update**:
   - Star count (add/remove `<i class="fas fa-star">` lines)
   - Quote text
   - Customer name
   - Customer title

**Example**:

```html
<div class="testimonial-card p-8 rounded-2xl hover-lift">
    <div class="flex items-center mb-4">
        <div class="star-rating flex gap-1">
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
            <i class="fas fa-star text-lg"></i>
        </div>
    </div>
    <p class="text-gray-700 leading-relaxed mb-6 text-lg">
        "This automation solution saved us hundreds of hours every month. The interface is intuitive and the support team is fantastic. Highly recommend!"
    </p>
    <div class="flex items-center">
        <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mr-4 border-2 border-green-400">
            <i class="fas fa-user text-green-600 text-lg"></i>
        </div>
        <div>
            <p class="font-bold text-gray-900">Emily Rodriguez</p>
            <p class="text-gray-600 text-sm">Operations Director, TechStart Inc.</p>
        </div>
    </div>
</div>
```

---

### Common Task 4: Add a New FAQ Item

**Location**: Lines 569-706 (FAQ Section)

**Steps**:

1. **Find the last FAQ item** (Question 5)

2. **Copy the entire `<div class="faq-item">` block**

3. **Paste it after the last FAQ**

4. **Update**:
   - Question text
   - Answer text

**Example**:

```html
<div class="faq-item bg-white border-2 border-gray-200 rounded-xl overflow-hidden hover:border-green-400 transition-all duration-300">
    <div class="faq-question p-6 sm:p-8 cursor-pointer hover:bg-green-50 transition-colors duration-300">
        <div class="flex items-center justify-between">
            <h3 class="text-lg sm:text-xl font-bold text-gray-900">Can we customize the automation workflows?</h3>
            <i class="faq-icon fas fa-chevron-down text-green-600 text-lg font-bold transition-transform duration-300"></i>
        </div>
    </div>
    <div class="faq-answer hidden px-6 sm:px-8 pb-6 sm:pb-8 border-t-2 border-gray-200 bg-gray-50">
        <p class="text-gray-700 leading-relaxed">
            Yes! Our platform is highly customizable. You can configure workflows to match your specific business processes, set up custom rules, define approval workflows, and integrate with your existing systems. Our team can also help with more complex customizations.
        </p>
    </div>
</div>
```

---

### Troubleshooting: Links Don't Work

**Problem**: Clicking a link does nothing or shows an error

**Possible Causes**:

1. **File doesn't exist**
   - Solution: Create the file (e.g., `privacy.html`)
   - Verify file is in the same folder as `index.html`

2. **Wrong file path**
   - Wrong: `href="/privacy.html"` (with slash)
   - Right: `href="privacy.html"` (no slash)
   - Right: `href="https://example.com"` (external)

3. **Typo in filename**
   - Check spelling exactly: `privacy.html` not `Privacy.html`
   - File names are case-sensitive on some servers

4. **Wrong URL format**
   - External links need `https://`
   - Internal links should not have `https://`

**How to Fix**:

1. Check the file exists in your folder
2. Check the filename matches exactly
3. Check the href attribute matches the filename
4. Test by opening the file directly in browser

---

### Troubleshooting: Styling Looks Wrong

**Problem**: Colors, spacing, or layout is broken

**Possible Causes**:

1. **Tailwind CSS not loading**
   - Check line 11: `<script src="https://cdn.tailwindcss.com"></script>`
   - Make sure this line is present and correct

2. **Font Awesome not loading**
   - Check line 12: `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">`
   - Icons won't show without this

3. **Typo in class name**
   - Example: `text-gree-600` instead of `text-green-600`
   - Check spelling carefully

4. **Browser cache**
   - Press `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
   - This forces browser to reload without cache

**How to Fix**:

1. Verify CDN links are correct (lines 11-12)
2. Check for typos in class names
3. Clear browser cache and reload
4. Check browser console for errors (F12 key)

---

### Troubleshooting: Mobile Menu Doesn't Work

**Problem**: Mobile menu button doesn't toggle menu

**Possible Causes**:

1. **JavaScript not working**
   - Check lines 911-960 (JavaScript section)
   - Make sure it's inside `<script>` tags

2. **HTML structure changed**
   - Mobile menu needs specific class names
   - Don't change `mobile-menu-button` or `mobile-menu` class names

**How to Fix**:

1. Don't modify the JavaScript unless necessary
2. Keep HTML structure the same
3. Check browser console for errors (F12 key)

---

### Troubleshooting: FAQ Accordion Doesn't Work

**Problem**: Clicking FAQ questions doesn't expand/collapse

**Possible Causes**:

1. **JavaScript not running**
   - Same as mobile menu issue

2. **Changed class names**
   - Don't change `faq-item`, `faq-question`, `faq-answer`, `faq-icon` class names

**How to Fix**:

1. Keep all class names exactly as they are
2. Check JavaScript is present (lines 911-960)
3. Test in browser console (F12)

---

## Best Practices

### 1. Always Backup Before Major Changes

```
Before editing, save a copy:
index.html → index.html.backup
```

This way you can revert if something breaks.

---

### 2. Test Changes in Browser

After every major change:
1. Save the file
2. Refresh browser (`F5` or `Ctrl+R`)
3. Test all functionality
4. Check on mobile (resize browser window)

---

### 3. Use Consistent Formatting

Keep your HTML organized:
```html
<!-- Good: Organized and readable -->
<section id="features" class="py-20 sm:py-24 lg:py-32 bg-white">
    <div class="max-w-7xl mx-auto px-4">
        <!-- Content -->
    </div>
</section>

<!-- Bad: Messy and hard to read -->
<section id="features" class="py-20 sm:py-24 lg:py-32 bg-white"><div class="max-w-7xl mx-auto px-4"><!-- Content --></div></section>
```

---

### 4. Don't Change Class Names Unnecessarily

Classes like `feature-card`, `mobile-menu`, `faq-item` are used by CSS and JavaScript. Changing them will break styling and functionality.

---

### 5. Keep Backups of Working Versions

```
project/
├── index.html (current version)
├── index.html.v1 (backup version 1)
├── index.html.v2 (backup version 2)
└── privacy.html
```

---

### 6. Test All Links Regularly

Create a checklist:
- [ ] Header navigation links
- [ ] Hero CTA buttons
- [ ] Footer links
- [ ] Mobile menu links
- [ ] Internal anchor links (#features, #benefits, etc.)
- [ ] External links (signup, demo, etc.)

---

### 7. Use Meaningful Link URLs

❌ Bad:
```html
<a href="https://test.com">Click here</a>
```

✅ Good:
```html
<a href="https://yourcompany.com/signup">Start Free Trial</a>
```

---

### 8. Keep Mobile Responsiveness

When making changes, test on:
- Mobile (320px width)
- Tablet (768px width)
- Desktop (1024px+ width)

Use browser DevTools (F12) to test different screen sizes.

---

### 9. Maintain Consistent Branding

- Use the same colors throughout
- Use the same fonts
- Keep logo consistent
- Use the same tone of voice in copy

---

### 10. Document Your Changes

Keep a changelog:
```
# Changelog

## Version 2.0 - January 15, 2025
- Updated hero headline
- Added 4th feature card
- Changed primary color from green to blue
- Fixed footer email link

## Version 1.0 - January 1, 2025
- Initial launch
```

---

## Quick Reference Guide

### File Structure
```
your-project/
├── index.html          (Main landing page)
├── privacy.html        (Privacy policy)
├── terms.html          (Terms of service)
├── blog.html           (Blog page - optional)
└── assets/
    ├── images/         (Images folder)
    └── css/            (Custom CSS - optional)
```

### Key Sections in index.html
```
Lines 67-110:    Header & Navigation
Lines 112-177:   Hero Section
Lines 179-275:   Features Section
Lines 277-361:   Benefits Section
Lines 363-385:   CTA Section
Lines 387-500:   Testimonials Section
Lines 502-535:   About Section
Lines 537-706:   FAQ Section
Lines 708-900:   Footer
Lines 911-960:   JavaScript
```

### Color Values
```
Green (Primary):
- #22c55e (main green)
- #16a34a (dark green)
- #dcfce7 (light green)

Grays:
- #f8f7f4 (background)
- #ffffff (white)
- #f3f4f6 (light gray)
- #9ca3af (medium gray)
- #4b5563 (dark gray)
- #111827 (very dark gray)
```

### Common Tailwind Sizes
```
Text: text-xs, text-sm, text-base, text-lg, text-xl, text-2xl, text-3xl, text-4xl, text-5xl, text-6xl, text-7xl

Spacing: 1-12, 16, 20, 24, 28, 32, 36, 40, 44, 48, 52, 56, 60, 64, 72, 80, 96

Width: w-1 to w-96, w-full, w-screen

Rounded: rounded-sm, rounded, rounded-md, rounded-lg, rounded-xl, rounded-2xl, rounded-3xl, rounded-full
```

### Breakpoints
```
Mobile: (default, no prefix)
Tablet: sm: (640px), md: (768px)
Desktop: lg: (1024px), xl: (1280px), 2xl: (1536px)

Example: class="text-lg md:text-xl lg:text-2xl"
```

---

## Getting Help

### Resources

1. **Tailwind CSS Docs**: https://tailwindcss.com/docs
2. **Font Awesome Icons**: https://fontawesome.com/icons
3. **HTML Tutorial**: https://www.w3schools.com/html/
4. **CSS Tutorial**: https://www.w3schools.com/css/
5. **MDN Web Docs**: https://developer.mozilla.org/

### Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| Colors not showing | Check Tailwind CDN link (line 11) |
| Icons not showing | Check Font Awesome link (line 12) |
| Mobile menu broken | Don't change class names, check JavaScript |
| Links don't work | Check file paths and URLs |
| Styling looks wrong | Clear browser cache (Ctrl+Shift+R) |
| Page looks stretched | Check max-width classes (max-w-7xl) |
| Text too small/large | Adjust text-* classes |
| Spacing wrong | Adjust p-*, m-*, pt-*, pb-* classes |

---

## Conclusion

You now have a complete guide to maintaining and customizing your AI Automation Bureau landing page. Remember:

1. **Start small** - Make one change at a time
2. **Test thoroughly** - Check every change in the browser
3. **Keep backups** - Save working versions
4. **Follow the structure** - Don't change class names or HTML structure
5. **Ask for help** - Use the resources provided above

Good luck with your landing page! 🚀