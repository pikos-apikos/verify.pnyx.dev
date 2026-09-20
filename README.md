# verify.pnyx.dev

Public website for **Verify**, PNyx's global, multilingual evidence-verification engine.

Verify is not an AI truth oracle. Its purpose is to turn a claim into a traceable evidence record: exact sources, relevant excerpts, provenance, conflicts, uncertainty, and an explicit `insufficient evidence` state.

Verification also has an execution cost. The product contract therefore treats attributable resource usage as run evidence and monetary cost as a derived, versioned estimate. If pricing cannot be established, cost is `unknown`, not zero.

The website follows the deterministic static setup used by [`pnyx.dev`](https://github.com/pikos-apikos/pnyx.dev). The runtime is dependency-free HTML and CSS.

## Build

```bash
python3 site/build.py
python3 site/build.py --check
```

Generated HTML is committed for transparent review and buildless static hosting.

## Local preview

```bash
python3 site/build.py serve
```

## Cloudflare Pages

- Production branch: `main`
- Framework preset: `None`
- Build command: `python3 site/build.py --check`
- Build output directory: `.`
- Root directory: `/`

## Product status

This repository currently publishes the product contract and research direction. It must not imply that a public verification service is already operational.

## Licensing

Software and executable material follow the PNyx EUPL-1.2 policy. Narrative and protocol material follow CC BY-SA 4.0. See the [PNyx licensing policy](https://github.com/pikos-apikos/pnyx/blob/main/LICENSING.md).
