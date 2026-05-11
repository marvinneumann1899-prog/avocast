# Decision 005 — Canvas redesign as Excalidraw sketch

**Date:** 2026-05-04
**Status:** Accepted

## Context

The original deliverable for the canvas-model task was an HTML Lean Canvas (`assets/canvas.html`, `docs/01-canvas.md`) — a polished 9-block grid covering Problem, Solution, UVP, Channels, Customer Segments, Cost, Revenue etc.

Two issues with that version:
1. The brief asks specifically for *"key problem, users, and forecasting value proposition"* — three things. The full Lean Canvas adds Channels, Pricing, Cost Structure, Revenue Streams etc. that the brief does not require, padding the deliverable with business-model framing that is not asked for.
2. The HTML version reads as corporate / generic. The student voice does not come through.

## Decision

The canvas was redesigned in Excalidraw (`assets/canvas-sketch.excalidraw`, `assets/canvas-sketch.png`) as the **main canvas artefact for the deliverable**. The HTML Lean Canvas is kept in the appendix as a reference / earlier iteration, but the Excalidraw sketch is what the report points to.

The new canvas focuses tightly on the three brief requirements:
- **Key problem** — banner across the top: *"U.S. avocado prices swing 20–30% week-to-week with no forward visibility. Every actor in the supply chain plans on gut feel and last year's chart."*
- **Users along the supply chain** — Farmer → Wholesaler → Retailer → Consumer, each with three sections: ROLE, KEY PROBLEM, GUT FEEL (their current workaround). Wholesaler, Retailer, and Farmer are marked as ★ AvoCast users; Consumer is the end of the chain.
- **Forecasting value proposition** — AvoCast box at the bottom with a divider that splits the value statement from three user-specific bullets (harvest planning, contract pricing, stock & promo timing). Three green arrows connect AvoCast to the three primary users through the gaps between the info columns.

## Why the Excalidraw sketch wins

- Hand-drawn aesthetic matches the dashboard sketch — both deliverables now share a visual language.
- Reads as one connected canvas instead of nine separate boxes.
- Tight on the three brief requirements rather than padded with business-model fluff.
- Marvin's voice comes through (e.g., the *GUT FEEL* framing, the supply-chain transaction labels).

## Why we kept the HTML version

It's a useful reference for the broader business model (pricing, channels, etc.) that may be relevant later in a real product context but is not part of this deliverable. Lives in `docs/01-canvas.md` and `assets/canvas.html`.
