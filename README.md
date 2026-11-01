# Rob Fritzemeier – Personal Resume Website

A clean, accessible static resume website for Rob Fritzemeier, hosted on Cloudflare Pages at [robthefritz.com](https://robthefritz.com).

## Structure

This is a single-page static website with minimal JavaScript (theme toggle only), no build step, and no dependencies. All files are in the `public/` directory:

```
public/
├── index.html          # Main resume page
├── style.css           # Styles with light/dark mode support
├── favicon.svg         # SVG favicon
├── favicon-32.png      # PNG favicon fallback
├── og-preview.png      # Open Graph preview image (1200x630)
├── og-preview.svg      # SVG source for preview
├── robots.txt          # Search engine directives
├── sitemap.xml         # XML sitemap
└── 404.html            # 404 error page
```

## Local Preview

To preview the site locally, run:

```bash
python3 -m http.server -d public
```

Then open [http://localhost:8000](http://localhost:8000) in your browser.

You can also open `public/index.html` directly in a browser, though the theme toggle works better with a local server.

## Cloudflare Pages Settings

When deploying to Cloudflare Pages:

- **Build command:** (leave empty)
- **Build output directory:** `public`
- **Root directory:** `/`

The site requires no build step. Cloudflare Pages will serve the contents of the `public/` directory directly.

For the custom domain configuration, point `robthefritz.com` to your Cloudflare Pages deployment through the Cloudflare dashboard.

## Features

- **Theme toggle:** Light/Dark/Auto modes with localStorage persistence and no-JS fallback
- **Responsive design:** Mobile-first layout that works at 360px, 768px, and 1280px widths
- **Expandable timeline:** Native `<details>/<summary>` elements for role details (newest role open by default)
- **Dark mode support:** Automatically adapts to user's system preferences or manual selection
- **Accessible:** Semantic HTML, skip link, proper headings, visible focus states, 4.5:1 contrast ratio
- **Print-friendly:** Optimized print stylesheet for resume PDFs, targeting 2 pages maximum (all timeline entries forced open in print)
- **Minimal dependencies:** Only ~100 lines of vanilla JavaScript for theme toggle; everything else works without JS
- **Performance:** Total page weight ~52KB (excluding OG preview image and future PDF)
- **SEO ready:** Open Graph tags, Twitter Card support, sitemap.xml, robots.txt, canonical URL

## Content Sections

1. **Hero** – Name, headline, and links (LinkedIn; email when added)
2. **Now** – Current focus and availability (placeholder content)
3. **How I Lead** – Leadership principles (placeholder content)
4. **Timeline** – 18 years of career progression at CarMax (expandable entries)
5. **Selected Work** – Four key projects with problem/solution/result format
6. **Education & Certifications** – Degree and professional certifications
7. **Contact** – Connection options

## TODO Items

The following content placeholders need to be filled in by Rob:

### 1. Email Address (3 locations)
- **Locations:** Hero section, Contact section, and commented-out email buttons
- **Current state:** Email links are commented out with `<!-- TODO(rob): set email address -->`
- **Action needed:** Uncomment and update the `mailto:` links once Rob provides his preferred email address

### 2. Resume PDF (2 locations)
- **Locations:** Hero section and Footer
- **Current state:** "Download resume (PDF)" buttons are commented out with `<!-- TODO(rob): add /rob-fritzemeier-resume.pdf to enable this button -->`
- **Action needed:** Add the file at `/public/rob-fritzemeier-resume.pdf` and uncomment the buttons

### 3. "Now" Card Content
- **Location:** Between Hero and "How I lead" sections
- **Current state:** Placeholder text with `<!-- TODO(rob) -->` comment
- **Action needed:** Replace with Rob's actual current focus, what he's open to next, and update the date

### 4. Leadership Principles (3 items)
- **Location:** "How I lead" section
- **Current state:** Placeholder text provided for all three principles, marked with `<!-- TODO(rob) -->`
- **Action needed:** Replace with Rob's actual leadership principles and descriptions

### 5. Selected Work Results (4 items)
- **Location:** "Selected work" section, end of each project card
- **Current state:** Empty `<strong>Result:</strong> <!-- TODO(rob) -->` placeholders
- **Action needed:** Add specific outcomes, metrics, or impact statements for each project:
  - Tax and fee processing system
  - PCI financial integration
  - Enterprise-wide security system
  - Salesforce and Azure cloud transformation

## Acceptance Checklist Results

✅ **Responsive:** Tested at 360px, 768px, and 1280px widths – looks correct in all sizes  
✅ **Light & Dark modes:** Both themes render correctly with proper contrast  
✅ **Works without JS:** Theme follows device preference; timeline details are fully functional  
✅ **Print layout:** Fits in 2 pages; all timeline entries forced open  
✅ **Contrast:** Body text passes WCAG AA (4.5:1) in both light and dark modes  
✅ **Page weight:** ~52KB total (excluding og-preview.png and future PDF)  
✅ **Touch targets:** All interactive elements meet 44px minimum  
✅ **Accessibility:** Semantic HTML, skip link, proper ARIA labels, visible focus states

## Design Credits

- **Owner:** Rob Fritzemeier
- **Designer:** Isho
- **Builder:** Kaihatsu
- **Host:** Cloudflare Pages

## License

All rights reserved © 2026 Rob Fritzemeier
