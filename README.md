# pantrimony.github.io

Static host for Pantrimony: the app-links `assetlinks.json`, the hosted error pages
(`/errors/{slug}`) and the privacy policy.

`.nojekyll` is required — Jekyll ignores dot-directories, which would make
`/.well-known/assetlinks.json` 404.

## Published from hashharit/pantrimony — do not hand-edit

`errors/`, `privacy/` and `.well-known/` are **build output**. The `site`
workflow in `hashharit/pantrimony` regenerates them from that repo on every
push to `main` that touches `web/`, `design/errors.json`, `design/tokens.json`
or `scripts/build_site.py`, and overwrites whatever is here. An edit made
directly in this repo will be silently replaced by the next publish.

To change any of them, edit the source in `hashharit/pantrimony`:

| Here | Source |
|---|---|
| `errors/` | `design/errors.json` |
| `privacy/` | `web/privacy/body.html` |
| `.well-known/` | `web/.well-known/` |

Everything else in this repo — `CNAME`, `.nojekyll`, `index.html`, this README
— is left alone by the workflow. **Never delete `CNAME`**: GitHub created it
with the custom domain, and removing it takes `pantrimony.com` offline. The
workflow refuses to publish if it is missing.
