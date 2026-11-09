# Deployment Options Considered

Version: 0.1.0

This decision record explains why v0.1 prioritises Microsoft 365 Copilot Agent Builder while keeping the same runtime instructions usable in a Copilot Notebook/Workspace.

## Requirements

The initial deployment should:

- be simple enough for a non-technical participant;
- support short typed or spoken/dictated conversation;
- apply stable behavioural instructions;
- minimise dependence on a hierarchy of reference files;
- remain inspectable and versionable in Git;
- be reproducible by organisations outside the original organisation;
- avoid requiring additional platform expenditure where possible;
- validate the human interaction before adding system integrations.

## Option A — Copilot Notebook/Workspace

### Strengths

- Low-friction place to test custom instructions and optional references.
- Suitable for iterative experimentation by an individual or small team.
- The same self-contained v0.1 runtime instructions can be pasted directly into its custom-instructions area.

### Limitations

- A workspace can encourage dependence on whichever references happen to be present.
- Participants need to be directed to the correct workspace and setup.
- A hierarchy of guidance files does not itself guarantee that an LLM has loaded, prioritised or reconciled them.

### v0.1 decision

**Supported.** Option A is the fallback and development/test route. Supporting references may be added, but the interviewer must not depend on traversing them to know how to behave.

## Option B — Microsoft 365 Copilot Agent Builder

### Strengths

- Provides a named, bounded participant-facing experience.
- Attaches instructions directly to the purpose-specific agent.
- Allows simple conversation starters.
- Better separates the public method from the participant interface.
- Does not require a bespoke software application for the first prototype.

### Limitations

- Availability and sharing depend on Microsoft 365 tenant licensing and administrator policy.
- An agent shared in one tenant is not the portable public artefact.
- More sophisticated actions and lifecycle controls may require a different platform later.

### v0.1 decision

**Recommended primary route.** Deploy one agent, not a series of agents. Keep the repository as the canonical implementation kit so another organisation can independently configure the same behaviour.

## Option C — Copilot Studio

### Strengths

Potentially appropriate for later requirements such as:

- multi-channel publishing;
- workflow/actions and structured storage;
- formal review and approval;
- deterministic safety logic;
- integrations with organisational systems;
- analytics and formal testing/deployment processes;
- genuinely separate agents with different permissions or responsibilities.

### Limitations for v0.1

- Additional implementation and governance complexity.
- Can introduce licensing or administrative dependencies.
- Risks automating a knowledge-management system before the core conversational interaction has demonstrated value.

### v0.1 decision

**Deferred and not required.** Lack of Copilot Studio access should not prevent the prototype.

## Why not multiple agents yet?

The first workflow is coherent:

```text
choose one useful topic
        ↓
short interview
        ↓
draft knowledge note
        ↓
participant review
```

Separate agents become justified only when functions materially differ in permissions, tools, knowledge sources, owners, risks or evaluation criteria. v0.1 has not demonstrated those needs.

## Why the runtime instructions are self-contained

Human-maintained repositories benefit from modular files and folders. Runtime LLM behaviour should not depend on the model discovering the repository structure and correctly inferring instruction precedence.

Therefore:

- `RUNTIME-INSTRUCTIONS.md` contains every behaviour- and safety-critical instruction needed by the interviewer;
- design principles and safeguards explain the rationale;
- acceptance tests verify expected behaviour;
- `RELEASE-MANIFEST.yaml` declares which runtime artefact is authoritative.

This intentionally creates limited repetition across **rationale → implementation → test**. It is preferable to hidden runtime dependencies.

## Future decision gate for Copilot Studio

Reconsider Option C only when trials demonstrate one or more concrete needs such as:

1. automatic storage or publication of reviewed notes;
2. formal approval workflows;
3. materially different permissions between roles;
4. deployment across additional managed channels;
5. formal usage/quality analytics;
6. deterministic controls that prompt instructions alone cannot reliably provide;
7. integrations with systems such as SharePoint or line-of-business repositories;
8. separate elicitation, curation or retrieval agents with genuinely distinct responsibilities.
