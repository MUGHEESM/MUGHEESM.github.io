# AI Coding Assistant Instructions

## Project Overview
This is a **static cybersecurity portfolio website** with an integrated blog platform for Muhammad Mughees. The site is built with vanilla HTML/CSS/JavaScript (no frameworks) and uses browser localStorage for blog post persistence.

## Architecture & File Structure

- **`index.html`** - Main portfolio page with 6 sections: Hero, About, Services, Skills, Contact
- **`blog.html`** - Blog listing and management interface (CRUD operations)
- **`styles.css`** - Unified stylesheet for both pages (850+ lines, CSS custom properties for theming)
- **`script.js`** - Portfolio interactivity: mobile nav, smooth scroll, scroll animations, active nav highlighting
- **`blog.js`** - Blog functionality: localStorage CRUD, modal management, category filtering

## Key Technical Patterns

### 1. CSS Variable Theming
All colors use CSS custom properties defined in `:root`. When updating colors, modify these variables:
```css
--primary-color: #00ff88;    /* Accent color for CTAs, links */
--secondary-color: #0a192f;  /* Dark background base */
--accent-color: #64ffda;     /* Secondary highlights */
```

### 2. LocalStorage Data Structure
Blog posts are stored as JSON arrays in `localStorage` with this schema:
```javascript
{
  id: Number (timestamp),
  title: String,
  category: String (kebab-case),
  excerpt: String (max 150 chars),
  content: String (HTML markup),
  image: String (URL),
  date: String (ISO date format)
}
```

### 3. Modal Pattern
Two reusable modals: `newPostModal` (create) and `readPostModal` (view). Both close via:
- Click `.close` button
- Click modal backdrop
- No ESC key handler implemented

### 4. Responsive Navigation
Mobile nav uses hamburger toggle pattern. Menu slides in from left at `768px` breakpoint. Active state managed by JavaScript scroll detection.

## Development Workflows

### Running Locally
Open `index.html` directly in browser (no build step needed). For CORS/fetch testing, use:
```powershell
python -m http.server 8000
```
Or any static server. Access at `http://localhost:8000`

### Adding New Services/Skills
Services are hardcoded in `index.html` lines 101-151 (`.services-grid`). Each `.service-card` requires:
- Font Awesome icon class (`.service-icon i`)
- Title and description text

Skills follow same pattern at lines 157-210 (`.skills-grid`).

### Blog Category Management
Categories are defined in 3 places (keep synchronized):
1. **`blog.html`** line 35-41 - Filter buttons
2. **`blog.html`** line 54-60 - Form select options
3. Sample posts in **`blog.js`** lines 25-94

## Critical Conventions

### Navigation Structure
- Internal links use `#section-id` anchors (portfolio) or `index.html#section-id` (blog page)
- Blog page is separate file, not SPA
- Smooth scroll handled by `script.js` lines 16-26

### Image Handling
No local images in repo. All images referenced via:
- External URLs (Font Awesome CDN)
- Placeholder services (`via.placeholder.com`)
- User must replace `img.jpg` reference in About section (line 65)

### Form Behavior
Contact form (portfolio) shows alert on submit - **no backend integration**. Replace alert at `script.js` line 57 when adding email service.

## Styling Specifics

### Grid Layouts
- Services: `minmax(300px, 1fr)` - 3 columns desktop, 1 column mobile
- Blog: `minmax(350px, 1fr)` - responsive auto-fill
- Skills: `minmax(250px, 1fr)` - 4 columns max

### Animation Patterns
- Scroll reveal: Intersection Observer with `0.1` threshold, 50px bottom margin
- Hero pulse: 3s ease-in-out infinite on shield icon
- Card hover: `translateY(-10px)` with glow shadow
- All transitions use `0.3s ease` timing

### Z-Index Layers
```
2000: Modals
1000: Fixed navbar
1: Section content with positioned elements
0: Image overlays, decorative elements
```

## Common Modifications

### Adding Blog Post Programmatically
Use `blogPosts.unshift()` to add to beginning, then call `savePosts()` and `displayPosts()`. Date must be ISO format (`YYYY-MM-DD`).

### Customizing Color Scheme
Update 3 primary variables in `styles.css` lines 9-11. All components inherit from these values.

### Mobile Breakpoints
- `768px`: Hamburger nav, column layouts, reduced font sizes
- `480px`: Full-width buttons, vertical filters

## External Dependencies
- **Font Awesome 6.4.0** (CDN) - All icons sourced from here
- No npm packages, no build tools, no transpilation

## Testing Checklist
- [ ] Test mobile nav toggle and close-on-click behavior
- [ ] Verify smooth scroll on anchor links (both pages)
- [ ] Check localStorage persistence (create/delete post, refresh page)
- [ ] Test modal close via backdrop click and X button
- [ ] Validate responsive layouts at 768px and 480px breakpoints
- [ ] Confirm category filter shows/hides correct posts
