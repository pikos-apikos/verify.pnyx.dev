# Architecture

## Goal

`verify.pnyx.dev` is buildable and reviewable with Python, a filesystem, and no network. It uses the same deterministic static-site contract as `pnyx.dev`.

## Static build

```text
site/content/**/index.<lang>.html
+ site/fragments/head.<lang>.html
+ site/fragments/header.<lang>.html
+ site/fragments/footer.<lang>.html
                ↓
         site/build.py
                ↓
      committed static HTML
```

The content path is the route registry. Every route requires paired `index.en.html` and `index.el.html` artifacts. English exports at the root; other languages export under their lowercase language code.

The builder contains no page content, navigation, metadata, or verification logic. It discovers, validates, composes, and writes static artifacts.

## Invariants

1. Source content and shared fragments live outside the builder.
2. English and Greek pages remain paired; additional translations are explicit artifacts.
3. Generated pages are never edited directly.
4. Unchanged inputs produce byte-identical outputs.
5. The public runtime has no JavaScript, external assets, trackers, cookies, or model dependency.
6. The website describes Verify's contract; it is not itself the verification engine.
7. Human approval remains the publication gate.

## Cloudflare Pages

- Production branch: `main`
- Framework preset: `None`
- Build command: `python3 site/build.py --check`
- Build output directory: `.`
- Root directory: `/`
