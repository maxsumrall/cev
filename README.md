# cev

> Interactive ClickHouse `EXPLAIN` visualizer for query-plan debugging and performance analysis.

**cev** helps you turn raw ClickHouse explain output into an interactive graph with actionable optimization hints.

🌐 Live: **https://cev.shenandoah.io**

---

## Why cev?

Analyzing ClickHouse performance often requires multiple commands and a lot of manual parsing.

`cev` reduces this to a guided workflow:

1. Paste your original SQL query
2. Paste `EXPLAIN PLAN` output (JSON)
3. Paste `EXPLAIN ESTIMATE` output
4. Explore a visual execution tree + recommendations

---

## Features

- 3-step guided analysis wizard
- Interactive query-plan graph (zoom, pan, inspect)
- MergeTree index/selectivity details when present
- Built-in analysis checks with severity levels
- “Highlight in graph” actions for detected issues
- Summary metrics (nodes, joins, tables, granules)
- Included sample files in `examples/`

---

## Quick start (local)

### Prerequisites

- Modern browser (Chrome, Edge, Firefox, Safari)
- Access to a ClickHouse instance

### Run

From repo root:

```bash
python3 -m http.server 8080
```

Open:

```text
http://localhost:8080
```

No build step required — this is currently a static app.

---

## Usage

Click **Start Analysis** in the app and follow the wizard.

Run this in ClickHouse:

```sql
EXPLAIN plan indexes=1, json=1
<your_query>
```

Then run:

```sql
EXPLAIN estimate
<your_query>
FORMAT JSONEACHROW
```

Paste both outputs into the wizard and click **Visualize**.

---

## Example inputs

Use these files for a quick test:

- `examples/original-sql.txt`
- `examples/explain-plan.json`
- `examples/explain-estimate.json`

---

## Repository layout

- `index.html` — main application (UI + logic)
- `examples/` — sample SQL and explain payloads
- `.github/workflows/main.yml` — deployment workflow

---

## Contributing

Contributions are welcome.

Suggested process:

1. Open an issue (bug report, UX gap, feature idea)
2. Keep PRs focused and small
3. For UI/analysis logic changes, include before/after context

Good areas for first contributions:

- Better error handling for malformed EXPLAIN JSON
- Additional plan-node formatting improvements
- Documentation cleanup and examples
- Accessibility and keyboard navigation improvements

