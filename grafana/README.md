# grafana

Grafana Cloud resources for personal infrastructure, managed as code.

## Layout

```
grafana/
  dashboards/   # Git Sync target — JSON managed by Grafana Cloud
  alerts/       # (future) alert rules, contact points, notification policies
  datasources/  # (future) data source definitions
```

## Git Sync

The `dashboards/` directory is the sync target for Grafana Cloud Git Sync
(GA 2026-04-20). Configuration:

- **Branch**: `main`
- **Path**: `grafana/dashboards`
- **Direction**: bidirectional

Git Sync covers dashboards and folders only. Alerts, data sources, contact
points, and library panels are out of scope at GA and are managed separately
(see sibling directories once populated).

## Editing

- **Dashboards**: edit in the Grafana UI. Use the UI's "save + open PR" flow
  for changes you want reviewed; direct saves commit to `main`.
- **Do not hand-edit `dashboards/*.json`** — Grafana owns that tree. Manual
  PRs are supported but should be rare (e.g., bulk rename, schema migration).

## Validation

PRs touching `grafana/**` run JSON validation in CI. UI-initiated direct
commits to `main` skip CI (they're already authored by Grafana).
