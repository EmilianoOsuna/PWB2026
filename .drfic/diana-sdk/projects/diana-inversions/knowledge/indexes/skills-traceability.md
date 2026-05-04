# Skills Traceability — diana-inversions

**Version**: 1.0.0  
**Last Updated**: 2026-05-03  
**Scope**: project + reusable layer

---

## ID Mapping

No previous project skill IDs existed in this workspace, so there is no old_id -> new_id migration table to preserve.

---

## Source Traceability

| Skill ID | Source of Truth |
|----------|-----------------|
| 001-speckit-specify-validation | .github/prompts/speckit.specify.prompt.md |
| 002-speckit-clarify-gap-analysis | .github/prompts/speckit.clarify.prompt.md |
| 003-speckit-plan-decomposition | .github/prompts/diana.plan.prompt.md |
| 004-speckit-tasks-atomicity | .specify/templates/tasks-template.md |
| 005-speckit-implement-governance | .specify/templates/plan-template.md |
| 001-inv-constitution-governance | .drfic/diana-sdk/projects/diana-inversions/inv-constitution.md |
| 002-inv-portfolio-management | .drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md |
| 003-inv-signal-confluence | .drfic/diana-sdk/projects/diana-inversions/inv-constitution.md |
| 004-inv-broker-integration | .drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md |
| 005-inv-auditability-documentation | .drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md |
| 006-inv-agent-governance | .drfic/diana-sdk/projects/diana-inversions/inv-constitution.md |
| 007-inv-market-exploration-alerts | .drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md |

---

## Compatibility Notes

- General reusable skills are consumed first by Speckit and then extended by project-specific skills.
- Shared SDK skills remain valid and are used in `generic_sdd` mappings.
- No skill is left without at least one knowledge doc.