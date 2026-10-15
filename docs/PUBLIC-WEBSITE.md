# Public Website — Human Front Door

The project should be understandable by someone with no cryptography, camera, AI or software background.

## Principle

The website is a view of the repository's evidence, not a second source of truth.

Research records, hypotheses, experiments and results live in version-controlled project files. The site turns them into an accessible narrative.

## Reader journey

1. **The problem** — AI makes it increasingly difficult to know who created/captured an image.
2. **The idea** — hide photographer-controlled, image-bound evidence inside the image itself at capture.
3. **How it might work** — plain-language interactive explanation of noise-adaptive secret witnesses.
4. **What we are NOT claiming** — current limitations and unproven assumptions.
5. **Can it work?** — CAP-1 hypotheses and their evidence states.
6. **Experiments** — what was tested, methods, results and failures.
7. **Attack the idea** — strongest known objections and attempts to break it.
8. **Timeline** — project history from first public disclosure onward.
9. **Technical view** — equations, threat model, source papers and reproducibility.
10. **Build/use it** — source code and eventual prototype instructions.

## Evidence UI

Every important statement should visibly carry one status:

- IDEA
- HYPOTHESIS
- PRIOR-WORK SUPPORTED
- EXPERIMENTALLY OBSERVED
- REPRODUCED
- FALSIFIED / SUPERSEDED

Never turn an AI-generated assertion into a green/confirmed claim without evidence.

## Deployment

### Recommended structure

- `public/index.php` — public site entry point.
- `public/api.php` — read-only structured project data if needed.
- `site-data/` — generated JSON/Markdown summaries committed by research runs.
- `loader.php` — optional one-file bootstrap installer for ordinary PHP hosting.

### loader.php

The loader should:
1. check PHP/runtime requirements;
2. download a pinned/tagged release from this public repository;
3. verify the downloaded release against a published SHA-256;
4. install/update only the public website files;
5. preserve local configuration;
6. show the exact repository release/commit installed;
7. fail closed on hash/signature mismatch.

The loader must never contain the OpenAI API key.

## Security boundary

The public website should be read-only by default. Research API keys, GitHub write credentials and experimental execution do not belong in the public web root.

## Mobile first

The site must work well on phones. Start with a short explanation and progressively reveal technical depth rather than opening on a wall of research text.
