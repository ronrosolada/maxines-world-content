# Maxine's World — Content

Lesson content packages for the Maxine's World Grade 3 educational app.

## Structure

- `catalog.json` — Content catalog (v2) listing all available lesson packages
- `packages/` — Weekly lesson packages (`.zip`), one per subject/week

## Subjects

| Subject | Weeks |
|---------|-------|
| Filipino | 15 |
| English | 14 |
| Science | 9 |
| Mathematics | 9 |
| GMRC | 8 |
| Makabansa | 7 |
| **Total** | **62** |

## Schema

Each `.zip` package contains:
- `package.json` — metadata (subject, quarter, week, lesson IDs, capabilities)
- `lessons/*.json` — Individual lesson files
- `assets/*.svg` — Visual assets for lessons

Content is served via LAN-only Caddy server to the Android app.
