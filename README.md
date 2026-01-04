# 📚 Portfolio Management Guide

Complete instructions for managing your Jekyll portfolio website.

---

## 📁 File Structure Overview

```
shubhdeepsingh/
├── _config.yml                  # Site configuration
├── _layouts/                    # Page templates
│   ├── default.html
│   └── single-writeup-layout.html
├── _includes/                   # Reusable components
│   └── navigation.html
├── _data/                       # Data files (YAML)
│   ├── certifications.yml
│   ├── projects.yml
│   └── skills.yml
├── assets/                      # Static files
│   ├── css/style.css
│   ├── js/theme-toggle.js
│   ├── images/
│   └── pdf/
├── index.html                   # Home page
├── skills.html                  # Skills page (uses _data/skills.yml)
├── projects.html                # Projects page (accordion style)
├── certifications.html          # Certifications page (uses _data/certifications.yml)
├── writeups.html                # Write-ups page (accordion style)
└── contact.html                 # Contact page
```

---

## 🔧 How to Edit Each Page

### 1️⃣ **HOME PAGE (index.html)**

**What it shows:** Your name, tagline, and bio

**How to edit:**

1. Open `_config.yml`
2. Find the `author:` section
3. Update these fields:

```yaml
author:
  name: "Your Name Here"
  tagline: "Your Professional Title"
  bio: "Your bio text here. Can be multiple sentences."
```

**That's it!** Changes apply to the home page automatically.

---

### 2️⃣ **SKILLS PAGE (skills.html)**

**What it shows:** List of your technical skills

**How to add a new skill:**

1. Open `_data/skills.yml`
2. Add this at the end:

```yaml
- name: "Tool or Skill Name"
  description: "Brief description of your experience with this skill."
```

**Example:**

```yaml
- name: "Python Scripting"
  description: "Created automation scripts for log analysis and report generation."

- name: "AWS Security"
  description: "Configured security groups, IAM policies, and CloudTrail monitoring."
```

**Rules:**
- Start with `- name:` (dash, space, name)
- Use 2 spaces for indentation
- Keep quotes around text
- Each skill is a separate block

---

### 3️⃣ **PROJECTS PAGE (projects.html)**

**What it shows:** Expandable project cards with details

**How to add a new project:**

1. Open `projects.html`
2. Find this line: `</section>` (near the bottom)
3. **BEFORE** that line, add this:

```html
<div class="project-accordion">
  <button class="accordion-header">
    <span class="accordion-icon">🔧</span>
    <span class="accordion-title">Your Project Title</span>
    <span class="accordion-toggle">+</span>
  </button>
  <div class="accordion-content">
    <div class="project-meta">
      <span><strong>Type:</strong> Project Category</span>
      <span><strong>Tools:</strong> Tool1, Tool2, Tool3</span>
      <span><strong>Duration:</strong> X weeks</span>
    </div>
    
    <h3>📋 Overview</h3>
    <p>Brief description of the project.</p>
    
    <h3>🎯 Objectives</h3>
    <ul>
      <li>Objective 1</li>
      <li>Objective 2</li>
      <li>Objective 3</li>
    </ul>
    
    <h3>💻 Code Example (Optional)</h3>
    <div class="code-block">
      <pre><code>Your code here
Multiple lines OK
Commands, logs, etc.</code></pre>
    </div>
    
    <h3>🖼️ Screenshot (Optional)</h3>
    <img src="/shubhdeepsingh/assets/images/your-image.png" alt="Description" style="max-width: 100%; border-radius: 8px; margin: 20px 0;">
    
    <h3>✅ Achievements</h3>
    <ul>
      <li>Achievement 1</li>
      <li>Achievement 2</li>
      <li>Achievement 3</li>
    </ul>
  </div>
</div>
```

**Customize:**
- Change emoji (🔧, 🛡️, 📧, 🔎, 🌐, etc.)
- Update title, type, tools, duration
- Add/remove sections as needed
- Delete optional sections you don't need

---

### 4️⃣ **CERTIFICATIONS PAGE (certifications.html)**

**What it shows:** List of certifications with images and details

**How to add a new certification:**

1. **First:** Upload your certificate image to `assets/images/`
2. Open `_data/certifications.yml`
3. Add this at the end:

```yaml
- name: "Certification Name"
  image: "/assets/images/your-cert-image.png"
  details:
    - "Detail or achievement 1"
    - "Detail or achievement 2"
    - "Detail or achievement 3"
```

**Example:**

```yaml
- name: "CompTIA Security+"
  image: "/assets/images/comptia-secplus.png"
  details:
    - "Learned network security fundamentals"
    - "Covered threat detection and incident response"
    - "Passed with 850/900 score"
```

**Rules:**
- Image path must start with `/assets/images/`
- Each detail is a separate line starting with `- "`
- Use 2 spaces for indentation

---

### 5️⃣ **WRITE-UPS PAGE (writeups.html)**

**What it shows:** Expandable write-up cards with full content

**How to add a new write-up:**

1. Open `writeups.html`
2. Find this line: `</section>` (near the bottom)
3. **BEFORE** that line, add this:

```html
<div class="writeup-accordion">
  <button class="accordion-header">
    <span class="accordion-icon">📄</span>
    <span class="accordion-title">Your Write-up Title</span>
    <span class="accordion-toggle">+</span>
  </button>
  <div class="accordion-content">
    <div class="writeup-meta">
      <span><strong>Category:</strong> Category Name</span>
      <span><strong>Date:</strong> Month Year</span>
      <span><strong>Author:</strong> Your Name</span>
    </div>
    
    <h3>📋 Summary</h3>
    <p>Brief summary of what this write-up covers.</p>
    
    <div class="alert-box">
      <strong>⚠️ Key Finding:</strong> Main takeaway or important finding.
    </div>
    
    <h3>🔍 Details</h3>
    <ul>
      <li><strong>Point 1:</strong> Details here</li>
      <li><strong>Point 2:</strong> Details here</li>
      <li><strong>Point 3:</strong> Details here</li>
    </ul>
    
    <h3>💻 Commands Used</h3>
    <div class="code-block">
      <pre><code>command line 1
command line 2
log output here</code></pre>
    </div>
    
    <h3>🎯 IOCs (Optional)</h3>
    <ul>
      <li><strong>IP Address:</strong> X.X.X.X</li>
      <li><strong>Domain:</strong> malicious-site.com</li>
      <li><strong>Hash:</strong> abc123...</li>
    </ul>
    
    <h3>✅ Conclusion</h3>
    <p>Wrap up with key takeaways and final thoughts.</p>
  </div>
</div>
```

**Available components:**

**Alert Box (Yellow warning):**
```html
<div class="alert-box">
  <strong>⚠️ Warning:</strong> Your text here
</div>
```

**Recommendation Box (Blue):**
```html
<div class="recommendation-box">
  <strong>💡 Recommendation:</strong> Your text here
</div>
```

**Code Block:**
```html
<div class="code-block">
  <pre><code>Your code here</code></pre>
</div>
```

---

### 6️⃣ **CONTACT PAGE (contact.html)**

**What it shows:** Your contact information and resume download

**How to edit:**

1. Open `_config.yml`
2. Find the `author:` section
3. Update these fields:

```yaml
author:
  email: "your-email@gmail.com"
  linkedin: "https://www.linkedin.com/in/your-profile"
  github: "https://github.com/your-username"
```

**To update resume:**
1. Replace the file at: `assets/pdf/resume.pdf`
2. Keep the filename as `resume.pdf`

---

## ⚙️ CONFIGURATION FILE (_config.yml)

**What it does:** Controls site-wide settings

**Important sections:**

### **Site Information:**
```yaml
title: "Your Name's Portfolio"
description: "Your tagline or description"
baseurl: "/shubhdeepsingh"              # Don't change this!
url: "https://shubamarora.github.io"    # Don't change this!
```

### **Author Information:**
```yaml
author:
  name: "Your Full Name"
  tagline: "Your Professional Title"
  bio: "Your complete bio here. Can be several sentences."
  email: "your-email@gmail.com"
  linkedin: "https://www.linkedin.com/in/your-profile"
  github: "https://github.com/your-username"
```

**⚠️ Don't change these sections:**
- `collections:` (needed for Jekyll)
- `markdown:` (needed for Jekyll)
- `permalink:` (needed for URLs)
- `exclude:` (needed for build)

---

## 🎨 THEME CUSTOMIZATION (assets/css/style.css)

**How to change colors:**

1. Open `assets/css/style.css`
2. Find the `:root` section at the top
3. Change the color values:

```css
:root {
  --bg-primary: #0d1117;      /* Main background (dark) */
  --bg-secondary: #161b22;    /* Card backgrounds (dark) */
  --accent-primary: #58a6ff;  /* Links and highlights (blue) */
  --text-primary: #e6edf3;    /* Main text (light gray) */
}
```

**Color codes:**
- Use hex codes like `#58a6ff` (blue)
- Or use color names like `red`, `blue`, `green`
- Test in browser to see changes

---

## 📸 ADDING IMAGES

### **For Certifications:**

1. Save image file to: `assets/images/`
2. Name it descriptively: `comptia-secplus.png`
3. Reference in `_data/certifications.yml`:
```yaml
image: "/assets/images/comptia-secplus.png"
```

### **For Projects/Write-ups:**

1. Save image to: `assets/images/`
2. Add to HTML:
```html
<img src="/shubhdeepsingh/assets/images/your-image.png" alt="Description" style="max-width: 100%; border-radius: 8px;">
```

**Supported formats:** `.png`, `.jpg`, `.jpeg`, `.gif`

---

## 🔄 WORKFLOW: Making Changes

### **For Simple Text Changes:**
1. Edit the file on GitHub directly (click pencil icon)
2. Make your changes
3. Click "Commit changes"
4. Wait 2-3 minutes
5. Refresh your website

### **For Adding New Items:**
1. Follow the instructions above for that page type
2. Copy the template
3. Paste it in the right location
4. Customize the content
5. Commit changes
6. Wait 2-3 minutes
7. Test on your live site

---

## ⚠️ COMMON MISTAKES TO AVOID

### **YAML Files (_data/):**

❌ **Wrong:**
```yaml
- name: My Skill     # Missing quotes
  description: text
```

✅ **Correct:**
```yaml
- name: "My Skill"   # Quotes around text
  description: "text"
```

❌ **Wrong:**
```yaml
- name: "Skill"
description: "text"  # Wrong indentation
```

✅ **Correct:**
```yaml
- name: "Skill"
  description: "text"  # 2 spaces indent
```

### **HTML Files:**

❌ **Wrong:**
```html
<div class="accordion-content">
  <h3>Title</h3>
</div>
<div class="accordion-content">  # Forgot to close previous div!
```

✅ **Correct:**
```html
<div class="accordion-content">
  <h3>Title</h3>
</div>
```

### **File Paths:**

❌ **Wrong:**
```
assets\images\photo.png          # Wrong slashes (Windows style)
/assets/images/Photo.png         # Wrong case (P vs p)
assets/images/my photo.png       # Spaces in filename
```

✅ **Correct:**
```
/shubhdeepsingh/assets/images/photo.png
```

---

## 🆘 TROUBLESHOOTING

### **Changes don't appear:**
- Wait 2-3 minutes for GitHub Pages to rebuild
- Clear browser cache (Ctrl+Shift+R)
- Check GitHub Actions tab for build errors

### **Page shows YAML/code instead of content:**
- Make sure you're viewing the live site, not the file
- URL should be: `https://shubamarora.github.io/shubhdeepsingh/`
- Not: `https://github.com/shubamarora/shubhdeepsingh/`

### **Accordion won't expand:**
- Make sure `<script>` section is at bottom of page
- Check browser console for JavaScript errors (F12)

### **Theme toggle not working:**
- Clear browser cache
- Check that `theme-toggle.js` exists in `assets/js/`
- Verify `_includes/navigation.html` has the toggle button

### **Build fails (red X in Actions):**
- Check YAML indentation (must use 2 spaces)
- Look for unclosed HTML tags
- Check for special characters in text (use quotes)

---

## 📋 QUICK REFERENCE

### **File Locations:**

| What You Want to Change | File to Edit |
|-------------------------|--------------|
| Your name, bio, email | `_config.yml` |
| Skills | `_data/skills.yml` |
| Certifications | `_data/certifications.yml` |
| Projects | `projects.html` |
| Write-ups | `writeups.html` |
| Colors/styling | `assets/css/style.css` |
| Navigation menu | `_includes/navigation.html` |

### **Adding New Items:**

| Item Type | Where to Add |
|-----------|--------------|
| New skill | End of `_data/skills.yml` |
| New certification | End of `_data/certifications.yml` |
| New project | Before `</section>` in `projects.html` |
| New write-up | Before `</section>` in `writeups.html` |
| New image | Upload to `assets/images/` |

---

## 🎓 LEARNING RESOURCES

**YAML Syntax:**
- https://yaml.org/spec/1.2/spec.html
- Remember: 2 spaces for indentation, quotes around text

**HTML Basics:**
- https://www.w3schools.com/html/
- For adding/editing content in accordion pages

**Jekyll Documentation:**
- https://jekyllrb.com/docs/
- For advanced customization

---

## ✅ CHECKLIST: Before Committing Changes

- [ ] Checked spelling and grammar
- [ ] YAML indentation is correct (2 spaces)
- [ ] All HTML tags are closed
- [ ] Image paths start with `/shubhdeepsingh/assets/`
- [ ] Quotes around all text in YAML files
- [ ] No spaces in filenames
- [ ] Tested locally if possible

---

## 🎉 YOU'RE READY!

Save this file as `README.md` in your repository for easy reference.

**Remember:**
1. Make small changes and test
2. Wait 2-3 minutes after committing
3. Check GitHub Actions for build status
4. Clear browser cache if changes don't show

**Happy updating!** 🚀
