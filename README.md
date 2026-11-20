<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/header-light.svg">
  <img alt="Rahul Modugula. AI/ML Engineer. I build systems that check their own work: trust layers, evaluation, distributed systems, ML infrastructure." src="assets/header-light.svg" width="900">
</picture>

I like software where the hard part is being **right**, not just fast: verification that fails closed, evaluations decided before the results exist, and pipelines that can prove what they did. Looking for new grad / early-career roles (F-1 OPT eligible).

## Featured

<table>
  <tr>
    <td align="center" valign="top">
      <a href="#sovereign-legal-ai-private-repo">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="assets/card-sla-dark.svg">
          <img alt="Sovereign Legal AI: citation checking for Indian advocates. Fail-closed verification, quotes matched to the Court's own paragraph, pre-registered evaluations. Private repo. Read more below." src="assets/card-sla-light.svg" width="290">
        </picture>
      </a>
    </td>
    <td align="center" valign="top">
      <a href="#resiliscore-private-repo">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="assets/card-rs-dark.svg">
          <img alt="ResiliScore: catastrophe-resilience scoring prototype on a 300 to 850 scale. Credibility-weighted estimates, contract-is-law schemas. Private repo. Read more below." src="assets/card-rs-light.svg" width="290">
        </picture>
      </a>
    </td>
    <td align="center" valign="top">
      <a href="#rezilient-hackathon-team-project">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="assets/card-rz-dark.svg">
          <img alt="Rezilient: forecast-driven outreach planning. Synthetic people and real places, a Bayesian model, a human sends every message. Hackathon team project. Read more below." src="assets/card-rz-light.svg" width="290">
        </picture>
      </a>
    </td>
  </tr>
</table>

<sub>These three live in private repositories, so each card links to its write-up below. The public projects are further down.</sub>

## Selected work

### Sovereign Legal AI (private repo)

A research and citation-checking tool built for Indian advocates. Each citation it checks is matched against the judgment text it finds, and it is designed so that a citation it cannot find is never shown as verified.

- **Fail-closed trust layer.** Name and year matching alone never verifies a citation. A quotation counts only when its words are found in the Court's own paragraph, not in a paragraph that merely records counsel's submissions.
- **Evaluation discipline.** Benchmark gates are pre-registered before runs, with held-out splits, fixed seeds and confidence intervals. Any change that could turn a failure into "verified" must ship with a fabricated-citation test that proves it still fails.
- **Search over the public record.** SQLite full-text search plus dense retrieval and a reranker over Supreme Court judgments and High Court records. Built on public material only.
- **Stack.** Python, FastAPI, Pydantic, SQLite FTS5, numpy, local OCR (including Telugu and Hindi), Fly.io.

```mermaid
flowchart LR
    D[Draft with citations] --> X[Extract citations and quotes]
    X --> L{Found in the record?}
    L -- no --> N[Shown as not found, never verified]
    L -- yes --> Q{Quotation given?}
    Q -- no --> V1[Citation matches a judgment]
    Q -- yes --> P{Words in the Court's own paragraph?}
    P -- no --> U[Flagged, not verified]
    P -- yes --> V2[Verified, with the paragraph shown]
```

It checks that a citation and quotation exist in the judgment text. It does not say whether the authority is still good law.

### ResiliScore (private repo)

A prototype exploring catastrophe-resilience scoring for properties on a 300 to 850 scale, with a 3D Manhattan explorer. Its coefficients are unvalidated, and the code labels them that way.

- **Credibility-weighted estimates.** Census-tract losses are blended with parcel-level evidence (Buhlmann-Straub credibility).
- **Contract is law.** Shared JSON schemas and pinned golden numbers change together, enforced by a sync test.
- **Honest limits.** The repo says plainly which model constants have no outcome test yet, and 48 numbered design decisions are written down.
- **Stack.** Python, FastAPI, Next.js, React, TypeScript, Three.js, Playwright, Fly.io.

### Rezilient (hackathon team project)

A prototype that turns a climate forecast into a ranked outreach list for care teams. Second place at the Health in Climate AI Hackathon NYC 2026, built with a team.

- **Synthetic people, real places.** All people are synthetic, places are real, and every real number is cited. No PHI anywhere in the code.
- **Bayesian model** in NumPyro and JAX, built as a ladder of increasingly fitted models.
- **Human in the loop.** The model ranks actions within capacity. A person sends every message, and medication questions are flagged to a pharmacist.
- **Stack.** Python, NumPyro, JAX, polars, FastAPI, React, deck.gl.

## More public projects

| Project | What it is |
| --- | --- |
| [witness](https://github.com/RahulModugula/witness) | A service that watches a procedure video and proves what happened, when, and by whom. Open-vocab object detection + tracking + hand-pose interaction logic. |
| [kronos](https://github.com/RahulModugula/kronos) | Distributed job scheduler in Go: gRPC, PostgreSQL, worker pool, retries. |
| [streamline](https://github.com/RahulModugula/streamline) | Real-time event pipeline: GitHub Archive to Kafka to Spark Structured Streaming to Delta Lake, with exactly-once semantics and schema evolution. |
| [athena](https://github.com/RahulModugula/athena) | RAG-powered research assistant with hybrid search (pgvector + BM25), cross-encoder reranking and RAGAS evaluation. |
| [odin](https://github.com/RahulModugula/odin) | AI-powered multi-agent code review combining Tree-sitter AST analysis with LLM agents. |
| [quantai-dashboard](https://github.com/RahulModugula/quantai-dashboard) | Real-time quantitative finance dashboard: options pricing (Black-Scholes), portfolio optimization (Markowitz) and risk analytics with Streamlit. |

## How I work

Tests first. Pre-registered evaluations. Fail-closed defaults. No secrets and no client data in repos.

**Stack:** Python · Go · TypeScript · FastAPI · PostgreSQL · SQLite · Kafka · Spark · Docker · Fly.io · GitHub Actions
