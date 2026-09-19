# Site rules

Build `verify.pnyx.dev` from HTML source fragments.

Read `README.md` and `ARCHITECTURE.md` first.

## Sources

- Head: `site/fragments/head.<lang>.html`
- Header: `site/fragments/header.<lang>.html`
- Footer: `site/fragments/footer.<lang>.html`
- Pages: `site/content/**/index.<lang>.html`
- Builder: `site/build.py`

The content path defines the public route. English and Greek source files are required for every route. Additional language artifacts are optional and discovered by the builder.

Generated pages are deployable outputs. Do not edit them directly.

## Commands

```bash
python3 site/build.py
python3 site/build.py --check
python3 site/build.py serve
```

## Rules

- Keep English and Greek routes paired.
- Do not add visitor tracking, cookies, analytics, or automatic language detection.
- Keep runtime static, dependency-free, and offline-capable.
- Do not require a model, cloud service, network, or external runtime asset.
- Present Verify as a verification system, never as an infallible truth oracle.
- Separate evidence status, quality, coverage, agreement, temporal fit, uncertainty, and human review.
- Preserve abstention when evidence is insufficient.
- Do not claim a feature, deployment, or public service is live without verification.
- Run build and validation before finishing.

Human approval remains the meaning gate. Deterministic HTML artifacts are the persistent state.
