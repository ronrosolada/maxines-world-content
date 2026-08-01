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

## Delivery: bundled in the APK (no server)

Content is **bundled inside the Android APK at release time** — there is no
content server and the app never downloads content at runtime.

Release flow:

1. Author/update lessons here (the source of truth for content).
2. On each Maxine's World release, the current month/quarter packages are
   converted into the app's playable pack
   (`android/tools/convert_slm_to_pack.py` in the app repo, which ingests
   the SLM source) and committed into `app/src/main/assets/content-pack/`.
3. The signed APK ships with all bundled lessons — offline-first, child-safe,
   no network dependency, no tracking of what the child loads.

A content update = a new APK release. This is deliberate: the APK is the
single immutable versioning unit, and install/upgrade atomically replaces
content.
