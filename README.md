# Pay As You Learn

Open-source software that uses an AI-powered engine to generate high-quality **11+ grammar school exam practice questions**.

## Mission

Help students and families access affordable, personalized 11+ preparation by generating relevant practice material on demand.

## Target Users

- Students preparing for UK 11+ grammar school entrance exams.
- Parents/tutors looking for extra practice resources.
- Educators who want customizable question sets.

## Core Problem We Solve

Traditional 11+ prep can be expensive, static, and one-size-fits-all. This project aims to provide:

- Adaptive question generation by topic and difficulty.
- Rapid creation of worksheets/mock tests.
- Transparent, community-reviewed question quality.

## MVP Scope

Initial milestone (MVP):

1. Generate practice questions by subject area:
   - Verbal reasoning
   - Non-verbal reasoning
   - Mathematics
   - English (comprehension, grammar, vocabulary)
2. Choose difficulty level (easy/medium/hard).
3. Produce answer keys and short explanations.
4. Export printable worksheets (PDF/Markdown).
5. Save generated sets for later review.

## Proposed Repository Structure

```text
pay-as-you-learn/
├── README.md
├── LICENSE
├── .gitignore
├── docs/
│   ├── architecture.md
│   ├── development.md
│   └── roadmap.md
├── app/
│   ├── api/
│   ├── engine/
│   ├── web/
│   └── shared/
├── tests/
│   ├── unit/
│   ├── integration/
│   └── eval/
└── scripts/
```

## Architecture (high-level)

Planned core components:

- **Question Generation Engine**: Builds prompts, calls LLMs, enforces response schema.
- **Quality & Safety Layer**: Checks curriculum fit, age-appropriateness, duplication, and answer consistency.
- **API Service**: Exposes endpoints to generate/retrieve question sets.
- **Web App**: Lets users select subjects, difficulty, and download outputs.
- **Evaluation Pipeline**: Tracks quality over time using rubric-based and human-in-the-loop review.

## Guiding Principles

- **Student-first quality** over raw generation speed.
- **Explainable outputs** (answer + reasoning where appropriate).
- **Safety and fairness** for school-age learners.
- **Open contribution model** with clear review standards.

## Immediate Next Steps

1. Decide and document initial tech stack.
2. Build minimal API skeleton with one `/generate` endpoint.
3. Define strict JSON schema for generated questions.
4. Add baseline quality checks and unit tests.
5. Publish contribution and roadmap docs.

## Suggested Learning Path for New Contributors

1. Read this README and `docs/roadmap.md`.
2. Understand the data model for question objects.
3. Explore prompt templates and validation rules.
4. Add/extend a small quality check with tests.
5. Submit a small PR and request review.

## Contributing

Contributions are welcome. Please see `CONTRIBUTING.md` once added.

## License

Licensed under the Apache License 2.0. See `LICENSE` for details.
