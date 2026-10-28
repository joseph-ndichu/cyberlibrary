# Engineering and pre-build workflow

The library is maintained using a risk-based, iterative lifecycle. A checklist is a planning aid; it is not a claim of ISO, NIST, or regulatory certification.

## Before production changes

1. **State the need and owner:** define the user problem, intended outcomes, scope, exclusions, and accountable owner.
2. **Gather user and stakeholder evidence:** identify readers, maintainers, publishers, and affected parties; document needs and constraints.
3. **Baseline requirements:** give requirements IDs, priorities, owners/sources, measurable acceptance criteria, and links to verification tests.
4. **Assess feasibility and risk:** compare build, buy, reuse, or integration; record data, legal, privacy, security, cost, schedule, and dependency risks.
5. **Review design:** document system boundaries, components, data flows, interfaces, access boundaries, and key architecture decisions. Threat-model significant changes.
6. **Plan verification and validation:** identify how each requirement will be checked and how users will confirm the feature solves the right problem.
7. **Plan delivery and operation:** define small releases, roles, code review, tests, monitoring, backups, rollback, incident handling, maintenance, and retirement.
8. **Approve a change baseline:** the owner and relevant reviewers accept the scope, risks, acceptance tests, and release plan before production implementation.

Throwaway prototypes may be used to test uncertain assumptions, but they are not treated as production-ready code. AI-generated requirements, designs, or code require human review and normal testing before adoption.

## References

- [ISO/IEC/IEEE 12207:2026 — Software life cycle processes](https://www.iso.org/standard/90219.html): lifecycle processes across conception, development, operation, support, and retirement; applicable iteratively and to agile approaches.
- [ISO/IEC/IEEE 29148:2018 — Requirements engineering](https://www.iso.org/standard/72089.html): requirements processes and information items for systems and software.
- [NIST SP 800-218 — Secure Software Development Framework](https://csrc.nist.gov/pubs/sp/800/218/final): secure-development practices to integrate into the chosen lifecycle.

Tailor the depth of evidence to the system's risk and applicable obligations. A real claim of compliance or certification requires the relevant standard, scope, and assessment process.
