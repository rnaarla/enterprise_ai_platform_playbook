# Enterprise AI Platform Playbook

**A unified, implementation-ready blueprint for MLOps, SLMOps and LLMOps.**

Design, build, deploy, operate and scale enterprise AI systems across classical machine learning, small and large language models, retrieval-augmented generation and bounded agents.

![Version](https://img.shields.io/badge/version-1.0-blue)
![Prose License](https://img.shields.io/badge/prose-CC--BY--4.0-green)
![Templates License](https://img.shields.io/badge/templates-Apache--2.0-green)
![Status](https://img.shields.io/badge/status-living%20document-brightgreen)

---

## The premise

Most enterprise AI failures are not model failures. They are system failures.

Every production AI service is a versioned function:

> **Outcome = f(data, context, model, prompt, tools, policy, runtime, infrastructure, human process, time)**

A model artifact alone is not deployable evidence. Change any one input without versioning and testing it, and you have shipped a behavior change you cannot explain, reproduce or roll back.

This playbook is built on one non-negotiable idea: **the governed unit is the AI system, not the model.** Prompt edits, corpus refreshes, feature logic, provider upgrades, tool schemas and policy changes all change behavior; all of them require versioning, evaluation and traceability.

## What this is

A technology-neutral reference for the people who run AI in production. It standardizes a shared control plane over workload-fit data planes, and it carries the full lifecycle from intake to retirement, including the parts most teams skip.

It is not an introduction. It assumes production experience with ML systems and platform engineering. Product names in the text are representative options, not mandatory selections; regulatory statements are implementation guidance, not legal advice.

## Who it is for

- Platform and infrastructure leads building an internal AI platform
- Staff and principal ML / LLM engineers
- SRE and operations owners for AI services
- Model risk, AI governance, security and privacy functions
- Data and knowledge engineering teams
- Technical leaders making build-versus-buy and architecture decisions

## What is inside

Thirty-one sections across the full lifecycle.

**Foundations**
- Executive blueprint and the first-principles model
- Scope, definitions and workload taxonomy
- Design principles and non-negotiable invariants
- Enterprise reference architecture and topology
- Platform product and operating model
- Lifecycle gates (G0 to G7) and the artifact system

**Lifecycle stages (0 to 12)**
- Strategy, portfolio intake and risk tiering
- Data source onboarding and ingestion
- Data, feature and knowledge engineering
- Development environments and experimentation
- Training, fine-tuning and optimization
- Evaluation, validation and assurance
- Registration, provenance and promotion
- CI/CD/CT and release engineering
- Deployment and delivery patterns
- Inference, serving, RAG and agent runtime
- Monitoring, observability and value measurement
- Incident response, resilience and continuity
- Feedback, retraining, recertification and retirement

**Cross-cutting disciplines**
- AI governance, model risk and compliance
- Security and privacy architecture
- Infrastructure, capacity and performance engineering
- Reliability engineering and platform operations
- FinOps, cost and sustainability
- Developer experience and platform engineering
- Technology selection and build-versus-buy
- Implementation roadmap (0 to 12 months)
- Maturity model and executive scorecard
- Troubleshooting and operational runbooks

## Reusable templates

The `/templates` directory ships the artifacts you can put to work immediately:

| Template | Purpose |
|---|---|
| `aiservice-manifest.yaml` | Declarative AI service: intended/prohibited use, release digests, authorization, SLOs, observability |
| `data-contract.yaml` | Producer/consumer data contract with schema, service levels, retention and deletion propagation |
| `evaluation-policy.yaml` | Versioned evaluation gates with segments and confidence-interval lower bounds, not vibes |
| `gate-evidence-checklist.md` | Blocking questions and required evidence for gates G0 to G7 |
| `raci.md` | Compact decision-rights matrix across product, engineering, platform, risk and data ownership |
| `runbook-template.md` | Trigger, containment, diagnostics, rollback, evidence and prevention |

## Start here

1. Read the **Executive blueprint** and **Design principles** for the model and the invariants.
2. Map your own systems against the **risk-tiering** and **lifecycle gate** model.
3. Lift the **templates** into your platform and adapt them; they are starting points, not law.
4. Use the **maturity model** to score by workload archetype and risk tier, not by enterprise average.

The book is opinionated about *what to decide* and *the tradeoffs*; it is deliberately restrained about *what to pick*. Thresholds, capacities and SLOs are set from your business-loss curves and dependency reality, not from convention.

## Why this is open and living, not printed

Half of what makes a playbook useful decays on a six-month cycle: tooling, model and provider behavior, regulatory timelines. A reference that cannot be patched is already aging. This one is versioned, forkable and meant to be argued with in public.

Review cadence: at least every six months, and after any material change in regulation, the foundation-model landscape, enterprise risk appetite or platform architecture. See `CHANGELOG.md`.

## Roadmap to v1.1

Known improvements queued for the next revision. Pull requests welcome on all of them.

- One fully worked inference-sizing example and one training-memory example with real numbers
- KV-cache formula precision (the factor of two for K and V) and a mixed-precision Adam bytes-per-parameter rule of thumb
- A statistics appendix: bootstrap and paired-comparison methods, plus multiple-comparisons correction across blocking segments
- Explicit treatment of the fairness-definition tradeoff and the contamination problem for managed-API benchmarks
- Reduced cross-stage repetition via a shared common-controls reference

## Contributing

This gets sharper in the open.

- Open an **issue** for an error, a gap, a weak claim or a missing failure mode.
- Send a **pull request** for fixes, new templates, regulatory profiles or worked examples.
- Challenge the principles. The invariants earn their place by surviving scrutiny.

See `CONTRIBUTING.md` for conventions.

## License

- Prose and documentation: **CC-BY-4.0**. Use it, adapt it, cite it.
- Templates and code under `/templates`: **Apache-2.0**, so you can fork them into production without attribution friction.

## Citation

```
Naarla, R. (2026). Enterprise AI Platform Playbook: A unified, implementation-ready
blueprint for MLOps, SLMOps and LLMOps (Version 1.0).
https://github.com/rnaarla/enterprise-ai-platform-playbook
```

## Standards referenced

The playbook aligns to and cites primary sources rather than restating them, including NIST AI RMF (AI 100-1) and the Generative AI Profile, NIST adversarial ML taxonomy (AI 100-2), ISO/IEC 42001 and ISO/IEC 42005, the EU AI Act, NIST Zero Trust Architecture and SSDF (including SP 800-218A), OWASP Top 10 for LLM Applications, MITRE ATLAS, SLSA and Sigstore. Verify the current edition and legal applicability for your jurisdiction before implementation.

---

*The platform is not a collection of notebooks and endpoints. It is the enterprise control system that turns data, code, models, prompts and policies into governed, observable, repeatable business services.*
