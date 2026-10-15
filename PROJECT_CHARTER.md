# Project Charter — CAP-1

## Mission

Determine whether a physical camera can create an imperceptible, statistically defensible, photographer-controlled attribution proof inside the captured image itself.

## Primary research question

Can an image carry a secret-verifiable, image-specific signal whose measured evidence strongly distinguishes the legitimate capture/key relationship from unrelated images, wrong keys and competing claims?

## Required properties

### P1 — Per-image freshness
Every capture uses fresh per-image cryptographic material. Repeated photographs must not expose a reusable fixed pixel map sufficient to authenticate later captures.

### P2 — In-image evidence
Authentication evidence must be carried by the image content itself, not only EXIF, sidecar files or removable metadata.

### P3 — Noise-adaptive embedding
Embedding strength and placement must be informed by local image statistics/noise. "Inside the numerical range of noise" is not sufficient by itself; experiments must test whether the resulting distributions and correlations remain distinguishable.

### P4 — Content binding
Selected evidence must bear witness to image content, including local and/or remote regions, so the system measures a relationship to this image rather than merely detecting an identifier.

### P5 — Controlled verification
The legitimate holder must retain protected secret material required for the strongest attribution demonstration. The research must distinguish private verification, public verification and selectively disclosed proof.

### P6 — Competing-claim resistance
Testing must include whether another party can construct a different key/mark/claim that scores convincingly against an existing image.

### P7 — Quantified evidence
Results must state measured false-positive, false-attribution, false-rejection and attack-success rates with confidence intervals where appropriate.

### P8 — Capture time
The authenticated record may contain camera time, but camera time is not automatically trustworthy real-world time. Independent time evidence must be evaluated separately.

## Non-goals for CAP-1

CAP-1 does not initially attempt to:
- detect use in AI training;
- enforce copyright or payment;
- authenticate video/audio;
- prove legal ownership;
- prove that the depicted event itself is truthful;
- prove that the key holder personally pressed the shutter without an identity/authorization mechanism.

## Success criterion

CAP-1 succeeds only if an independently reproducible prototype produces strong attribution evidence while surviving serious steganalysis, competing-claim testing and manipulation testing under a clearly documented threat model.

A negative result is a valid project outcome.
