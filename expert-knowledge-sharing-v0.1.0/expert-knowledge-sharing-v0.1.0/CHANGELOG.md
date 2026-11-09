# Changelog

All notable changes to this project are documented here.

The project uses semantic versioning. Versions before 1.0 are experimental.

## [0.1.0] - 2026-11-08

### Added

- Initial reusable expert knowledge-sharing method.
- Microsoft 365 Copilot-first deployment design.
- Option B, Microsoft 365 Copilot Agent Builder, selected as the recommended participant-facing prototype.
- Option A, Copilot Notebook/Workspace custom instructions, retained as a fully supported lightweight deployment.
- Option C, Copilot Studio, documented as a possible later route rather than a v0.1 dependency.
- One self-contained runtime instruction artefact for Options A and B.
- Three adaptive starting conditions: colleague question, interdisciplinary context and open elicitation.
- Approximately eight-minute, one-topic session design.
- Voice-friendly one-question-at-a-time interaction.
- Participant review, attribution, provenance and uncertainty handling.
- Security, privacy, sensitivity and anti-impersonation safeguards.
- Initial interdisciplinary-knowledge hook.
- Knowledge-note template.
- Acceptance-test suite and fictional worked example.
- Release manifest to make runtime authority explicit.

### Design decisions

- Adopted **slice, not harvest** as a core principle.
- Defined the target as experience-dependent knowledge another capable person would not readily derive from available documentation.
- Prioritised concrete experiences over abstract descriptions of expertise.
- Treated real colleague questions as a first-class elicitation route.
- Rejected “query the expert's mind” and digital-expert framing.
- Avoided mandatory confidence classification for every statement.
- Kept dedicated interdisciplinary elicitation outside v0.1 while allowing relevant disciplinary differences to surface.
- Kept the repository modular for maintainers but removed runtime dependence on folder traversal or “read everything first” behaviour.
- Chose one agent rather than a multi-agent architecture for the first prototype.
- Deferred Copilot Studio workflows, automatic retrieval and automatic publication until validated requirements emerge.

### Status

Experimental. Intended for small-scale, opt-in testing rather than production knowledge-management deployment.
