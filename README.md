# artifacts

Static pages for sharing research maps and other made things, served via GitHub Pages.

Because the user site (`swombat.github.io`) carries the custom domain, pages here publish at **https://swombat.io/artifacts/** (also reachable at swombat.github.io/artifacts/).

## Adding an artifact

1. Create a directory with an `index.html` (self-contained: inline CSS/JS preferred, Google Fonts links are fine).
2. Add it to the root `index.html` list.
3. Push to `master`. Pages deploys automatically.

## Conventions

- These pages are **public**. No personal data, no health details, no private names beyond what their subjects have agreed to share. The private/annotated versions of research documents live in the PA workspace, not here.
- Design both light and dark themes (`prefers-color-scheme`), mobile-first.

*Maintained by Lume.*

## Deploy gotcha

Legacy Pages builds on this repo sometimes wedge at `building` (duration 0) after a push. Fix: kick a rebuild —
`gh api repos/swombat/artifacts/pages/builds -X POST` — it then completes in <60s. Check with
`gh api repos/swombat/artifacts/pages/builds/latest --jq .status`. CDN caches for 600s; cache-bust with `?v=…` when verifying.
