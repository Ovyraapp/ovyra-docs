# ARCHITECTURE

## System Overview

Ovyra should evolve as a three-layer system:

1. client applications for web and future mobile
2. API and intelligence services for recommendations, personalization, and ingestion
3. documentation and operating systems that keep the team and AI agents aligned

## Repository Roles

- `ovyra-web`: user-facing application, UI system, auth flows, maps, onboarding, discovery surfaces
- `ovyra-api`: recommendation engine, AI enrichment, ingestion pipelines, profile logic, partner-facing integrations
- `ovyra-docs`: product strategy, prompts, operating playbooks, roadmap, brand system

## Backend Boundaries

- route modules should remain thin
- business logic belongs in services and domain modules
- external providers should sit behind adapters
- ingestion should be designed to move into workers or queues without changing public APIs

## Data Strategy

- use Supabase or Postgres-backed persistence for MVP speed
- keep normalized entities for places, events, tags, and user profiles
- preserve raw ingest metadata when useful for debugging and future reprocessing
- design recommendation outputs as contracts reusable by web and mobile

## AI System Principles

- AI should enrich and rank, not blindly author core truth
- prompts must be versioned and documented
- every AI-generated field should have a clear downstream use
- human-readable summaries should coexist with structured machine-usable attributes

## Collaboration and CI/CD

- each repo should support fast local onboarding
- environment variables must be documented with no committed secrets
- CI should at minimum typecheck and build
- documentation should be explicit enough for autonomous AI agents to execute scoped work safely
