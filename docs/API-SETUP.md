# OpenAI API Setup

The research runner uses the OpenAI API independently of ChatGPT message limits.

## Secret

Set this only in the execution environment:

```bash
export OPENAI_API_KEY="your-key-here"
```

For local development, a future `.env` file may be supported, but it must remain ignored by Git.

For GitHub Actions, store the key using GitHub Actions secrets. Do **not** place the value in workflow YAML, source files, issues, README files, logs or screenshots.

## Configuration

Model names and research-role assignments must be configurable. Do not assume that today's preferred model names or pricing will remain permanent.

Expected configuration concepts:

```text
OPENAI_API_KEY=...
OCP_RESEARCH_MODEL=...
OCP_REVIEW_MODEL=...
OCP_WRITER_MODEL=...
OCP_MAX_CALLS_PER_RUN=...
OCP_MAX_OUTPUT_TOKENS=...
```

Only `OPENAI_API_KEY` is sensitive. The repository should provide safe example values/placeholders for the rest.

## First API task

The first real research run should address:

**RQ-001: What prior research most closely anticipates CAP-1, and which CAP-1 properties remain unproven or materially different?**

The run must actively search for reasons CAP-1 may fail or already exist. It must not be prompted to prove the idea correct.
