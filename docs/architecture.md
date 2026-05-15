# Architecture Overview

This document describes the planned architecture for Pay As You Learn.

## 1) Generation Flow

1. User chooses subject, topic, difficulty, and question count.
2. API validates request payload.
3. Engine composes prompt and model parameters.
4. LLM produces structured question candidates.
5. Validation layer checks schema, answer integrity, and quality rules.
6. Passed items are stored and returned to user.

## 2) Logical Components

- `app/api`: Request handling, authentication (future), and orchestration.
- `app/engine`: Prompting, model adapters, parsing, and retries.
- `app/shared`: Common schemas, enums, and utility functions.
- `tests/eval`: Quality and regression evaluations for generated content.

## 3) Question Object (planned)

- `subject`
- `topic`
- `difficulty`
- `question_text`
- `options` (if multiple choice)
- `correct_answer`
- `explanation`
- `tags`

## 4) Quality Gates

- Schema compliance
- Curriculum/age suitability
- No duplicate or near-duplicate question wording
- Answer correctness check for deterministic question types
- Banned-content safety checks

## 5) Observability (planned)

- Generation latency
- Validation pass/fail rate
- Regeneration count
- Human review score trend
