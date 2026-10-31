# Rob Fritzemeier – Personal Resume Website

A clean, accessible static resume website for Rob Fritzemeier, hosted on Cloudflare Pages at [robthefritz.com](https://robthefritz.com).

## Structure

This is a single-page static website with no build step, no dependencies, and no external resources. All files are in the `public/` directory:

```
public/
├── index.html    # Main resume page
├── style.css     # Styles with light/dark mode support
├── favicon.svg   # Simple SVG favicon
└── 404.html      # 404 error page
```

## Local Preview

To preview the site locally, run:

```bash
python3 -m http.server -d public
```

Then open [http://localhost:8000](http://localhost:8000) in your browser.

You can also open `public/index.html` directly in a browser, though some features work better with a local server.

## Cloudflare Pages Settings

When deploying to Cloudflare Pages:

- **Build command:** (leave empty)
- **Build output directory:** `public`
- **Root directory:** `/`

The site requires no build step. Cloudflare Pages will serve the contents of the `public/` directory directly.

For the custom domain configuration, point `robthefritz.com` to your Cloudflare Pages deployment through the Cloudflare dashboard.

## Features

- **Responsive design:** Mobile-first layout that works on all screen sizes
- **Dark mode support:** Automatically adapts to user's system preferences
- **Accessible:** Semantic HTML, skip link, proper headings, visible focus states, 4.5:1 contrast ratio
- **Print-friendly:** Optimized print stylesheet for resume PDFs, targeting 2 pages maximum
- **No dependencies:** Pure HTML and CSS, no JavaScript required, no external resources

## Content Sections

1. **Hero** – Name, headline, and links
2. **How I Lead** – Leadership principles
3. **Timeline** – 18 years of career progression at CarMax
4. **Selected Work** – Four key projects with problem/solution/result format
5. **Education & Certifications** – Degree and professional certifications
6. **Contact** – Connection options

## TODO Items

The following content placeholders need to be filled in by Rob:

### 1. Email Address (2 locations)
- **Location:** Hero section and Contact section
- **Current state:** Email links are commented out with `<!-- TODO(rob): set email address -->`
- **Action needed:** Add email address to the `mailto:` links or keep them omitted

### 2. Leadership Principles (3 items)
- **Location:** "How I lead" section
- **Current state:** Placeholder text provided for all three principles, marked with `<!-- TODO(rob) -->`
- **Action needed:** Replace with Rob's actual leadership principles and descriptions

### 3. Selected Work Results (4 items)
- **Location:** "Selected work" section, end of each project card
- **Current state:** Empty `<strong>Result:</strong> <!-- TODO(rob) -->` placeholders
- **Action needed:** Add specific outcomes, metrics, or impact statements for each project:
  - Tax and fee processing system
  - PCI financial integration
  - Enterprise-wide security system
  - Salesforce and Azure cloud transformation

## Design Credits

- **Owner:** Rob Fritzemeier
- **Designer:** Isho
- **Builder:** Kaihatsu
- **Host:** Cloudflare Pages

## License

All rights reserved © 2026 Rob Fritzemeier
