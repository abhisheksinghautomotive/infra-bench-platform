# ADR-000: ADR Template and ADR Folder

Date: YYYY-MM-DD  
Status: Proposed / Accepted / Superseded / Rejected  
Authors: <Your Name> (<github-username>)

## Context
We need a consistent, repo-local place to store Architecture Decision Records (ADRs) to document important decisions, alternatives, and rationale. This improves onboarding, review, and traceability across the portfolio.

## Decision
Create an `ADRs/` folder at repository root and add this ADR-000 as the canonical template for all future ADRs. All ADR files must:

- Use the filename pattern `ADRs/ADR-<NNN>-<short-title>.md` (zero-padded numeric index).
- Include the fields: Date, Status, Authors, Context, Decision, Consequences, Alternatives considered, Related ADRs.
- Be written in Markdown and committed to the repo.
- Be referenced from the top-level `README.md` under a “Design decisions / ADRs” section.

## Consequences
- Pros:
  - Uniform documentation across repos.
  - Easy review and traceability of decisions.
  - Enables PR review of architecture changes.
- Cons:
  - Slight overhead to write and maintain ADRs.
  - Requires discipline to keep ADRs up-to-date.

## Alternatives considered
- Centralized ADRs in `devops-portfolio-admin` only — rejected because repo-specific decisions are easier to discover in-repo.
- Use external wiki — rejected to keep decisions versioned with code.

## Implementation
1. Create `ADRs/` folder at repository root.
2. Add `ADRs/ADR-000.md` (this file) as the template.
3. Update `README.md` with a link to the ADRs folder and short guidance.
4. Use PR workflow for ADR additions/changes (one ADR per PR).

## Related ADRs
- (blank for future entries)
