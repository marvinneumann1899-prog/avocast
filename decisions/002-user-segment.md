# 002 — User segment: Wholesaler

**Date:** 2026-04-28
**Status:** Accepted

## Context

The brief lists "farmers, retailers" as example users (e.g.). The background paragraph mentions growers, wholesalers, and supermarkets. We had to pick one to anchor the Canvas problem framing.

## Decision

Primary user segment = **Wholesaler** (B2B intermediary between growers and retailers).

## Rationale

- Wholesaler sits on **both sides** of the supply chain: buys from farmers, sells to retailers. A price forecast informs *both* sides of their decisions.
- Wholesaler holds **physical inventory** of a perishable product → spoilage risk creates real urgency around timing decisions.
- Weekly decision cadence matches the dataset's weekly granularity.

## Caveat to flag in the report

The dataset's `AveragePrice` column is the consumer-side **retail price**, not the wholesaler's own buy/sell price. We treat retail price as a leading indicator for what retailers will be willing to pay wholesalers in the coming weeks. This is a reasonable proxy but should be acknowledged as a limitation in the methodology section.
