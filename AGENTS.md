# AGENTS.md

Guidance for coding agents working in this repo.

## Project shape

- Single-file web app: `index.html`
- Sample inputs: `examples/`
- Deploy workflow: `.github/workflows/main.yml`

## Local run

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Editing rules

- Keep the app static (no build step) unless explicitly requested.
- Prefer small, focused edits.
- Preserve existing EXPLAIN wizard flow (query → plan → estimate).
- Keep sample files in `examples/` working for demo/testing.

## Documentation

- Update `README.md` when behavior or workflow changes.
- Keep setup/usage instructions copy-paste ready.
