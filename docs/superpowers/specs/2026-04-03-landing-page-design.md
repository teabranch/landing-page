# TEA/Branch Landing Page Design

## Context

TEA/Branch (`teabranch`) is a GitHub organization that builds open-source AI infrastructure. The org needs a central landing page at `teabranch.dev` (served via GitHub Pages) to welcome visitors and direct them to the org's projects. Currently the repo contains only a README stub, LICENSE, and .gitignore — no site exists yet.

The two initial projects to feature are:

- **Open Responses Server** — API proxy that lets any AI backend speak OpenAI's Responses API
- **Open Bedrock Server** — Unified chat completions API supporting both OpenAI and AWS Bedrock

## Stack

- **Jekyll** with no theme gem (custom HTML/CSS layout)
- **GitHub Pages** with custom domain `teabranch.dev`
- Gemfile: `jekyll ~> 4.3`, `jekyll-seo-tag`

## Visual Style

Clean & Modern on a warm cream palette with green leaf accents.

### Color Palette

| Token | Value | Usage |
|-------|-------|-------|
| Background | `#FFFAF5` | Page body |
| Card background | `#FFFFFF` | Project cards |
| Card border | `#E5DDD4` | Warm neutral borders |
| Sidebar/muted bg | `#F5EDE4` | Secondary button hover |
| Text primary | `#2D2B27` | Headings, body text |
| Text secondary | `#6B6560` | Descriptions, muted text |
| Accent green | `#4a7c59` | Tags, primary buttons, links |
| Accent green light | `#e8f5e9` | Tag backgrounds |

### Typography

- System sans-serif stack: `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`
- Hero heading: 42px, 700 weight
- Card headings: 20px, 600 weight
- Body: 14-18px, regular weight

### Emoji Usage

- `🌿` — Org-level (header logo, hero, footer)
- `🍃` — Project-level (card titles, feature bullet markers, badge)

## Page Structure

### 1. Header

- Left: `🌿 TEA/Branch` logo/text (links to `/`)
- Right: `GitHub` link (to `github.com/teabranch`)
- Bottom border: 1px solid `#E5DDD4`

### 2. Hero Section

- Centered layout, max-width 700px
- Large `🌿` emoji (56px)
- Headline: "Open tools for **open models**" (green color on "open models")
- Subtext: "TEA/Branch builds open-source infrastructure that lets you use any AI model with any tool — no vendor lock-in."
- Badge pill: `🍃 MIT Licensed` (green background, white text, rounded)

### 3. Project Cards (2-column grid)

Two cards in a responsive grid (`1fr 1fr`, stacks to `1fr` on mobile).

Each card contains:

- **Header row**: Category tag (green pill, e.g., "API PROXY") + ghbtns.com GitHub star iframe widget
- **Title**: `🍃 Project Name` (h3)
- **Description**: 1-2 sentence summary
- **Features**: 4 bullet points, each prefixed with `🍃`
- **Action buttons**: "Docs" (green primary) + "GitHub" (cream secondary)

#### Open Responses Server Card

- Tag: `API PROXY`
- Star widget: `ghbtns.com/github-btn.html?user=teabranch&repo=open-responses-server&type=star&count=true&size=large`
- Description: "Use any AI backend with OpenAI's Responses API. Run Codex against Ollama, vLLM, or any OpenAI-compatible model."
- Features: Drop-in Responses API proxy, MCP tool integration, Streaming & SSE support, Docker & PyPI packages
- Docs link: `https://open-responses-server.teabranch.dev`
- GitHub link: `https://github.com/teabranch/open-responses-server`

#### Open Bedrock Server Card

- Tag: `UNIFIED API`
- Star widget: `ghbtns.com/github-btn.html?user=teabranch&repo=open-bedrock-server&type=star&count=true&size=large`
- Description: "A single chat completions endpoint that works with both OpenAI and AWS Bedrock models. Switch providers without changing code."
- Features: Provider-agnostic chat API, OpenAI + Bedrock support, Knowledge base integration, File API support
- Docs link: `https://open-bedrock-server.teabranch.dev`
- GitHub link: `https://github.com/teabranch/open-bedrock-server`

### 4. Footer

- Top border: 1px solid `#E5DDD4`
- Single line: `🌿 TEA/Branch — Open source under MIT License — GitHub`
- Links in green accent color

## Card Interaction

- Hover: subtle lift (`translateY(-2px)`) + stronger shadow
- Star widget: native GitHub button behavior (opens GitHub star flow)
- Docs/GitHub buttons: standard link navigation

## Responsive Behavior

- Cards: 2-column grid above 768px, single column below
- Header: flex-wrap for narrow screens
- Hero: fluid padding, text scales naturally
- All max-widths use relative units where practical

## File Structure

```
landing-page/
├── _config.yml          # Jekyll config with custom domain, SEO
├── _layouts/
│   └── default.html     # Base layout with head, header, footer
├── _includes/
│   ├── header.html      # Site header
│   └── footer.html      # Site footer
├── assets/
│   └── css/
│       └── style.css    # All styles (single file, no preprocessor needed)
├── index.html           # Landing page content
├── CNAME                # Custom domain: teabranch.dev
├── Gemfile              # Jekyll + plugins
└── .gitignore           # Add _site/, .jekyll-cache/, etc.
```

## GitHub Pages Configuration

- Custom domain: `teabranch.dev` (CNAME file in repo root)
- Build: Jekyll via GitHub Pages default action
- Base URL: `/` (apex domain, no path prefix)

## SEO

- `jekyll-seo-tag` plugin for meta tags
- Title: "TEA/Branch — Open tools for open models"
- Description: "Open-source AI infrastructure by TEA/Branch. Use any AI model with any tool."

## Verification

1. Run `bundle exec jekyll serve` locally and verify the page renders correctly
2. Check responsive layout at 320px, 768px, and 1200px widths
3. Verify GitHub star iframes load and are clickable
4. Verify all Docs and GitHub links point to correct URLs
5. Validate HTML with no errors
6. Run `markdownlint-cli2` on any markdown files
