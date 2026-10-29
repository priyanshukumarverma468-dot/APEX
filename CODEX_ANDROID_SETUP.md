# Codex + GitHub setup from Android phone

1. Open https://github.com/priyanshukumarverma468-dot/APEX in Chrome and sign in.
2. To add these instructions without importing a ZIP: tap **Add file** > **Create new file**, enter `AGENTS.md`, paste the content from this package's AGENTS.md, then choose **Commit changes** (prefer a new branch if offered).
3. Open https://chatgpt.com/codex and connect GitHub when offered; select the APEX repository and an available cloud environment. If the repo does not appear, check GitHub app installation/repository access permissions in GitHub settings.
4. In Codex, ask: “Read AGENTS.md and MERGE_NOTES.md. Audit this repository first; create docs/IMPLEMENTATION_STATUS.md and a pull request implementing the highest-priority missing safe features. Do not replace the existing project.”
5. A ZIP saved only on your Android phone is not automatically visible to Codex. To use it, add its extracted contents to GitHub (Chrome may support individual file uploads, not direct ZIP extraction), or use Git commands from Termux.
6. Codex cloud browser/computer is separate from your physical phone. It cannot open arbitrary Android settings or control your phone by default.
7. Keep repository private until secrets, authentication, and deployment security have been reviewed.

Do not upload `.env`, credentials, token files, or phone backups. `.env.example` is okay when it contains placeholders only.
