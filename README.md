# Creator Preflight

**One transcript in. Chapters, caption QA, metadata checks, and a release pack out.**

Creator Preflight is a local-first pre-publish quality gate for video creators. Paste a timestamped transcript plus the planned title and description; the app compiles chapter markers, checks caption readability, audits metadata/CTA/link basics, assigns a deterministic readiness score, and exports Markdown/JSON release packs.

> Built from scratch on September 3, 2026 for the **AI Content Engine Hackathon**. No paid service, external API, backend, account, or upload is required.

## Live demo

https://senih25.github.io/creator-preflight/

### 20-second judge test

1. Open the live demo and click **Load demo**.
2. Confirm the deterministic result: **99/100**, **9 chapters**, **12 caption cues**, **1 item to review**.
3. Open **Chapters** to see generated timestamp navigation.
4. Open **Release pack** to see publishing-ready Markdown.
5. Try **Download JSON**, or click **Import SRT/VTT** (or drag a caption file onto the transcript box) to run it on a real caption export.

## What it automates

- **Native caption import** — reads `.srt` and `.vtt` files exported from editors via file picker, drag-and-drop, or smart paste; conversion stays in the browser with no upload or API.
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

## What it replaces (value)

On the built-in demo (12 caption cues), Creator Preflight compiles **9 chapter markers** and runs **11 deterministic publish checks** across metadata, captions, chapters and CTA/links in one pass, then emits a copy-ready Markdown release pack and a JSON report. It replaces a repeated manual pre-publish pass: drafting chapter timestamps, scanning caption lines for readability risks, checking metadata/CTA/link presence, and assembling release notes.

## Judging alignment

**Functionality (30%):** native `.srt`/`.vtt` import, transcript parsing, chapter generation, caption-density calculations, metadata checks, scoring, Markdown/clipboard output and JSON export.

**Creativity (20%):** a private, deterministic transcript-to-release compiler with inspectable rules and zero-upload handling of unreleased creator material.

**Technical execution (30%):** zero-dependency single-file static deployment, deterministic inspectable rules, safe HTML escaping, responsive UI, no runtime secrets or network dependency. Live Chrome audits measured Accessibility / Best Practices / SEO / Agentic Browsing at **100 / 100 / 100 / 100** (45/45 audits pass), with mobile 390×844 **LCP 152 ms · TTFB 3 ms · CLS 0.00**. A temporary headless-Chromium regression harness passed **26/26** import, edge-case, XSS and baseline assertions; the public QA ledger documents the cases.

**Real-world usefulness (20%):** targets the repetitive gap between “edit finished” and “publish” and now accepts `.srt` / `.vtt` caption files creators already export.

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
