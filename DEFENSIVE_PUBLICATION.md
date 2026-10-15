# Defensive Publication — Open Creator Provenance / CAP-1

**Public disclosure date:** 15 October 2026

This document records proposed technical concepts for open research and implementation. It intentionally includes alternatives and extensions so that the public record captures the substance of the proposal. It does not claim that every element is novel, patentable, secure or experimentally validated. Prior work must be identified and credited.

## Core concept

At image capture, a camera creates fresh per-image cryptographic material and embeds secret-dependent authentication evidence into the image itself using small, spatially distributed modifications designed to be consistent with the image's local noise/statistical characteristics.

The evidence is intended to permit a holder of protected secret material to later demonstrate a strong statistical relationship among:

- the protected key relationship;
- the particular captured image;
- an authenticated capture record; and
- capture-time information.

## Proposed implementation families

The proposal includes implementations in which:

1. pixel/sample locations are selected pseudorandomly from per-image secret material;
2. modification direction and magnitude depend on secret material and measured local image statistics;
3. selected locations encode or participate in checks of neighboring pixels, blocks, features or remote regions;
4. checks overlap so that image regions are witnessed by evidence distributed elsewhere;
5. evidence is sparse and distributed rather than a single visible or easily removable mark;
6. different image regions may use different embedding strengths according to estimated noise, texture, luminance or other perceptual/statistical properties;
7. evidence is evaluated statistically, allowing noisy measurements while aggregating many secret-dependent observations;
8. fresh per-image signing/authentication keys, embedding keys, nonces or derived secrets are used;
9. a protected master secret may derive purpose-separated per-image secrets using a cryptographic KDF, or per-image secrets may be independently generated;
10. a hardware security element/token/camera module may retain secret material and perform sensitive operations without exporting the long-term secret;
11. verification may be private/interactive, publicly verifiable, selectively disclosed, zero-knowledge, undeniable-signature-like, or use another protocol that demonstrates control without revealing signing secrets;
12. a capture record may bind an image representation, per-image identifier, key reference, camera/sensor assertions and time information;
13. external timestamp evidence may be bound to a digest/commitment without disclosing the image;
14. verification may produce an overall score plus local evidence/failure maps;
15. the system may preserve attribution evidence in copies/edits without treating a surviving mark as proof that the copy is unaltered.

## Two distinct security problems

The project treats these separately:

**Concealment:** Can an observer determine that authentication information has been embedded?

**Attribution/authentication:** Can a party without the legitimate secret create an equally convincing relationship between a different/competing key and the image?

A design is not considered secure merely because the changes are visually imperceptible.

## Extensions disclosed for future research

If CAP-1 succeeds, related mechanisms may be investigated for:

- video, including secret selection of frames/regions and chained witnesses across time;
- audio;
- photographs of physical artworks/objects as provenance evidence;
- creator-level corpus signals distinct from one-off per-image signals;
- statistical detection of marked works used in machine-learning training;
- recipient-specific corpus variants for source tracing;
- creator lineage systems connecting physical, digital and AI-assisted works.

These extensions are secondary to CAP-1 and are not claimed to be solved by this publication.

## Open research intent

The objective is public benefit and independent evaluation. Implementers should investigate existing patents, publications and licences before assuming freedom to operate.
