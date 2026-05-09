# PROMPTS

## Role of Prompts in Ovyra

Prompts are a product surface, not only an implementation detail. They shape recommendation quality, entity understanding, tone, and trust. Ovyra should maintain prompts as versioned operating assets.

## Prompt Categories

- entity tagging prompts for places and events
- summarization prompts for concise user-facing descriptions
- recommendation reasoning prompts for ranking or reranking contexts
- onboarding prompts for taste capture and preference clarification
- internal research prompts for ops or editorial workflows

## Prompt Design Rules

- request structured outputs whenever downstream systems consume the result
- keep instructions deterministic where possible
- separate system behavior from dynamic user or data context
- avoid prompts that invent operational facts when source data is weak

## Example Prompt Objectives

- infer tags such as vibe, category, time-of-day fit, price signal, and audience type
- summarize venues in one premium, neutral sentence
- classify user taste from onboarding answers into reusable profile facets
- explain why a recommendation is relevant without exposing chain-of-thought style internals

## Governance

- store prompts with identifiers and revision history
- track which prompts affect user-facing experiences
- log sample inputs and outputs for QA
- review prompt changes alongside feature changes when ranking behavior can shift
