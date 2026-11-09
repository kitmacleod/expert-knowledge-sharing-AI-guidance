# Microsoft 365 Copilot Agent Configuration

Version: 0.1.0

This file describes the recommended Option B configuration. Product labels may vary by tenant and Microsoft rollout.

## Proposed name

**Experience to Share**

Alternative if a more explicit organisational name is preferred: **Knowledge Sharing Interviewer**.

## Proposed description

A short, supportive interviewer that helps experienced colleagues turn one useful piece of experience into an attributed knowledge note for others to review and use.

## Instructions

Copy the **complete contents** of `RUNTIME-INSTRUCTIONS.md` into the agent's instruction field. Do not replace them with links to the repository and do not make runtime behaviour depend on the agent reading the rest of the repository.

## Conversation starters

Use the starters in `CONVERSATION-STARTERS.md` where the Agent Builder user interface supports them.

## Knowledge sources

**v0.1 default: none required.**

The objective is to test conversational elicitation before introducing repository, SharePoint, Teams or other retrieval dependencies.

Optional source material may be introduced in controlled experiments, for example a system overview or architecture document. When doing so, the agent must still distinguish the participant's account from source material and surface material disagreements rather than silently harmonising them.

## Actions

**v0.1 default: no automated actions.**

Do not automatically publish, email, file or distribute a knowledge note. Participant review comes first.

## Sharing

For early testing, share only with willing prototype participants. Do not imply that the agent itself is portable across organisations; the public repository is the portable implementation kit.

## Voice

The runtime instructions are voice-friendly, but v0.1 does not depend on a dedicated voice-agent channel. Ordinary product dictation/voice capabilities can be tested where available.

## Before sharing

Run the scenarios in `evaluation/ACCEPTANCE-TESTS.md`. In particular confirm that the agent:

- asks one question at a time;
- does not present an interview plan before starting;
- does not claim to capture all expertise;
- does not invent facts or contacts;
- handles secrets and personal criticism safely;
- surfaces interdisciplinary differences only when relevant;
- produces a concise draft note;
- asks for participant review;
- does not impersonate the contributor.
