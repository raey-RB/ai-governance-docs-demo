# ADR-0001: Expand Workspace Chatbot to Access Live Internal Database

**Status:** Accepted  
**Date:** 2026-07-18  
**Deciders:** AI/Data Science Lead, AI Engineering, Product  
**Related CR:** CR-0001

## Context
The workspace chatbot originally retrieved answers from a static or periodically-refreshed data source. Users increasingly reported that responses felt outdated compared to current internal records, which reduced trust in the bot's answers.

## Decision
We will integrate the chatbot with an internal database API to enable near-live data retrieval, replacing the static data source as the primary source of truth for relevant queries.

## Options Considered

**Option A: Keep static data source, increase refresh frequency**
- Pros: Lower integration effort, no new access surface
- Cons: Still not truly current; doesn't fully solve trust issue

**Option B: Integrate direct API access to live internal database (chosen)**
- Pros: Most current data, highest response accuracy, addresses root cause of trust issue
- Cons: Introduces new data access surface; requires ongoing governance of what the bot can see and surface

**Option C: Hybrid caching layer with scheduled sync**
- Pros: Balances freshness and access control
- Cons: Higher engineering complexity; deferred for future iteration

## Consequences
- Positive: Significantly improved response accuracy and user trust.
- Negative / Risk: New data access surface introduced without a formal data sensitivity review at time of launch. This gap was identified after the fact and is now being addressed through the formal CR/impact assessment process (see CR-0001).
- Follow-up action: Future data source expansions of this kind will route through the AI Change Request process for Security and governance review prior to deployment.

## Supersedes / Superseded by
None (initial decision)
