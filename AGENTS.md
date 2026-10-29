# AGENTS.md — APEX repository instructions for Codex

Project: APEX (Advanced Personal AI Agent). Repository: https://github.com/priyanshukumarverma468-dot/APEX

## Read first
Read README.md, MERGE_NOTES.md, docs/SETUP.md, docs/SECURITY.md, requirements.txt, backend/app.py, frontend/index.html, and existing tests. Inspect the actual repository tree; do not assume the uploaded ZIP has already been committed.

## Non-negotiable
- Continue the existing APEX project; do not scaffold a replacement or delete existing code.
- The user works on an Android phone only and has a ₹0 budget. Prefer free/open-source solutions; clearly identify any unavoidable external cost, API key, or provider limitation before implementation.
- Keep `backend/` as the active backend and `frontend/` as the active UI. Treat `experimental_backend/` as reference code, not a drop-in replacement; integrate pieces only after API compatibility review and tests. Keep `frontend_legacy/` as backup.
- No claims that tools, browser control, AI models, APK building, integrations, or tests work without actually validating them.
- Do not invent device-control permissions. Codex in a cloud environment cannot directly tap or control the user's Android phone or Chrome without a separately installed, authorized companion mechanism. Prefer a mobile-friendly web dashboard, explicit user approval, and clear manual phone steps.
- Never request passwords, session cookies, OTPs, or personal tokens in chat or commit them to git. Use environment secrets.
- Do not expose unauthenticated server endpoints to the internet. Require authentication, authorization, rate limiting, safe paths, and approval before destructive/external actions.
- Do not implement stealth access, covert monitoring, bypasses, or unauthorized remote device control.
- Preserve existing data and file paths. Make small reviewable changes, add tests, and document migration.

## What to build (in priority order)
1. Audit the existing code and produce `docs/IMPLEMENTATION_STATUS.md` with verified working/partial/missing features and reproduction commands.
2. Fix dependency and startup paths; document supported Linux/cloud development versus Android Termux limitations (notably Playwright and pydantic-core). Do not pretend that installing Rust alone fixes Android wheel issues.
3. Complete responsive APEX UI: dashboard, chat, tasks, workspace editor, agents, integrations, settings; accessible touch controls and useful error states.
4. Wire UI to actual FastAPI endpoints, with input validation, useful loading/error states and safe file handling.
5. Implement configurable AI provider interface with an explicit demo/offline mode. Never mislabel demo responses as real AI.
6. Add persistent task storage, cancellation, status logs, safe scheduling, and per-action confirmation for risky operations.
7. Add secure, opt-in memory with inspect/delete controls and clear local storage behavior.
8. Implement coding agent for repository edits and test execution in an isolated workspace; require approval for file deletion, commits, pushes and external deployments.
9. Browser automation only in a supported authorized environment, with allowlists, visible logs, timeouts and approval for external actions; report unsupported Android/Termux capabilities.
10. Add optional integrations (GitHub, Telegram, YouTube) with documented scopes, OAuth/approved APIs, dry-run where possible, and explicit confirmation before publishing/uploading.
11. Document APK build workflow separately; never label web UI as APK. Build APK only when Android source and toolchain are available.
12. Add CI tests, lint checks, security checks, and a clear Android-phone user guide.

## What NOT to add or do
- No paid-only dependencies, paid upgrades, or billing setup by default.
- No hardcoded credentials, unverified feature-complete labels, fake buttons, or simulated success messages.
- No silent auto-posting, mass messaging, scraping behind login, or uncontrolled agents.
- No blanket file-system access, phone control, SMS/call interception, or background device administration.
- No destructive repo reset, force push, branch deletion, or overwriting working modules.
- Do not automatically merge `experimental_backend/` into `backend/`.

## Acceptance and reporting
For each feature: state implemented files, setup prerequisites, test command and result, known limitations, and whether it runs on Android Termux or requires a cloud/Linux host. Prefer a pull request to direct commits to main. At the end, provide concise Hindi instructions suitable for Chrome on Android.
