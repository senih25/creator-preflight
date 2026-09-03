# Creator Preflight

**One transcript in. Chapters, caption QA, metadata checks, and a release pack out.**

Creator Preflight is a local-first pre-publish quality gate for video creators. Paste a timestamped transcript plus the planned title and description; the app compiles chapter markers, checks caption readability, audits metadata/CTA/link basics, assigns a deterministic readiness score, and exports Markdown/JSON release packs.

> Built from scratch on September 3, 2026 for the **AI Content Engine Hackathon**. No paid service, external API, backend, account, or upload is required.

## Live demo

https://senih25.github.io/creator-preflight/

### 20-second judge test

1. Open the live demo and click **Load demo**.
2. Confirm a readiness score, findings and parsed transcript metrics appear.
3. Open **Chapters** to see generated timestamp navigation.
4. Open **Release pack** to see publishing-ready Markdown.
5. Try **Download JSON**, or replace the sample with your own timestamped transcript.

## What it automates

- **Chapter compilation** — parses `MM:SS text` / `HH:MM:SS text` cues and creates spaced navigation markers.
- **Caption QA** — flags dense lines, possible high-speed segments, sparse timestamp data and excessive filler phrases.
- **Metadata QA** — checks title length, primary-keyword consistency, description depth, early topic reinforcement, CTA and URL presence.
- **Release readiness** — produces an explainable 0–100 score with good/warning/error findings.
- **Release pack** — generates Markdown plus a machine-readable JSON report.

## Why local-first

Draft transcripts can contain unreleased material. Creator Preflight uses no backend, analytics, external API, API key, account or persistence. All analysis is deterministic JavaScript in the current browser tab.

## Architecture

`metadata + timestamped transcript → parser → deterministic checks → readiness model → chapters/findings → Markdown + JSON`

The scoring model applies explicit penalties for concrete publishing risks. It does **not** claim to predict rankings, views, or recommendation-algorithm performance.

## Judging alignment

**Functionality:** real transcript parsing, chapter generation, caption-density calculations, metadata checks, scoring, clipboard export and JSON export.

**Creativity:** a compiler/linter for the last mile of creator publishing rather than another generic text generator.

**Technical execution:** zero-dependency static deployment, deterministic inspectable rules, safe HTML escaping, responsive UI, no runtime secrets or network dependency.

**Real-world usefulness:** targets the repetitive gap between “edit finished” and “publish” — checks that matter every upload but are easy to skip.

## Run locally

```bash
python -m http.server 8080
```

Then open `http://localhost:8080/`.

## Hackathon compliance

- Repository and working app created during the active hackathon window on **2026-09-03**.
- Solo project.
- No paid dependency or API.
- No scraping or external service automation.
- Public runnable source.

## License

MIT.
