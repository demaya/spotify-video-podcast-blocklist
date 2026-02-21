# Repository Guidelines

## Project Structure & Module Organization
This repository is intentionally minimal and data-focused.
- `spotify-video-podcast-blocklist.txt`: canonical blocklist (one domain per line).
- `README.md`: top-level project description.

Keep the blocklist as the single source of truth. If supporting files are added later (for automation or validation), place them under clearly named folders such as `scripts/` and `tests/`.

## Build, Test, and Development Commands
There is no build pipeline. Use lightweight checks before committing:
- `wc -l spotify-video-podcast-blocklist.txt` checks list size changes.
- `sort -u spotify-video-podcast-blocklist.txt | wc -l` verifies uniqueness.
- `rg 'spotify|scdn|akamai' spotify-video-podcast-blocklist.txt` performs quick sanity checks on entries.

Optional cleanup (run only when intended):
- `sort -u spotify-video-podcast-blocklist.txt -o spotify-video-podcast-blocklist.txt`

## Coding Style & Naming Conventions
For `spotify-video-podcast-blocklist.txt`:
- Use lowercase domains only.
- Keep exactly one domain per line.
- No comments, wildcards, URLs, protocols, or trailing whitespace.
- Preserve plain UTF-8 text and a trailing newline at end of file.

File naming should stay descriptive and kebab-case where possible (for example, `domain-validation.sh`).

## Testing Guidelines
No automated test framework is currently configured. Validation is manual and data-quality focused:
- Ensure no duplicate domains.
- Ensure each entry is a valid hostname-like value.
- Confirm new domains are relevant to Spotify video/podcast delivery endpoints.

If tests are introduced, prefer simple shell-based checks in `tests/` and name files `*.test.sh`.

## Commit & Pull Request Guidelines
Current commit history uses short, imperative summaries (for example, `add blocklist`). Continue this style:
- Subject line in imperative mood, concise, lowercase acceptable.
- Explain domain additions/removals in the commit body when non-obvious.

PRs should include:
- What changed (added/removed domains).
- Why it changed (source, observation, or issue link).
- Any validation commands run and their result.
