# Oak Ridges Advisory

## Project overview

This is the Hugo website for Oak Ridges Advisory, an operator-led advisory firm working across Southeast Asia and Canada. The site uses the Pico Corp Hugo theme as a Git submodule.

The firm's three domains are:

- Financial services, including fintech
- Energy, including energy transition and decentralisation
- Food and agriculture, with a focus on product development, commercialization, and trade

Cross-domain advisory services include market entry, venture building, and AI and innovation. Keep these distinct from the three sector domains in site copy and page structure.

## Project structure

- `hugo.toml`: site identity, theme settings, navigation, and global copy
- `content/_index.md`: home page, composed from theme sections
- `content/about/_index.md`: firm and principal biographies
- `content/contact/_index.md`: contact information and routing
- `content/services/`: service and domain pages; front matter drives the theme's service cards and layouts
- `data/`: shared process and values content
- `assets/css/custom.css`: site-level styles, brand presentation, and homepage globe backdrop
- `assets/`: source logos and other processed assets
- `static/`: files copied directly to the published site, including logo variants and the globe image
- `layouts/`: site-level overrides of selected theme templates and partials
- `themes/hugo-theme-pico-corp/`: theme submodule; read its `README.md` for template and front matter conventions
- `.github/workflows/hugo.yml`: GitHub Pages build and deployment
- `public/`: generated output; do not edit or commit it

## Hugo workflow

Initialize the theme when cloning:

```sh
git submodule update --init --recursive
```

Run the local development server:

```sh
hugo server -D
```

Build the production site:

```sh
hugo --minify
```

The theme requires Hugo 0.146.0 or newer. The GitHub Actions workflow installs Hugo 0.168.0, builds on pushes to `main` or manual dispatch, and deploys through GitHub Pages. In the repository's Pages settings, the publishing source must be **GitHub Actions**.

## Content and theme conventions

- Follow the Pico Corp theme's `sections` front matter pattern for home and About page layouts. Use supported section types from the theme README.
- Service pages use the theme's service front matter fields such as `weight`, `icon`, `summary`, `lead`, `highlights`, `benefits`, `process`, and `deliverables`.
- Keep service icons in the theme's SVG sprite. The site overrides `layouts/_partials/utils/icon-sprite.html` to add the local `leaf` icon; use an existing sprite symbol or extend this override when adding another icon.
- Use the site-level templates in `layouts/` for local customizations. Do not edit theme files for site-specific changes, since the theme is a submodule and updates should remain straightforward.
- Keep CSS changes in `assets/css/custom.css`; the theme includes it in the generated stylesheet.
- Reference site URLs using Hugo's `relURL` or page references where possible so links work on custom domains and GitHub Pages paths.
- Preserve responsive behavior and both light and dark color schemes. The homepage globe backdrop has separate light and dark gradient tuning, and the footer must remain above its fixed background layer.

## Brand and factual accuracy

- Use **Oak Ridges Advisory** consistently.
- Keep the regional focus on Southeast Asia, with the firm's Canadian roots and Canada–Southeast Asia connections.
- Do not invent the name, title, contact details, or credentials of the food and agriculture principal. Current copy only states the supplied background: a former Trade Commissioner with the Embassy of Canada, long-standing regional residence and connections, and food and agriculture expertise.
- For John Januszczak, use source-supported biography from `https://januszczak.org/` and the local `ceo-playbook` project when available. Do not transfer personal achievements to Oak Ridges Advisory as firm-wide claims without support.
- Do not invent an Oak Ridges email address, phone number, office, client list, project, metric, or regulatory credential. The current contact page routes relevant enquiries to John's published contact page.
- Food and agriculture service copy should cover product development, commercialization, and trade.
- Write in clear, concise language. Prefer concrete descriptions of the work and avoid generic consulting claims or unsupported promises.
