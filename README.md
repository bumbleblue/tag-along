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

## Deploying to Netlify

1. Push this repo to GitHub.
2. On [Netlify](https://app.netlify.com/): **Add new site → Import an existing project**, pick the repo. Build command `npm run build` and publish directory `_site` are read from `netlify.toml` automatically.
3. **Enable the contact form:** Site configuration → Forms → Enable form detection (Netlify no longer enables this by default). Submissions arrive under the "contact" form; set up an email notification under Forms → Notifications.
4. **Custom subdomain:** Domain management → Add a domain → enter your subdomain (e.g. `tagalong.example.com`). Then, at your DNS provider, add a **CNAME record** pointing that subdomain to your Netlify site (`<sitename>.netlify.app`). Netlify provisions HTTPS automatically after DNS propagates.
5. Update `url` in `src/_data/site.json` to the final address (it's used for `sitemap.xml`, canonical URLs, and social previews) and `github` to this repo's URL.

Old URLs from the previous Persona site (`/Playbook`, `/Upcoming-Events`, …) are redirected in `src/_redirects`, so existing links keep working.

## Checklist before going live

- [ ] `src/_data/site.json`: set `url` and `github`
- [ ] `src/imprint.md`: fill in the Impressum (legally required in Germany) and delete the TODO box
- [ ] Netlify: enable form detection, add a form notification email
- [ ] Verify the code-of-conduct email address in `site.json` still works

## License

The entire site — texts, playbook, design — is [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). Fork it, put your city's name on it, and go sing.

The [code of conduct](src/code-of-conduct.md) is adapted from the Citizen Code of Conduct (Stumptown Syndicate), CC-BY-SA 3.0.
