# Claude guidance — grafana/

This directory is a Grafana Cloud Git Sync target. Rules:

- `dashboards/*.json` is machine-authored by Grafana. Do not restructure,
  reformat, or hand-edit dashboard JSON. If a dashboard change is requested,
  direct the user to the Grafana UI.
- Safe to edit: `README.md`, this file, any CI under `.github/workflows/`
  scoped to this directory.
- Alerts and data sources are not yet covered by Git Sync (as of 2026-04).
  If the user asks to manage those as code, use Terraform (`grafana` provider)
  or Grizzly — not ad-hoc JSON in this tree.
