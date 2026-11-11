# Handoff: start here in Claude Code

1. Open this folder in Claude Code. CLAUDE.md loads automatically.
2. The site is already committed locally (one commit on `main`), but it was pushed and Pages enabled on 2026-11-11. Live: https://kritarthasuvarna-spec.github.io/
3. First prompt to give Claude Code:
   > Push this repo to origin main, enable GitHub Pages (branch main, root) with `gh api`, and give me the live URL. Optionally rename the repo to kritarthasuvarna-spec.github.io first.
4. Requirements on the PC: git, and the GitHub CLI (`winget install GitHub.cli`, then `gh auth login`). Python, for a local preview server.
5. If the remote is missing, run: `git remote add origin https://github.com/kritarthasuvarna-spec/kritarthsuvarna.github.io.git`
