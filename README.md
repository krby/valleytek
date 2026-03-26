# Valleytek Website

Marketing home page for Valleytek.

## Tech Stack

Astro as a SSG + Sveltia as headless Git based CMS so all content is static and has free options for hosting
- **Astro** 5.0 — static site generator
- **Tailwind CSS** 4.0 — utility-first styling
- **TypeScript**
- **Lucide Icons** — SVG icon library
- **Marked** — markdown rendering (FAQ page)
- **Web3Forms** — contact form submissions
- **Sveltia CMS** — Headless Git-based CMS

## Project Structure

```
src/
├── pages/          # Astro pages (index, about, services, faq, contact)
├── content/
│   ├── pages/      # Page content as markdown + YAML frontmatter
│   └── services/   # Individual service descriptions (6 services)
├── components/     # Header, Footer, ServiceIcon
├── layouts/        # BaseLayout wrapper
├── data/           # company.json (contact info, certifications)
└── styles/         # global.css (Tailwind theme: navy/crimson)
public/
├── images/         # Hero, product, and facility photos
└── admin/          # Sveltia CMS config
```

## Useful Commands

```bash
# Main dev loop
npm install
npm run dev        # Start dev server (localhost:4321)

# Previewing prod build
npm run build      # Output static site to dist/
npm run preview    # Preview the production build locally
```

## Content Management System (CMS)

The site includes [Sveltia CMS](https://github.com/sveltia/sveltia-cms), a browser-based content manager that lets non-technical users edit all site content without touching code.

### Accessing the CMS

Navigate to `/admin/` on the deployed site (e.g. `https://yoursite.com/admin/`). Log in with your GitHub account and the CMS reads and writes directly to the repo.

### Controlling what site editors can edit

All editable fields are defined in [public/admin/config.yml](public/admin/config.yml) using Sveltia's [content modeling](https://sveltiacms.app/en/docs/content-modeling) pattern.

### Content model

The CMS is structured around **collections** — groups of related content. Each collection has **fields** that define what editors can change, and each field has a **widget type** (`string`, `text`, `markdown`, `image`, `list`, etc.) that controls the editor UI.

This site uses these collections:

| Collection | Type | Purpose |
|---|---|---|
| **Pages** | File collection | One fixed entry per page (Home, About, Services, FAQ, Contact). Editors update fields but can't add/remove pages. |
| **Services** | Entry collection | Editors can create, edit, reorder, and delete service items freely. |
| **Site Settings** | File collection | Single entry for company-wide data (name, address, logo, social links, certifications). |

See the [Sveltia CMS docs](https://sveltiacms.app/en/docs/intro) for more info

