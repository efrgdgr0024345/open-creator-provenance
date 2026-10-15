# Open Creator Provenance

Open research into **CAP-1 (Capture Attribution Proof)**: whether a camera can embed an imperceptible, image-bound, photographer-controlled authentication signal into the image itself at capture time.

## Golden Rule

The first and most important objective is to **prove or disprove CAP-1**.

A successful CAP-1 design must let the legitimate key holder demonstrate, at a stated and experimentally measured confidence level, that:

1. a particular image carries authentication evidence created at capture;
2. that evidence is bound to that particular image rather than merely being a reusable watermark;
3. the evidence corresponds to a protected creator/camera key relationship;
4. an authenticated capture-time record is bound to the evidence; and
5. unrelated images and wrong/competing keys have an extraordinarily small measured false-attribution rate.

The project will not describe statistical evidence as literally "100%" when the mathematics only supports a finite probability. It will publish the measured false-positive, false-attribution and attack-success rates.

## Core proposed direction

CAP-1 investigates:

- fresh per-image cryptographic material;
- secret-dependent, sparse evidence distributed through image pixels;
- embedding adapted to the image's existing local noise/statistics;
- content-dependent witnesses, including relationships between selected locations and surrounding or remote image regions;
- photographer-controlled verification;
- resistance to competing ownership claims;
- trustworthy capture-time evidence;
- operation without requiring permanent dependence on a manufacturer cloud service.

The public image must not reveal enough information to let possession of many prior images authenticate a new image.

## Scope discipline

**Phase 1: CAP-1 only.**

AI-training tracing, video, audio, creator lineages, royalties and other applications are recorded as future research directions. They must not distract from proving or disproving CAP-1.

## Research principles

- Publish failures as well as successes.
- Separate assumptions, hypotheses, experimental results and established facts.
- Cite prior work and credit its authors.
- Prefer reproducible experiments over persuasive language.
- Actively attempt to falsify the design.
- Do not claim legal ownership merely because a cryptographic relationship is demonstrated.
- Distinguish camera-recorded time from independently trustworthy time.
- Keep the project open for independent implementation and criticism.

## Current status

**Research / experimental. No security or ownership claims have yet been demonstrated.**

See:
- [PROJECT_CHARTER.md](PROJECT_CHARTER.md)
- [DEFENSIVE_PUBLICATION.md](DEFENSIVE_PUBLICATION.md)
- [research/CAP-1-RESEARCH-PLAN.md](research/CAP-1-RESEARCH-PLAN.md)
