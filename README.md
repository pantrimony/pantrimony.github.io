# pantrimony.github.io

Static host for Pantrimony: the app-links `assetlinks.json`, the hosted error pages
(`/errors/{slug}`) and the privacy policy.

`.nojekyll` is required — Jekyll ignores dot-directories, which would make
`/.well-known/assetlinks.json` 404.

## /errors/

Generated — do not hand-edit. Source is `design/errors.json` in the backend
repo; rebuild with `uv run python scripts/build_error_pages.py <out>` and copy
`<out>/errors/` here. These back the RFC 9457 `type` URIs that every API
problem response carries.
