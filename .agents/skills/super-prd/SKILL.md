---
name: super-prd
description: Generate technical Product Requirements Documents (PRDs) for software systems. Supports dual-mode: quick synthesis from conversation context, or deep discovery through structured interview. Use when user wants to create a PRD, document requirements, plan a feature, or turn conversation context into a specification.
---

## Mode Selection

Assess the conversation context before starting:

| Mode | Trigger | Behavior |
|------|---------|-----------|
| **Quick** | Context already rich with requirements, user stories, and technical decisions | Explore the repo to understand current codebase state, then synthesize PRD directly from context |
| **Deep** | Requirements are vague, missing key dimensions | Initiate structured discovery interview (1-3 rounds) |

Announce which mode you're using and why.

## Quick Mode

1. Explore the repository to understand the current codebase state, domain glossary, and relevant ADRs.
2. Identify major modules to build or modify. Look for opportunities to extract **deep modules** — modules that encapsulate significant functionality behind a simple, testable interface that rarely changes.
3. Synthesize the PRD from conversation context and codebase understanding.

## Deep Mode: Discovery Interview

Ask across these dimensions, one round at a time. Stop when all dimensions are sufficiently clear (max 3 rounds).

1. **Project Background** — Core problem? Target users? Use scenarios? Current alternatives and pain points?
2. **Feature Scope** — Must-have core features? Nice-to-have auxiliary features? Explicit Non-Goals?
3. **Technical Constraints** — Specified tech stack? Existing system integration? Performance/security/compliance requirements?
4. **Success Metrics** — Quantifiable KPIs or OKRs?

## PRD Template

Generate the PRD using the structure below. For detailed guidance on each section, tech stack recommendations, and examples, refer to `prd-expert-prompts.md`.

1. **Background** — Problem statement, project goals, success metrics (3-5 quantifiable KPIs), glossary
2. **User Stories** — Personas, story list (P0/P1/P2 priority), Gherkin acceptance criteria (include error flows and edge cases), Non-Goals
3. **Module Design** — Module breakdown, dependencies, interfaces, reusable modules. Identify deep modules where applicable.
4. **Process Design** — Business process flows, data flows, core function flows (Mermaid or text description)
5. **Technology Stack** — Frontend/backend/database/deployment choices, each with rationale
6. **Architecture Design** — System architecture diagram, component interaction, deployment architecture
7. **Database Design** — Table structures (fields, types, constraints, relationships), index strategy, migration plan
8. **API Design** — Specification (RESTful/GraphQL), endpoint inventory (method, path, request/response), authentication and authorization
9. **Frontend & UI Design** — UI style, component library conventions, state management, responsive strategy
10. **AI System Requirements** (if applicable) — Tool and API requirements, model selection rationale, evaluation strategy
11. **Project Conventions** — Code style, comment conventions, Git workflow, directory structure
12. **Development Boundaries** — Untouchable files/modules, technical debt, future extension points
13. **References** — Official documentation, best practices, related ADRs

## Quality Standards

- All metrics are concrete and quantifiable — avoid "fast", "intuitive", "modern"
- User stories follow INVEST principles; acceptance criteria use Gherkin syntax with error flows and edge cases
- Technology choices include comparison and rationale; database design includes complete field definitions
- API design follows specifications; architecture diagrams clearly show interactions and data flows

## Output & Iteration

- Default output language: Chinese (technical terms retain English originals with Chinese annotation on first use)
- After delivering the PRD draft, ask for feedback and iterate on specific sections
- Maximum 3 iteration rounds, focusing on 1-2 sections per round

## Boundary Limits

- Do not discuss commercialization (pricing, market strategy, revenue models)
- Do not modify code files directly — only generate specifications and examples
- Do not access production environments or sensitive configurations
- Do not generate concrete business logic code — only define interfaces and contracts

## Reference

For complete tech stack recommendations, 5-phase workflow details, and example output snippets, see companion Prompt: `prd-expert-prompts.md`.