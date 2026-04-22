# Changelog

## 2026-04-23 — Realism polish pass + public deployment

Closed the remaining "looks fake" gaps and deployed to GitHub Pages as a public static site. Everything below is shipped and visible in the live demo.

### Icon rewrite (no more emoji in structural chrome)

- **New SVG symbol library** — 17 service/connector logos (KCSO sheriff seal with 6-point star + KCSO cartouche, Azure AI Document Intelligence, WSP JIS shield, SharePoint disc+S-curve, Microsoft Graph faceted octahedron, Azure OpenAI knot in green, Microsoft Purview shield-with-check, Microsoft Teams T+silhouette, Outlook envelope+O, Odyssey gavel, Dataverse stacked cylinders, Power Automate, Copilot Studio flame, WA File & Serve, Approvals clipboard, Azure AI Language Aa-bubble, Trigger lightning, Condition diamond, Terminate check).
- **Multi-color Copilot flame** — `fiSparkle` now renders the 5-stop official gradient (cyan → purple → magenta → pink → orange) with an asymmetric 4-point shape + secondary spark. Replaces the single-color sparkle everywhere.
- **15 Fluent-style UI icons** — book, chat, plug, shield, chart, brain, bell, check, warn, DLP, filing, calendar, print, download, scale + 16 extras in the second batch (inbox, mail, sent, draft, junk, trash, home, folder, clock, people, star, lock, alert, palette, phone, megaphone).
- **6 Office file-type icons** with real brand-gradient squares (Word blue, Excel green, PowerPoint orange, Folder yellow, Template with TPL sublabel, PDF red).
- **KCPAO seal** — detailed 80px mark with scales of justice, navy+gold rings, and compact 40px version used on topbar + favicon.
- **Sheriff Report Intake icon** — purpose-designed SVG showing the handwritten → typed-and-sealed document transformation with an orange KCSO sheriff-star on the source and a gold KCPAO seal-with-check on the output.

### Emoji → SVG replacement pass (every structural UI place)

- Outlook sidebar (7 icons — Inbox, Calendar, Junk, Drafts, Sent, Deleted, New mail)
- OneDrive sidebar (6 icons — Home, My files, Recent, Shared, Favorites, Recycle bin)
- Teams left rail (5 icons — Chat, Teams, Calendar, Calls, Files)
- Power Automate flow strip (7 connector icons)
- Power Automate designer step cards (letters → connector SVGs for all 25 flow steps)
- Power Automate designer left-rail connections (9 service SVGs)
- Power Automate designer tabs (Report Intake + Purview marks)
- Copilot Studio hero + all section headers (Fluent SVGs everywhere)
- Copilot Studio knowledge/action rows (proper connector SVGs)
- Notification center (kind → proper SVG via `kcNotifIconId` map)
- Connector status dock (7 rows with mini SVG logos)
- SharePoint file list (JS-rendered file-type SVGs by extension)
- E-filing sequence overlay (4 recipient service logos)
- Topbar brand (KC text → proper KCPAO seal SVG)
- PowerPoint ribbon (🛡 Sensitivity → fiShield · ✨ Design → fiSparkle)
- Purview classification banners (🛡 → fiShield on both page 1 + page 2 + 3 sensitivity-label-bar uses)
- 10× Azure AD 🔐 lock icons in Entra ID identity chips
- Copilot Pages ✨ labels → fiSparkle
- Open-shifts 🚨 alert → fiAlert in PAO red
- OneDrive trash buttons + file-type icons

### Power Automate + Copilot Studio designers

- **Full Power Automate designer overlay** with Microsoft chrome — top breadcrumb, two flow tabs (Intake 13 steps, Redaction 12 steps), 3-column body (left rail + canvas + inspector), bottom run history. Canvas renders each step as a branded card with proper connector SVG + connector name. Condition steps create yes/no branches with independent columns.
- **Flow simulation engine** — "Test · Run now" button animates each step in sequence with realistic timing (Azure AI Doc Intelligence 2.1 s, OpenAI 1.8 s, etc.), spinner + auto-scroll to the current step, live elapsed-time and Azure-AI-cost counters, run-progress bar, branch picking (YES runs, NO marked skipped), and a completion summary card. Each run prepends a new entry to the run-history strip.
- **Full Copilot Studio agent designer** — Purple/pink gradient chrome, 6 tabs (Overview · Knowledge · Topics · Actions · Guardrails · Analytics), hero with agent stats, 5 knowledge sources with SharePoint paths, 5 conversation topics with trigger expressions, 7 action/connector cards with auth modes, 8 guardrail policies with on/off pills, 8 KPI tiles + 30-day usage trend chart.
- **Seeded telemetry data** — 28-day sparkline + 30-day analytics chart use realistic patterns (weekday base, weekend dips, Monday spikes, deterministic per-date hash, one visible outage day with red bar and hover-tooltip).

### Cross-canvas realism pack

- **Pipeline telemetry feed** in the Report Intake sidebar — streams real service calls with timestamps during extraction and drafting (Azure AI Document Intelligence, WSP JIS connector, SharePoint, Graph Word populateTemplate, Azure OpenAI with token counts + cost, Purview auto-labeler, Teams+Outlook notification, DLP block event).
- **Copilot reasoning trail** — floating bottom-right mini-window that streams Copilot's inner monologue during extraction and drafting with a live elapsed-time counter. Marks each step done-or-typing with cursor animation.
- **Ingest route badges** on each queue item (Axon Records, MDC upload, Precinct scanner, Det. email).
- **Low-confidence verify popover** — vehicle plate comes back at 72% confidence (cursive 8 looks like B). ⚠ Verify button opens a popover showing the cropped handwriting strip with the blurry 8, three OCR alternates with confidence scores, and a manual text input. Accepted value updates the extraction row and re-flashes any drafted declaration fields.
- **DLP block event** — during extraction, Det. Alvarado's attempt to CC the source PDF to personal Gmail is contained and logged with a toast + telemetry entry.
- **Connector status dock** (bottom-right, always-on) — 7 service rows with live-pulsing dots, proper SVG logos, latency/TTL indicators, signed-in user + Azure AD session expiry.
- **Running Azure AI cost ticker** — accumulates real per-step costs across the session with a bump animation on each add.
- **Keyboard shortcut cheatsheet** — `?` opens a two-column Fluent-style cheatsheet with shortcuts for Report Intake, Document Viewer, Discovery Redaction, and Global.
- **Collaborative presence + review comments** on the declaration — stacked avatars (Sarah editing + Marcus viewing 2 min ago + Maria viewed yesterday), autosave indicator (`just now → 3s ago → 1 min ago`), Azure AD session badge, and a pending review bubble from Marcus about the statute cite. Resolve/reply actions wired.
- **E-filing sequence overlay** — on Approve & File, a modal shows the 4 recipients (Superior Court Clerk, Defense/OPD via File & Serve, Det. Alvarado, Purview audit) stepping through queued → sending → ✓ accepted with real receipt numbers.
- **Document viewer** — full-screen file preview opens after filing. Left sidebar has Pages · Template Source · Copilot fields · Audit · Versions (3-row history) · Graph/tenant identifiers. Zoom controls, Print (print-scoped CSS), Download .docx/.pdf. ESC/click-outside closes. Page 2 with Certificate of Service renders scrollable.
- **In-viewer PII redaction** — gold "Redact PII" button scans the declaration, flashes blue targeting reticles on each field span, wipes each to a black bar (clip-path animation), shows a live status banner with variable sub-step text (NER model, CrR 4.7 checklist, sealed-juvenile index, CI-protection policy, geocoder). Post-scan toggles "Show originals"; "Save redacted copy" downloads.
- **Notification center** (topbar bell with badge count) — 4 tabs (All, @Mentions, Workflow, Security), items with unread dots + relative timestamps + proper brand SVGs, seeds with 5 events on load, grows live as you walk the demo.
- **Global Copilot FAB** — fixed bottom-right gradient-flame button with pulsing halo. Click or press `Ctrl+K` / `⌘K` from anywhere → gradient-bordered popover with 4 suggested prompts and a Copilot-styled input.

### Polish pass

- **Favicon** — compact KCPAO seal SVG embedded as data-URI; browser tab shows [seal] `King County Prosecuting Attorney's Office — Microsoft 365`.
- **Loading splash** — full-screen navy gradient with pulsing KCPAO seal + serif title + Copilot-gradient loading bar. 850 ms duration on first paint.
- **Dynamic home-page date** — reads `new Date()` so the hero stamp always says today.
- **Toast stack auto-cap at 3** — oldest dismisses when a 4th arrives.
- **Varied Purview label phrases** — Page 1 and Page 2 classification banners now read differently, matching real Purview provenance variance.
- **Scanning status variance during redaction** — cycles through 7 realistic sub-step narration lines with jittered timing.
- **Enhanced handwritten form** — 10 fields each use a different cursive font stack + rotation + letter-spacing + skew (simulates one officer writing quickly with variance); paper-grain texture via 8 layered radial gradients; existing coffee ring, fingerprint smudge, crossout, overwrite, and ink blot retained.
- **Right-click context menus** — on the declaration paper and Word redaction canvas. Declaration menu: Copy / Translate to Spanish / Cite in document / Summarize with Copilot (primary) / Compare versions / Version history / Search the web. Each fires a context-appropriate toast.
- **Custom Fluent tooltips** — `data-tip="…"` attribute system with 220 ms hover delay, proper dark-theme styling with backdrop blur, auto-flip to stay in viewport, supports inline `<kbd>` tags.

### Deployment

- Initialized git, created public GitHub repo, enabled GitHub Pages. Demo live at the URL in the repo description.
- `.gitignore` excludes the Python HTTP-server `__pycache__`, node modules, and macOS `.DS_Store`.

## 2026-04-22 (late evening) — Declaration upgraded to a real court filing with visible KCPAO templating

The auto-drafted declaration now looks like an actual Washington State Superior Court pleading, not a generic form. The templating story is made explicit so the client can see exactly where the layout came from.

### New template-provenance banner

A navy/gold banner sits above the paper showing:

- `[TEMPLATE]` gold badge with the exact template ID: **KCPAO-CDPC-R4.2 · Certification for Determination of Probable Cause**
- SharePoint path: `/sites/kcpao-filing-standards/Templates/CrR-3.2.1/` (shown in monospace with a SharePoint icon)
- Three right-aligned stats: **347 declarations** drafted YTD from this template · **v.4.2.0** (rev. 2026-02-14 by LegalTech) · **1.8 s** Copilot draft time
- Gold under-stripe separating the banner from the paper below

This makes it unambiguous that Copilot pulled a client-owned template, populated fields from the KCSO intake, and produced the output — not that it invented the format.

### New pleading-paper layout

- **Purview classification banner** across the top of the paper in cream/gold: `🛡 ATTORNEY WORK PRODUCT · CONFIDENTIAL · CrR 4.7 MATERIAL` with an `auto-labeled by Microsoft Purview` tag.
- **Classic WA pleading-paper frame** — double-line pinstripe down the left margin, single line on the right, line numbers 1 → 28 running down the left gutter in Times New Roman (matches Washington State superior court pleading-paper convention).
- **Large faint seal watermark** (~360px) floating behind the body text showing simplified scales of justice.

### Redesigned KCPAO seal (72×72px in the letterhead)

- Tan/cream radial-gradient background with navy outer rings and a gold inner ring.
- Scales of justice rendered in navy with gold pans.
- Circumscribing text along curved paths: `★ KING COUNTY ★` on top arc, `PROSECUTING ATTORNEY` on bottom arc, `EST. 1854` at the base.
- Drop shadow for depth.

### New letterhead block

- Three-column grid: seal · office info · case number strip.
- Big Georgia serif office name: `KING COUNTY / PROSECUTING ATTORNEY` with wide letter-spacing.
- Prosecuting Attorney's name prominently: `LEESA MANION / PROSECUTING ATTORNEY`.
- Division + address + phone line: `CRIMINAL DIVISION · W400 King County Courthouse · 516 Third Avenue, Seattle, WA 98104 · (206) 477-1200`.
- Right-side KC# strip with case number in navy monospace + `Criminal Division` tag.
- Double-gold-rule under the letterhead (navy double-line actually, separating letterhead from caption).

### Real WA superior court caption

- Centered two-line court title: `IN THE SUPERIOR COURT OF THE STATE OF WASHINGTON / IN AND FOR THE COUNTY OF KING`.
- Three-column caption frame with parallel double borders top and bottom (classic WA pleading style).
- Left column: plaintiff/defendant block with `THE STATE OF WASHINGTON · Plaintiff · v. · LI-WEI CHANG (DOB 03/14/1997) · Defendant`.
- Middle: vertical parallel lines between columns (the `│` WA court convention).
- Right column: case number, centered title `CERTIFICATION FOR DETERMINATION OF PROBABLE CAUSE`, `[CrR 2.2(a) · CrR 3.2.1]` citation, charge row, and a simulated red-ink **clerk stamp** (FILED · Apr 21 · 2026 · King County Clerk) slightly rotated like a real rubber stamp.

### New signature block

- Two-column grid: typed DPA info on the left, e-signature box on the right.
- Left: signature line, `SARAH CHEN, WSBA #42118`, `Senior Deputy Prosecuting Attorney`, `Criminal Division · Felony Unit`, contact info.
- Right: cursive e-signature rendered as an inline SVG scribble in navy, with an `e-signed · 2026-04-21 08:04 PST · verified` stamp beneath.

### New court filing footer

- Three-column footer strip: left = `CERTIFICATION FOR DETERMINATION OF PROBABLE CAUSE` + template-ID note, middle = `Page 1 of 2`, right = office address.
- Separated from body by a thin rule.

### Filed-state stamp

When the DPA approves & files, a bigger red-ink-stamp-style **FILED · 04/21/2026** badge angles onto the upper-right of the paper with inset rings (real rubber-stamp look), and the caption clerk stamp flips from red to green.

## 2026-04-22 (evening) — Sheriff Report Intake + Discovery Redaction made interactive

Both headline use cases now run as staged, live-animated flows instead of showing pre-completed output. The user drives each step with the primary CTA; nothing is pre-done on page load.

### Sheriff Report Intake (UC3) — `Report Intake` tile

- **Stage bar across the top** with four numbered steps (report received → extract → draft → sign & file), active step pulses navy, done steps flip green.
- **Stage 1 · Ready to extract** — the handwritten KCSO form is visible; the extraction sidebar shows empty skeleton rows ("— / —"); the big navy CTA says "▶ Run Copilot extraction."
- **Stage 2 · Extracting** — clicking the CTA triggers a blue/purple scan line that sweeps top-to-bottom of the handwritten paper over 3.4 seconds. As the line passes each handwritten field, that field flashes blue and then gets a permanent amber highlighter mark. Each extraction row on the right populates one at a time with a left-slide entry, and the confidence percentage counts up live (0% → 99%). A `0 / 9` counter in the panel header ticks up as each field lands.
- **Stage 3 · Ready to draft** — when extraction completes, the ingest chip flips green ("9 fields extracted · JIS cross-check complete"), the JIS footnote fills in, and the CTA turns purple and flips to "Draft Declaration of Probable Cause."
- **Stage 4 · Drafting** — clicking CTA reveals the PAO letterhead declaration card (slides up from 0-height); paragraphs fade in one by one (~360ms stagger); each `<span class="kc-decl-field">` flashes gold as the extracted value "populates" it.
- **Stage 5 · Ready to sign** — all paragraphs landed; CTA turns green: "Approve & file to Superior Court." The Approve button inside the declaration card is enabled.
- **Stage 6 · Filed** — green "FILED" stamp angles onto the declaration; watermark text flips to the case number; file-receipt toast fires with arraignment calendar info.
- **Replay** — the "↻ Regenerate" button resets state to Stage 1 so the full animation replays. Re-entering the Report Intake app from Home also resets.

### Discovery Redaction (UC4) — `Word` tile

- **Stage-aware toolbar** with a phase pill (Unscanned / Scanning / Redacted · Review / Ready to release / Released) and a single primary CTA that drives the flow.
- **Stage 1 · Unscanned** — the witness statement is shown with **PII visible** under subtle amber highlight + dashed underline (so the DPA can see what's about to be redacted). "Show originals" is disabled because nothing is redacted yet. CTA: "▶ Run PII scan."
- **Stage 2 · Scanning** — a full-page blue/purple scan line sweeps top-to-bottom over 4.2 seconds. As each PII span is reached, it flashes a blue targeting reticle, then wipes left-to-right into a solid black redaction bar via CSS `clip-path` animation. The `0` counter ticks up live ("Copilot found 3 / 10 PII items…").
- **Stage 3 · Redacted · Review** — the findings panel slides down under the toolbar showing two columns: six auto-redacted item types (with green chips + confidence %) on the left, and two **flagged items** on the right — a confidential-informant identifier and a juvenile reference — each with a rationale paragraph, an "Acknowledge" button, and a "Show in document" button that scrolls + spotlight-flashes the flagged span in the page. In the document, the two flagged items pulse a slow orange glow until acknowledged. CTA is gold: "⚠ Review 2 flagged items."
- **Stage 4 · Reviewed** — when both flagged items are acknowledged, the CTA flips green ("✓ Approve & release to defense"), the orange tab on each span turns green for visual trail.
- **Stage 5 · Released** — release triggers a green "RELEASED TO DEFENSE" angled stamp on the page with an audit receipt number; toast fires citing Voorhees (OPD), Purview audit entry, and deadline met. Time-saved chip bumps +32 min.
- **Show originals** — available after scan, toggles all redactions back to a yellow highlight so the DPA can spot-check; release still uses the redacted copy.
- **Reset** — full replay button; also resets when re-entering the Word app from Home.

### Implementation notes

- Both flows are pure CSS + vanilla JS — no external libraries, no dependencies.
- State is driven by `data-stage` / `data-redact-stage` attributes on the root element; CSS selectors handle per-stage visuals.
- Scan-line animations use CSS keyframes with `cubic-bezier(0.45, 0.05, 0.55, 0.95)` for a natural sweep.
- Redaction wipe uses `clip-path: inset(0 100% 0 0)` → `inset(0 0 0 0)` so the black bar appears to "paint" across each span.
- Both canvases can be replayed from the reset button or by leaving and re-entering the app.
- JS parses clean (`new Function(code)` check over the 260K-char script block).

## 2026-04-22 — Initial KCPAO demo

Transformed the prior Meridian State University HR demo framework into the **King County Prosecuting Attorney's Office** (KCPAO) Microsoft 365 + Copilot demo.

### Rebrand

- Swapped the Meridian State palette (navy / teal / gold) for a KCPAO palette: justice navy (#0a2e4f), King County blue (#0068b3), justice gold (#b08d57). Brand-mark updated from "M" monogram to "KC" with a gold underline on sign-in and the topbar.
- Title, sign-in screens, letterhead, seal, and footer all re-branded to "King County Prosecuting Attorney's Office" with a custom seal SVG and Leesa Manion's name on the Office masthead.
- Vocabulary migrated office-wide: HRBP → Senior DPA, HR Director → Chief Deputy Prosecuting Attorney, Benefits Analyst → Paralegal, Workday → Odyssey (JIS), FERPA → CrR 4.7 (Discovery), SHRM → WSBA, FMLA → victim-leave references, etc. 1,500+ discrete substitutions across 7 targeted passes.

### Six use cases rewritten

- **UC1 Charging Review Copilot** — Sheriff referral triage against RCW + office filing standards.
- **UC2 Victim Notification Agent** — Marsy's Law-compliant drafting, tone-calibrated, English + Spanish.
- **UC3 Sheriff Report Intake** — handwritten/scanned KCSO reports → templated probable-cause declarations.
- **UC4 Discovery Redaction Copilot** — auto-redacts PII before defense release; DPA approval gated.
- **UC5 Juvenile Case Protection** — RCW 13.50 sealing enforcement across the tenant.
- **UC6 Public Records Act Desk** — PRA orchestration with 5-day clock, Foundry-evaluated.

All four personas (Sarah, Marcus, Maria, Dan) now see the same canonical six-agent fleet, with role-specific pill text per persona.

### New canvases — the two headline features

- **Sheriff Report Intake (UC3)** — built a full handwritten-to-templated document flow:
  - Scanned field-incident form rendered as an off-white lined-paper mock with cursive handwriting, KCSO letterhead, and officer + sergeant signatures.
  - Copilot OCR extraction panel shows 9 extracted fields with per-field confidence scores and a JIS cross-check on priors.
  - Auto-drafted Certification for Determination of Probable Cause renders below on KCPAO letterhead (seal, Leesa Manion masthead, Superior Court caption, justified body, DRAFT watermark).
  - **Approve & file to Odyssey** button transitions the UI to a filed state and fires a toast with the Superior Court calendar event.

- **Discovery Redaction (UC4)** — rebuilt the Word canvas as a redaction-review view:
  - Page 42 of State v. Reyes, a witness statement, with 7 PII items inline-redacted with solid black bars.
  - Two items (CI identifier, juvenile reference) are flagged warn-orange and must be acknowledged before release.
  - Redaction toolbar adds **Show originals / Hide originals**, **Re-run scan**, **Approve & release to defense** buttons, plus a live counter of "34 detected · 32 auto-redacted · 2 need sign-off".
  - First approve click on unacknowledged flagged items fails closed with a DPA-attention warn toast; second click releases and writes a Purview audit entry.

### Inbox, files, and secondary flows

- Top-of-inbox emails (15+) rewritten for the PAO context: KCSO referral intake, handwritten incident reports, discovery-redaction sign-off requests, victim notifications, PRA requests, filing receipts, Judge's chambers calendar conflicts.
- Filler subject + sender arrays re-themed (WSBA CLE, Bar Leaders Cup, Criminal Law journal club, PRA Desk, Appellate Research).
- OneDrive file list, Teams channels, Copilot responses (charging memo, evening handoff, Q2 Council briefing), and meeting details retargeted from HR/tenure/mortgage content to charging/discovery/public-records content.

### Verified

- All JavaScript blocks parse cleanly (`new Function(code)` check over the single 260K-char script block).
- No residual "Meridian", "MSU", "HR ", "Patel", "tenure", "faculty", "professor", "mortgage", or "Workday" references anywhere in the file.
