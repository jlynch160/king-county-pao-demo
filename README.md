# KCPAO · Microsoft 365 + Copilot Demo (King County Prosecuting Attorney's Office)

A self-contained, single-file interactive demo showing how **Microsoft 365 Copilot**, **Copilot Studio**, **Power Platform**, and **Microsoft Foundry** map onto six prosecuting-office use cases for the King County Prosecuting Attorney's Office.

> All personas, case numbers, defendants, and operational data are fictional. No real case, victim, witness, or defendant is depicted. The demo is intended for sales conversations and architecture discussions only.

## The four-layer Microsoft AI stack (KCPAO framing)

| Layer | Product | Role |
|---|---|---|
| 1 | Microsoft 365 Copilot | Productivity layer for DPAs + paralegals — Outlook, Teams, Word, Excel, PowerPoint, OneDrive |
| 2 | Copilot Studio | Conversational agent layer — six custom KCPAO agents |
| 3 | Power Platform | Workflow, app, and case-management layer — Power Apps, Automate, Pages, Dataverse |
| 4 | Microsoft Foundry | Advanced AI orchestration, evaluation, and governance — the spine for Discovery Redaction (UC4) and PRA Desk (UC6) |

## Six use cases covered

1. **Charging Review Copilot (UC1)** — reviews Sheriff referrals against RCW + office filing standards, triages the overnight queue, and pre-drafts declarations for the clearest cases.
2. **Victim Notification Agent (UC2)** — drafts Marsy's Law-compliant victim communications (hearing, plea, release) in sensitive, plain language; English + Spanish; tone-calibrated for homicide, DV, SA matters.
3. **Sheriff Report Intake (UC3)** — takes **handwritten** or scanned KCSO incident reports, extracts the facts with OCR, cross-checks JIS, and drafts a Declaration of Probable Cause on Office letterhead ready for a DPA to review and sign.
4. **Discovery Redaction Copilot (UC4)** — auto-redacts PII (SSN, DOB, addresses, phone numbers, plates, CI identifiers, sealed-juvenile records) in discovery packets before defense-counsel release. Human DPA approval required; ambiguous items are flagged in the warn color and must be acknowledged.
5. **Juvenile Case Protection (UC5)** — enforces RCW 13.50 juvenile sealing across email, Teams, Word, and OneDrive. Any artifact naming a sealed matter is auto-blocked before send.
6. **Public Records Act Desk (UC6)** — orchestrates PRA requests, tracks the 5-day clock, pulls responsive records from OneDrive + SharePoint, pre-stages a redaction review, and reports SLA + risk metrics to the Chief Deputy.

## Highlighted demo canvases

Both of the canvases below are live-interactive — click through the Home app grid:

- **"Report Intake" tile** → Sheriff Report Intake canvas: a scanned, handwritten KCSO field-incident form appears on the left; Copilot's OCR extraction + JIS cross-check runs on the right; the auto-drafted Certification for Determination of Probable Cause populates below on KCPAO letterhead with Leesa Manion's name on the masthead. Click **Approve & file to Odyssey** to see the filing receipt + Superior Court calendar event.
- **"Word" tile** → Discovery Redaction workflow: a 312-page State v. Reyes discovery packet, focused on page 42 — a witness statement. PII is shown with black-bar redactions; two items (CI reference + juvenile record) are outlined in warn-orange and must be acknowledged before release. Toggle **Show originals** for DPA review; **Approve & release to defense** writes the redaction audit to Purview.

## Four personas

- **Sarah Chen, Senior DPA** — Criminal Division lead, sees charging review + sheriff intake + redaction + victim notification.
- **Marcus Johnson, Chief Deputy Prosecuting Attorney** — triage view: priority cases, media-sensitive matters, PRA SLA dashboard, Council briefing.
- **Maria Gutierrez, Paralegal** — intake-heavy view: sheriff reports queued, discovery redaction prep, juvenile-case protection, PRA record assembly.
- **Dan Kowalski, IT Director** — governance view: DLP events, notification SLA monitoring, juvenile-record exposure blocks, PRA executive readout.

## Running locally

Just open `index.html` in a modern browser. No build step, no external dependencies.

## Deployed

When deployed to Azure Static Web Apps via GitHub Actions, the same folder can be pushed as-is.
