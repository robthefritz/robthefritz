# Rob Fritzemeier – Personal Resume Website

A clean, accessible static resume website for Rob Fritzemeier, hosted on Cloudflare Pages at [robthefritz.com](https://robthefritz.com).

## Structure

This is a single-page static website with minimal JavaScript (theme toggle only), no build step, and no dependencies. All files are in the `public/` directory:

```
public/
├── index.html          # Main resume page
├── style.css           # Styles with light/dark mode support
├── llms.txt            # Plain-text summary of the site for AI agents/assistants
├── logo.svg            # RF logo, master copy (ring + monogram)
├── favicon.svg         # SVG favicon (adapts to light/dark tab bars)
├── favicon-32.png      # PNG favicon fallback
├── apple-touch-icon.png # 180px home-screen icon
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

## Deploys

Merges to `main` auto-deploy `public/` (no build step) to the existing Cloudflare Pages project `robthefritz` (direct upload, production branch `main`) via [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml). Same-repository pull requests targeting `main` get a Pages preview for the PR branch; the preview URL is posted on the PR and updated in place. Fork pull requests and PRs whose head branch is `main` are not deployed.

GitHub Actions uses repository secrets `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID`. Point `robthefritz.com` at the Pages project in the Cloudflare dashboard.

Browsers cache `style.css` and the icons for up to 4 hours. When you change one, bump its `?v=` number in both `index.html` and `404.html` so visitors get the new file right away.

## Features

- **Theme toggle:** Light/Dark/Auto modes with localStorage persistence and no-JS fallback
- **Responsive design:** Mobile-first layout that works at 360px, 768px, and 1280px widths
- **Expandable timeline:** Native `<details>/<summary>` elements for role details (newest role open by default)
- **Expandable project briefs:** "Learn more" slots on Selected Work cards, same native details pattern — the place to layer in deeper project detail over time
- **Dark mode support:** Automatically adapts to user's system preferences or manual selection
- **Accessible:** Semantic HTML, skip link, proper headings, visible focus states, 4.5:1 contrast ratio
- **Print-friendly:** Optimized print stylesheet for resume PDFs (all timeline entries forced open, "Learn more" slots hidden)
- **Minimal dependencies:** Only ~100 lines of vanilla JavaScript for theme toggle; everything else works without JS
- **SEO ready:** Open Graph tags, Twitter Card support, sitemap.xml, robots.txt, canonical URL
- **AI-ready:** schema.org `Person` structured data and `llms.txt` so search engines and AI assistants can represent Rob accurately

## Content Sections

1. **Hero** – Name, headline, and links (Email, LinkedIn, GitHub; PDF when added)
2. **At a glance** – Current role, focus, leadership approach, and foundation
3. **Now** – Current focus (draft content, awaiting Rob's review)
4. **How I Lead** – Three leadership principles (draft content, awaiting Rob's review)
5. **Timeline** – 18 years of career progression at CarMax (expandable entries; recent three roles carry draft bullets)
6. **Selected Work** – Four key projects with problem/action/result format; each card has a "Learn more" expansion slot for deeper briefs over time
7. **Skills** – Four skill categories (draft content, awaiting Rob's review)
8. **Education & Certifications** – Degree and professional certifications
9. **Contact** – Connection options

## Content Drafts for Review

The following blocks were drafted (from the LinkedIn public profile and the site's own content) and are marked with `DRAFT(rob)` comments in `public/index.html`. **All of them need Rob's read-through and edit before the site is committed.** No facts were invented beyond what the existing site/LinkedIn state; where a specific number or outcome would strengthen a statement, one was deliberately left out so Rob can supply a real one.

1. **At a glance** section (4 items: current role, focus, leadership, foundation)
2. **Now** card (current focus paragraph + updated date)
3. **How I lead** principles (3 titles + descriptions)
4. **Timeline** bullets for the three recent roles (Senior Manager, Manager, Lead Software Developer)
5. **Selected work** Problem statements (4 cards)
6. **Selected work** Result statements (4 cards)
7. **Selected work** "Learn more" briefs (4 expandable blocks — the layer-in-more-detail slots, safe to replace)
8. **Skills** categories and items (4 groups)
9. **`llms.txt`** and JSON-LD `Person` schema — mirror the site content; update alongside any content edits

## TODO Items

### 1. Rob reviews the drafted content (list above)
- **Action needed:** Preview locally, edit every `DRAFT(rob)` block, remove the marker comments when satisfied

### 2. Resume PDF (2 locations)
- **Locations:** Hero section and Footer
- **Current state:** "Download resume (PDF)" buttons are commented out with `<!-- TODO(rob): add /rob-fritzemeier-resume.pdf to enable this button -->`
- **Action needed:** Add the file at `/public/rob-fritzemeier-resume.pdf` and uncomment the buttons

### 3. Optional follow-ups (tracked on GitHub)
- v1.1: #10 privacy-friendly analytics (Cloudflare Web Analytics needs no build step), #11 headshot photo, #13 writing/notes section
- Later: #8 projects page (AlternativeWeather, NihongoTranscriber, etc.), #9 colleague voices, #12 contact form

## Previously Open TODOs

- ~~Email address~~ – resolved: `robthefritz@gmail.com` is live in Hero and Contact
- ~~"Now" card content~~ – drafted (see drafts list)
- ~~Leadership principles~~ – drafted (see drafts list)
- ~~Selected Work problem statements~~ – drafted (see drafts list)
- ~~Selected Work result statements~~ – drafted (see drafts list)

## Acceptance Checklist Results

✅ **Responsive:** Tested at 360px, 768px, and 1280px widths – looks correct in all sizes  
✅ **Light & Dark modes:** Both themes render correctly with proper contrast  
✅ **Works without JS:** Theme follows device preference; timeline details are fully functional  
⚠️ **Print layout:** Re-verify page count now that the Now, How I lead, Selected work, and Skills sections are restored  
⚠️ **Page weight:** Re-verify after content review (was ~52KB before sections were restored)  
✅ **Contrast:** Body text passes WCAG AA (4.5:1) in both light and dark modes  
✅ **Touch targets:** All interactive elements meet 44px minimum  
✅ **Accessibility:** Semantic HTML, skip link, proper ARIA labels, visible focus states

## Design Credits

- **Owner:** Rob Fritzemeier
- **Designer:** Isho
- **Builder:** Kaihatsu
- **Host:** Cloudflare Pages

## License

All rights reserved © 2026 Rob Fritzemeier
