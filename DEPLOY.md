# Deploying to alenewecker.com

The domain is registered at Squarespace. The site is hosted for free on GitHub Pages.

## 1. Push to GitHub

    gh repo create alenewecker --public --source=. --push

## 2. Turn on GitHub Pages

Repo → Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
The `CNAME` file in this repo already sets the custom domain to `alenewecker.com`.

## 3. Point the Squarespace domain at GitHub

Squarespace → Domains → alenewecker.com → **DNS** → DNS Settings:

1. Delete the Squarespace Defaults record group (the A records and `www` CNAME that point at Squarespace).
2. Add these custom records:

| Host | Type  | Data                     |
|------|-------|--------------------------|
| @    | A     | 185.199.108.153          |
| @    | A     | 185.199.109.153          |
| @    | A     | 185.199.110.153          |
| @    | A     | 185.199.111.153          |
| www  | CNAME | `<github-username>.github.io` |

DNS can take anywhere from a few minutes to a few hours to propagate. Once GitHub shows
the domain as verified, tick **Enforce HTTPS** on the Pages settings screen.

## Alternatives

Netlify or Cloudflare Pages work too: connect the repo, leave the build command empty,
set the publish directory to `/`, and follow their custom-domain DNS instructions in Squarespace.
