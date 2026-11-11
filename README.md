# Expert Knowledge Sharing

**Version 0.1.0 | Experimental prototype**

A lightweight, reusable method for using conversational LLMs to help experienced colleagues share useful experience-dependent knowledge with others.

The initial implementation targets Microsoft 365 Copilot, particularly **Agent Builder (Option B)**, while deliberately retaining compatibility with **Copilot Notebook/Workspace custom instructions (Option A)**. Copilot Studio (Option C) is documented as a possible later deployment route, not a v0.1 dependency.

## Core proposition

Do not ask an expert to “document everything you know”. Instead:

> **one short session → one useful slice of experience → one attributed, reviewable knowledge note**

A normal session aims for about **8 minutes plus review**. The interviewer asks one short question at a time, prefers concrete incidents over abstract explanations, follows promising threads, and does not pretend to recreate or replace the expert.

## What knowledge are we looking for?

Experience-dependent knowledge another capable colleague may not readily derive from existing documentation, including:

- judgement and reasoning;
- warning signs and cues;
- exceptions, edge cases and workarounds;
- mistakes and lessons learned;
- historical rationale and failed approaches;
- dependencies that matter in practice;
- disciplinary terminology, assumptions and norms that can obstruct shared understanding.

This is broader, and more operationally useful, than claiming that all such material is strictly “tacit knowledge”.

## Three ways to start

The interviewer chooses naturally from context rather than asking the participant to select a mode.

1. **Colleague-question-led:** start from a real question someone would normally ask the experienced colleague.
2. **Interdisciplinary:** when multiple disciplines are involved, surface material differences in terminology, assumptions or ways of thinking.
3. **Open elicitation:** otherwise identify one useful thing experience has taught the participant that someone less experienced could benefit from.

## Deployment options considered

### Option A — Copilot Notebook/Workspace

Use `adapters/microsoft-365-copilot/RUNTIME-INSTRUCTIONS.md` as the notebook/workspace custom instructions. Start with a conversation starter from `CONVERSATION-STARTERS.md`.

This remains a supported v0.1 route and is particularly useful for individual testing and experimentation with optional reference material.

### Option B — Microsoft 365 Copilot Agent Builder **(recommended v0.1 route)**

Create one purpose-specific Copilot agent and use the same self-contained `RUNTIME-INSTRUCTIONS.md` as its instructions. Configure the name, description and starters using `AGENT-CONFIGURATION.md`.

The agent is a deployment of this project, not the canonical source. The repository remains the portable source of truth so other organisations can recreate or adapt it.

### Option C — Copilot Studio **(not required for v0.1)**

Potentially useful later if testing demonstrates a real need for formal workflows, deterministic controls, automatic publication, integrations, multiple channels, analytics or separate agents. v0.1 deliberately does not depend on Copilot Studio or its licensing.

See `docs/DEPLOYMENT-OPTIONS.md`.

## Important architectural choice

The repository is modular for humans, but **runtime does not depend on the LLM discovering or traversing this folder hierarchy**.

`RUNTIME-INSTRUCTIONS.md` is the single, self-contained operational specification for Options A and B. Supporting files contain rationale, tests and maintenance guidance. The interviewer should never need to “read all repository files first” before talking to a participant.

## Repository structure

```text
expert-knowledge-sharing/
├── README.md
├── CHANGELOG.md
├── LICENSE
├── RELEASE-MANIFEST.yaml
├── adapters/
│   └── microsoft-365-copilot/
│       ├── RUNTIME-INSTRUCTIONS.md
│       ├── AGENT-CONFIGURATION.md
│       └── CONVERSATION-STARTERS.md
├── specification/
│   ├── DESIGN-PRINCIPLES.md
│   ├── SAFEGUARDS.md
│   └── KNOWLEDGE-NOTE-TEMPLATE.md
├── evaluation/
│   └── ACCEPTANCE-TESTS.md
├── examples/
│   └── EXAMPLE-SESSION.md
└── docs/
    └── DEPLOYMENT-OPTIONS.md
```

## Quick start: Option B

1. In Microsoft 365 Copilot, create a new agent with Agent Builder if available in your tenant.
2. Copy the complete contents of `RUNTIME-INSTRUCTIONS.md` into the agent instructions.
3. Use `AGENT-CONFIGURATION.md` for the proposed name and description.
4. Add the starters in `CONVERSATION-STARTERS.md` where the product permits.
5. Test the cases in `evaluation/ACCEPTANCE-TESTS.md` before sharing the agent.
6. Keep the prototype opt-in and treat generated notes as drafts until the participant reviews them.

## Quick start: Option A

1. Create or open a Copilot Notebook/Workspace.
2. Copy the complete contents of `RUNTIME-INSTRUCTIONS.md` into its custom instructions.
3. Start a chat using the first starter in `CONVERSATION-STARTERS.md`.
4. Supporting files may be added as references for experimentation, but runtime behaviour must not depend on them.

## What v0.1 is not

It does not attempt to:

- capture everything a person knows;
- evaluate someone's expertise or performance;
- create a digital replica or persona of an expert;
- turn recollections automatically into organisational facts;
- replace succession planning, documentation or interpersonal knowledge transfer;
- automatically mine email, chat, tickets or repositories;
- automatically publish notes into an organisational knowledge base.

## Prototype evaluation

Test the interaction with a small number of willing participants before adding complexity.

Ask the participant:

1. Was this easy to do?
2. Did a question surface something useful you might not otherwise have documented?
3. Is the resulting note accurate?
4. Was anything irritating, repetitive or uncomfortable?
5. Would you willingly do another short session?

Then ask an appropriate less-experienced recipient:

1. Did you learn something you did not already know?
2. Could this change what you would do?
3. What would you ask the contributor next?

The recipient's next question is a valuable candidate for another session.

## Project status

v0.1.0 closes the first design iteration. The priority now is evidence from real trials rather than adding prompt complexity.


