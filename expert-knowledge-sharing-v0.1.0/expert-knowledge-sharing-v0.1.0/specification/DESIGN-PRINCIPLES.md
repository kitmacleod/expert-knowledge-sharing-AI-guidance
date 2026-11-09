# Design Principles

Version: 0.1.0

## Slice, not harvest

Capture one useful piece of experience at a time. Never promise comprehensive knowledge extraction.

## Conversation, not form filling

The model follows useful threads instead of completing a questionnaire.

## Episodes before abstractions

Concrete incidents often expose expert judgement more effectively than asking people to list general rules.

## One question at a time

Minimise cognitive load and support spoken as well as typed interaction.

## Pull as well as push

Questions from less-experienced colleagues are strong starting points because they represent demonstrated knowledge needs.

## Spend expert time where it adds value

Documentation can often provide the “what”. Expert conversation is especially valuable for the “why”, “except”, “watch out for”, “we tried” and “in practice”.

## Preserve provenance

An attributed recollection is not the same as an independently verified fact.

## Do not manufacture coherence

Experts can be unsure, disagree, remember things differently or change their views. Preserve meaningful uncertainty rather than silently resolving it.

## Bridge disciplines when relevant

Different disciplines may attach different meanings, assumptions and norms to apparently shared concepts. Surface differences when they matter, without turning every session into an interdisciplinary exercise.

## Human usefulness is the criterion

Optimise for knowledge that helps another person understand, decide or act, not for quantity of generated text.

## Expert augmentation, not replacement

The system helps people articulate and transmit experience. It does not recreate, impersonate or replace them.

## Runtime must be self-contained

Repository structure is for maintainers. The deployed interviewer must not depend on discovering a folder hierarchy or reading supporting artefacts before it can behave safely and usefully.

## Validate at release time

Check completeness, precedence and expected behaviour before deployment through a manifest and acceptance tests, rather than making every participant session begin with a repository inspection.

## Keep v0.1 technically boring

Use the smallest platform capability that can test the human interaction. Add retrieval, actions, workflows, multi-agent orchestration and automatic publication only when real trials demonstrate a requirement.
