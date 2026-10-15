# AGENTS.md — Instructions for Codex and Other Coding Agents

## Read this first

This repository is an open public-benefit research project. The immediate job is **not** to build a commercial product and **not** to expand into every possible application.

### GOLDEN RULE

**CAP-1 comes first.**

CAP-1 asks whether a camera can embed an imperceptible, image-bound, photographer-controlled authentication signal into an image at capture time, allowing the legitimate holder to later demonstrate the capture/key relationship with an experimentally measured, extremely low false-attribution rate.

Before coding, read:
1. `README.md`
2. `PROJECT_CHARTER.md`
3. `DEFENSIVE_PUBLICATION.md`
4. `research/CAP-1-RESEARCH-PLAN.md`
5. `docs/PUBLIC-WEBSITE.md`

Do not silently weaken, reinterpret or expand the Golden Rule.

## Project philosophy

- Public benefit over monetisation.
- Open research.
- Credit prior work.
- Publish failures.
- Challenge the project's own assumptions.
- Prefer measurements and reproducible experiments to persuasive claims.
- Never describe statistical evidence as literally 100% unless mathematically justified.
- Never turn an AI-generated claim into an established fact without evidence.
- Keep humans able to understand what is happening.

## Immediate engineering milestone — M0

Build the smallest useful **Open Research Lab** around CAP-1.

M0 must provide:

### 1. Research runner
A command-line Python application that accepts a CAP-1 research question and calls the OpenAI Responses API using `OPENAI_API_KEY` from the environment.

Never request, print, log, store or commit the API key.

Model IDs must be configurable through environment/config rather than hard-coded assumptions about future model names.

### 2. Multi-role review
For each research question, create logically separate passes:
- Researcher — gathers and explains relevant evidence.
- Skeptic/attacker — searches for errors, counterexamples and missing prior art.
- Scientific reviewer — reconciles the evidence without hiding disagreements.
- Human writer — produces an understandable explanation.

Do not assume four expensive calls are always required. Reuse context/results and allow cheaper configurable models for routine passes.

### 3. Evidence records
Save each run in a stable machine-readable format containing at minimum:
- run ID;
- timestamp;
- question;
- model/configuration;
- sources/citations where available;
- researcher findings;
- adversarial review;
- reviewer conclusion;
- unresolved questions;
- evidence-state labels;
- token/usage data returned by the API;
- cost field if it can be calculated reliably, otherwise mark unknown rather than inventing it.

Do not store chain-of-thought. Store conclusions, evidence, critiques and concise reasoning summaries only.

### 4. Human reports
Generate from the same evidence record:
- plain-English report;
- scientific/technical report;
- engineering/action report;
- adversarial review.

### 5. Spending controls
Implement application-side controls:
- maximum calls per run;
- maximum output tokens per call;
- configurable model by role;
- dry-run mode;
- explicit confirmation/flag before expensive research runs;
- usage logging.

Do not claim dollar cost if current pricing is not configured from a reliable source.

### 6. Public website
Build a mobile-first PHP site following `docs/PUBLIC-WEBSITE.md`.

It must explain the project from the beginning and render research/evidence states clearly.

The website is read-only. It must not contain the OpenAI key or research execution credentials.

### 7. loader.php
Create a single-file bootstrap installer/updater for ordinary PHP hosting.

Requirements:
- install the public site from a pinned GitHub release/artifact;
- verify SHA-256 before installation;
- preserve local configuration;
- show installed version/commit;
- fail closed on verification failure;
- never contain API credentials.

If a secure release/update flow cannot yet be completed, implement a safe local/demo mode and document exactly what remains. Do not fake verification.

## Architecture preference

Keep M0 understandable.

Suggested:
- Python 3 for research/experiments;
- standard project files + JSON for evidence records initially;
- PHP for the public website/loader;
- GitHub Actions for tests and reproducible automation;
- no database/service complexity until evidence demonstrates it is needed.

## Security

- `.env` must be ignored.
- Provide `.env.example` with placeholders only.
- Never commit secrets.
- Treat AI-generated experimental code as untrusted until reviewed/tested.
- Do not execute arbitrary model-generated shell commands on production infrastructure.
- Separate public website code from research execution.

## Scientific discipline

Every material claim must use one of:
- IDEA
- HYPOTHESIS
- PRIOR-WORK SUPPORTED
- EXPERIMENTALLY OBSERVED
- REPRODUCED
- FALSIFIED / SUPERSEDED

When sources disagree, preserve the disagreement.

A paper is evidence, not truth by authority.

## Scope parking lot

Do not implement these during M0 unless required for CAP-1:
- AI-training tracing;
- video CAP-V;
- audio;
- royalty/payment systems;
- creator-lineage economics;
- legal copyright enforcement;
- commercial accounts/subscriptions.

Record good ideas for later rather than allowing them to derail CAP-1.

## Definition of M0 done

M0 is complete when a new contributor can:
1. clone the repo;
2. configure an API key locally/secretly;
3. run one research question;
4. inspect its structured evidence;
5. read the generated human reports;
6. run tests;
7. view the public project website locally;
8. understand exactly what CAP-1 claims and does not claim.

At completion, update the README with exact commands and limitations.

## Working method

Make small, reviewable commits. Run tests before claiming completion. Do not delete or rewrite the founding documents without explicit human approval. If implementation conflicts with the charter, stop and document the conflict rather than silently changing the charter.
