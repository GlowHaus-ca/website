# Glow Haus website

Marketing and price-list site for **Glow Haus**, a beauty studio in London, Ontario.

- **`site/`** — the deployable static site. Open `site/index.html`, or serve the folder. See [`site/README.md`](site/README.md) for running, deploying, and PDF export.
- **`design/`** — the original design handoff (HTML prototypes, prototype runtime helpers, and the handoff brief). Reference only; not deployed.

## Quick start

```sh
cd site
python3 -m http.server 8080
# → http://localhost:8080
```

## Deploying

**AWS Amplify Hosting:** connect this repo in the Amplify console and pick the
`main` branch. The included `amplify.yml` publishes the `site/` folder with no
build step, so no settings need changing. Add a custom domain under
*Hosting → Custom domains* once it is live.

**Any other static host** (Netlify, Vercel, Cloudflare Pages, GitHub Pages):
set the publish directory to `site/` and leave the build command empty.
