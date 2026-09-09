# Docket: Vendor Decision Desk

A functional vendor-onboarding prototype for procurement and accounts-payable reviewers. It turns a flagged submission into an evidence-backed, explainable decision while keeping human responsibility visible.

## What the prototype demonstrates

- An attention queue with composable workflow and SLA filters
- Source-level comparison between vendor claims and bank evidence
- Readable OCR, uncertain OCR, missing-source, and resolved-evidence scenarios
- Approval gated by verified relationship evidence
- Evidence requests and rejection flows with required reasoning
- Truthful previews of status, ownership, communication, and queue changes
- Append-only browser-local audit history and decision revisions
- Responsive layouts, visible focus, keyboard interaction, and reduced-motion support

## Run locally

The two pages must share one origin for their browser-local decision record.

```bash
cd outputs
python3 -m http.server 8000
```

Open `http://localhost:8000/docket-slice.html`.

Start with Northstar Holdings, open its evidence review, choose a prototype scenario, and prepare a resolution. Returning to the queue shows the updated workflow state.

## Main files

- `outputs/docket-slice.html`: attention queue and dashboard metrics
- `outputs/evidence-transcript-slice.html`: evidence inspection, decision register, and audit history
- `outputs/bank-letter-scan.png`: sample source document used by the evidence viewer

## Prototype boundary

All decisions and communications are simulated. State is stored only in the current browser. The prototype does not send vendor messages or update a procurement system.

## Review status

The final independent source audit scored the implementation 96/100 with no open P0 or P1 findings. Runtime certification still requires exercising the same-origin build across desktop and mobile viewports.
