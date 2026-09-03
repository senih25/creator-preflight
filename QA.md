# Creator Preflight — QA Evidence

Validated with Chrome DevTools MCP on September 3, 2026 against the public GitHub Pages deployment.

## Acceptance summary

| Check | Result |
| --- | --- |
| Public HTTPS deployment | PASS |
| Login required | NO |
| Demo loads without external API | PASS |
| Timestamp parser | PASS |
| Chapter compiler | PASS |
| Caption QA | PASS |
| Metadata / CTA / link QA | PASS |
| Deterministic readiness score | PASS |
| Findings / Chapters / Release pack tabs | PASS |
| Markdown release pack | PASS |
| JSON export control present | PASS |
| Mobile 390×844 layout | PASS |
| External analysis network dependency | NONE |

## Deterministic demo result

Using the built-in `Load demo` case:

- Title: `7 YouTube SEO mistakes costing you views`
- Primary keyword: `YouTube SEO`
- Transcript cues parsed: **12**
- Chapters compiled: **9**
- Items to review: **1**
- Readiness score: **99/100**
- Status: **Ready with minor checks**
- Warning: one caption line over 84 characters

The same demo produced the same result in desktop and mobile emulation.

## Chapter output

The demo generated these chapter markers:

- 0:00 Most creators do not have a content
- 0:52 Mistake one is writing the title after
- 2:21 Your first two description lines need to
- 3:07 Mistake three is treating chapters like decoration
- 4:02 Mistake four is publishing auto captions without
- 5:11 Mistake five is adding links without checking
- 6:06 Mistake six is asking the viewer to
- 7:12 Mistake seven is skipping a final metadata
- 8:08 The simplest fix is a repeatable checklist

## Network / console note

The app itself has no runtime API or backend dependency. During the first Pages deployment test, GitHub Pages returned a temporary 404 while the deployment was building. After deployment, the document request returned HTTP 200.

The only remaining browser-console 404 observed was the browser's optional request for `/favicon.ico`; this does not affect application functionality or analysis.

## Privacy verification

The application performs its analysis in browser memory. No application XHR/fetch request is required to run the demo, parse transcripts, calculate the score, compile chapters, or produce the release pack.

## Judge reproduction

1. Open https://senih25.github.io/creator-preflight/
2. Click **Load demo**.
3. Confirm **99/100**, **9 chapters**, **12 caption cues**, **1 item to review**.
4. Open **Chapters** and **Release pack**.
5. Replace the sample transcript with any timestamped transcript and run the preflight again.
