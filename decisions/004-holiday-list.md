# 004 — Holiday list extended beyond brief's example

**Date:** 2026-04-28
**Status:** Accepted

## Context

The brief instructs: *"Add a holiday (e.g., Thanksgiving)."* The example holiday list explicitly mentions *"U.S. Thanksgiving (4th Thursday of November)"*.

## Decision

Use **four holidays** in the Prophet model:
1. Super Bowl Sunday (early February)
2. Cinco de Mayo (5 May)
3. Fourth of July (4 July)
4. Thanksgiving (4th Thursday of November)

## Rationale

The brief's Thanksgiving suggestion is methodologically thin for avocados. The actual US avocado-demand peaks are:
- **Super Bowl** — guacamole consumption surge.
- **Cinco de Mayo** — historically the largest single-day avocado-demand event in the US.
- **Fourth of July** — BBQ season.
- Thanksgiving is *not* a major avocado holiday (turkey-dominated).

Including all four gives the Prophet model real demand signals to learn from. Thanksgiving is retained to honour the brief's hint, even though we expect its effect coefficient to be small. Justified in the report under evaluation criteria *Transfer* (rationalising deviations from the brief) and *Creativity*.
