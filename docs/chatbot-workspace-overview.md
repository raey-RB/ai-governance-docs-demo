# Workspace Chatbot — Technical Overview

**Owner:** AI/Data Science Lead  
**Last updated:** 2026-07-20  
**Status:** Active

## Purpose
The workspace chatbot answers internal user questions by retrieving relevant information from connected data sources and generating natural-language responses.

## Architecture Summary
- **Interface:** Internal workspace chat UI
- **Core model:** LLM-based response generation
- **Retrieval layer:** Queries internal database via API (see CR-0001, ADR-0001) for current data
- **Data sources:** Internal live database (primary), legacy static reference set (fallback)

## Data Access
The chatbot's service account has read access to designated internal database tables relevant to user queries. Access scope is intentionally limited to non-sensitive, business-relevant fields; sensitivity review of accessible fields is an active follow-up item (see CR-0001).

## Change History
| Date | Change | Reference |
|------|--------|-----------|
| 2026-07-18 | Expanded retrieval source to live internal database | CR-0001 / ADR-0001 |

## Known Limitations
- No formal automated data sensitivity classification yet applied to newly accessible fields.
- No CAB review was performed for this change (retroactively identified process gap).

## Related Documents
- [CR-0001](../change-requests/CR-0001-database-api-access.md)
- [ADR-0001](../adr/0001-expand-chatbot-database-access.md)
