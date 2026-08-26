# Tag along

The website for **Tag along** — an event concept you can copy and remix: everything you need to kickstart a lightweight barbershop tag-singing event in your community.

Built with [Eleventy](https://www.11ty.dev/). Every page is a plain markdown file — edit text without touching any code. No frameworks, no client-side JavaScript, self-hosted fonts, ~no dependencies to rot.

## Editing the site

| Page | File |
|---|---|
| Home | `src/index.md` |
| Playbook | `src/playbook.md` |
| Upcoming events | `src/events.md` |
| Sample invitation | `src/invitation.md` |
| Code of conduct | `src/code-of-conduct.md` |
| Get in touch (form) | `src/contact.md` |
| Imprint & privacy | `src/imprint.md` |

Site-wide settings (name, **canonical URL**, contact email, GitHub link) live in `src/_data/site.json`. The layout is `src/_includes/base.njk`; design tokens (colors, fonts) are CSS variables at the top of `src/assets/css/style.css`.

**Adding an event:** add a section to `src/events.md`, commit, push — Netlify redeploys automatically.

**Adding a page:** copy any `.md` file, change `title`, `permalink`, and `description` in the frontmatter. It appears in `sitemap.xml` automatically; add it to the footer list in `base.njk` if it should be linked everywhere.

## Local development

```bash
npm install
npm start        # dev server with live reload at http://localhost:8080
npm run build    # writes the production site to _site/
```

## License

The entire site — texts, playbook, design — is [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). Fork it, put your city's name on it, and go sing.

The [code of conduct](src/code-of-conduct.md) is adapted from the Citizen Code of Conduct (Stumptown Syndicate), CC-BY-SA 3.0.
