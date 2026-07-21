# Change Request Template

**CR ID:** CR-0001  
**Title:** Expand workspace chatbot API access to internal live database  
**Requested by:** AI/Data Science Lead  
**Date submitted:** 2026-07-20  
**Status:** Implemented — Follow-up in Progress

## 1. Description
The workspace chatbot's retrieval source was expanded to pull from a more current, near-live internal database, replacing a more static/delayed data source. Goal: improve response accuracy and user trust in the bot's answers.

## 2. Type of Change
- [ ] Model / version change
- [x] Prompt change
- [x] Data source / retrieval change
- [x] API / tool / MCP integration change
- [ ] Agent permission change
- [ ] Documentation only
- [ ] Other

## 3. Impact Assessment
- **Affects model behavior/output?** Yes — responses now reflect live/current data instead of stale data.
- **Affects data access or sensitivity?** Yes — bot now has access to a broader internal dataset; sensitivity of newly accessible fields was not formally reviewed at the time.
- **Affects security/permissions?** Yes — new API access granted to the bot's service account.
- **Affects compliance/privacy/Responsible AI principles?** Potentially — no formal data governance review was completed before rollout.
- **Risk tier:** Medium (retroactively assessed; was treated as Low at the time)

## 4. Approvals Required
- [x] AI Engineering
- [ ] Security *(not completed — identified gap)*
- [x] Product
- [ ] CAB (if High risk)

## 5. Implementation Plan
API integration built and tested by AI Engineering; deployed directly following internal product sign-off.

## 6. Rollback Plan
Revert chatbot configuration to prior static data source; no data was permanently altered.

## 7. Related Documents
- ADR: ADR-0001
- Docs updated: docs/chatbot-workspace-overview.md
- PR link: *(to be linked in Step 5)*

## 8. Audit Log
| Date | Action | By |
|------|--------|-----|
| 2026-07-18 | API access expanded, deployed to production | AI Engineering |
| 2026-07-20 | CR retroactively documented for governance record | AI/DS Lead |
| 2026-07-21 | Security review scheduled to close governance gap | AI/DS Lead |
