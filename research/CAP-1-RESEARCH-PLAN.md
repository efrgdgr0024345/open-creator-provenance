# CAP-1 Research Plan

## RQ-001 — Prior art and feasibility

Find the strongest existing work in:
- robust/fragile/semi-fragile watermarking;
- steganography and steganalysis;
- natural/sensor-noise steganography;
- image-dependent authentication;
- ownership/counterfeit-claim attacks;
- undeniable/selectively verifiable signatures;
- camera provenance and trusted capture;
- trustworthy timestamping.

For every source record: citation, URL/DOI, claim supported, assumptions, limitations, and relevance to CAP-1.

## RQ-002 — Formal model

Define:
- image representation used by encoder/verifier;
- key hierarchy and per-image freshness;
- embedding and extraction functions;
- witness graph (which evidence authenticates which regions);
- score/statistic;
- null and alternative hypotheses;
- threat model;
- acceptance/attribution rules.

No probability claim may be made until this model exists.

## EXP-001 — Synthetic proof of concept

Start with lossless images. Implement the simplest testable content-bound, secret-selected embedding scheme. This is an experiment, not the final security design.

Measure:
- genuine-key score distribution;
- wrong-key score distribution;
- unrelated-image score distribution;
- edited-copy score distribution;
- competing-key search;
- extraction errors.

## EXP-002 — Noise adaptation

Replace fixed perturbations with image/noise-adaptive embedding. Compare marked vs unmarked distributions using multiple steganalysis approaches.

## EXP-003 — Witness coverage

Implement local and remote content witnesses. Measure how edit size/location changes the evidence relative to the retained original.

## EXP-004 — Ownership/attribution attacks

Actively test:
- counterfeit ownership claims;
- copy/transplant attacks;
- key-search attacks;
- chosen-image attacks;
- denoising and re-watermarking;
- adding a second claimant's mark;
- partial edits designed to preserve evidence.

## EXP-005 — Camera pipeline

Only after the digital prototype is credible, test RAW/sensor-to-image pipelines and determine where embedding must occur to preserve both concealment and trusted-capture meaning.

## Human-readable outputs

Every research cycle produces:
1. **Plain English:** what we learned and why it matters.
2. **Scientific:** assumptions, equations, sources, methods and uncertainty.
3. **Engineering:** reproducible implementation/test instructions.
4. **Adversarial review:** strongest reasons the result may be wrong.

## Evidence states

Every material claim must be labelled:
- IDEA
- HYPOTHESIS
- PRIOR-WORK SUPPORTED
- EXPERIMENTALLY OBSERVED
- REPRODUCED
- FALSIFIED / SUPERSEDED

The research system must never silently upgrade a claim's evidence state.
