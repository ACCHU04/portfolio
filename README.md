# Acchutha K S — Portfolio

A static site with no build step, no dependencies and no framework. Vercel serves the files as they are.

```
index.html               the whole site (HTML, CSS and JS in one file)
avatar.webp              the avatar photo in the hero
favicon.png              the icon shown in the browser tab
Acchutha_KS_Resume.pdf   the file the "Resume" buttons download
```

## Hosting on Vercel (free, from the GitHub repo)

1. Go to https://vercel.com and sign in with the GitHub account that owns the repo.
2. Click **Add New… → Project**, then **Import** the `ACCHU04/portfolio` repo.
3. Leave every setting at its default:
   - **Framework Preset** — `Other`
   - **Build Command** — empty
   - **Output Directory** — `/`
   - **Root Directory** — `/`
4. Click **Deploy**. The site is live in about 30 seconds.
5. Optional: claim a cleaner address in **Settings → Domains** (for example `portfolio.vercel.app`).

Vercel picks up every push to `main` and redeploys automatically.

## If the site is not on GitHub yet

Push the files first, then import. Create the repo **empty** — do not tick "Add a README file",
`.gitignore` or a license, because that creates an unrelated commit and the first push is rejected.

```
git remote add origin https://github.com/ACCHU04/portfolio.git
git push -u origin main
```

## Updating later

- **New resume:** replace `Acchutha_KS_Resume.pdf`, keeping the same file name. Nothing else to change.
- **Project text and links:** in `index.html`, search for `const PROJECTS`. Each project has `repo:` (its GitHub link), `stack:` and `pts:` (the bullet points).
  Crime-AI and SwiftDash have no `repo:` yet. Add one (for example `repo:'https://github.com/ACCHU04/your-repo',`) and the button switches from "View GitHub profile" to "View repository".
- **Skills:** search for `const SKILLS`.
- **Hackathons and highlights:** search for `const HIGHLIGHTS`.
- **Pipelines:** search for `const PIPES`.
- **Tool logos:** search for `const TOOLS`.

## Link previews

Social previews need **absolute** image URLs. `index.html` currently points at
`https://portfolio.vercel.app/avatar.webp` in the `og:image` and `twitter:image` tags.

If the real domain ends up different, change these four values in `index.html`:

- `og:image`
- `twitter:image`
- `og:url`
- `rel="canonical"`

Search the file for `portfolio.vercel.app` to find every occurrence at once. Without this, WhatsApp
and LinkedIn previews show a blank card.

After the site is live, add the URL to the "Portfolio" link on the resume.
