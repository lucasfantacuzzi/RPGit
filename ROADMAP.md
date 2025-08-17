## Roadmap (checklist)

### Core (MVP)
- [ ] Git integration (HTTP/SSH gateway to system Git binaries)
- [ ] Repo management API (create/archive/delete, init bare, set default branch)
- [ ] Hooks runner (post-receive template + per-repo symlink management)
- [ ] Campaigns, Bosses and Quests data model
- [ ] Basic Kanban board (SSR) — Tavern: Todo / Doing / Done
- [ ] XP and Level system for players (base curve + caps)
- [ ] Party support (teams)
- [ ] Hooks: commits/PRs translate into quests and boss damage
- [ ] Loot and badges system (rarity tiers; cosmetic only at first)
- [ ] Citadel (organization) to group multiple campaigns

### Git Operations
- [ ] Path sanitization & safe repo resolution
- [ ] HTTP auth on /git/* (Basic/JWT stub)
- [ ] SSH server (public-key auth; per-user key management)
- [ ] Branch protection rules (no force-push, required reviews — later)
- [ ] Repository import (existing bare path) & mirror support (read-only)

### RPG Mechanics
- [ ] Boss HP & damage formulas (based on quest points/labels)
- [ ] Boss phases (HP thresholds) and defeat state
- [ ] Anti-abuse: XP caps per day, commit-size heuristics, dedupe by idempotency-key
- [ ] Leaderboards (global, per citadel, per campaign, per party)
- [ ] Player classes (Warrior/Mage/…); class modifiers (later)
- [ ] Loot tables per boss; drop distribution for contributors
- [ ] Achievements (milestone-based badges)

### Project Management (Citadel / Campaign / Dungeon / Tavern)
- [ ] Dungeon model (sprint | pipeline | branch) with stages
- [ ] CI webhooks intake (GitHub Actions / GitLab / Jenkins) → dungeon stage status
- [ ] Gate rules: quest can’t go to “Treasure” unless dungeon stages are green
- [ ] Kanban filters (assignee, label, search, party)
- [ ] WIP limits per column / per player
- [ ] Quest checklists & attachments
- [ ] Notes in Tavern (lightweight threads per boss/quest)
- [ ] Swimlanes by party or label

### Pull Requests (optional v2)
- [ ] PR create/view UI (diffs, comments)
- [ ] Reviews & approvals (required count)
- [ ] Merge strategies (merge-commit / squash)
- [ ] Link PR ↔ quest; PR merged → bonus XP / loot roll

### Security & Permissions
- [ ] RBAC: Citadel (admin/member/guest), Campaign (maintainer/contributor/viewer), Party (lead/member)
- [ ] Sessions (secure cookies) + CSRF on forms
- [ ] Optional OIDC (Keycloak/GitHub/Google)
- [ ] Rate limiting & brute-force protection
- [ ] Audit log of sensitive actions
- [ ] Secrets management for CI webhooks

### API & Extensibility
- [ ] REST API v1 (versioned) for all core entities
- [ ] API tokens (scoped; per-user/per-citadel)
- [ ] Outbound webhooks for RPG events
- [ ] Rules engine (configurable weights: labels → XP/damage modifiers)
- [ ] Plugin hooks (event handler registration)

### Observability & Reliability
- [ ] Structured logging with request IDs
- [ ] Metrics (Prometheus): git ops, events processed, XP awarded, boss HP changes
- [ ] Tracing (OpenTelemetry) around event pipeline
- [ ] Dead-letter queue & replay for failed events
- [ ] Health/ready endpoints

### Packaging & Ops
- [ ] Docker image (multi-arch) + docker-compose quickstart
- [ ] Helm chart (ingress/TLS, persistence, resources)
- [ ] Config via env/file; sane defaults
- [ ] Backup/restore guide (DB + repos)
- [ ] Zero-downtime DB migrations (up/down)
- [ ] TLS via reverse proxy (Nginx/Caddy) examples
- [ ] Systemd unit (bare-metal install)

### Developer Experience & QA
- [ ] Makefile/Taskfile + devcontainer
- [ ] Seed script (demo citadel/campaign/boss/quests)
- [ ] Unit tests for domain services
- [ ] Integration tests (git clone/push; hook → event → XP/HP)
- [ ] E2E smoke tests (Kanban flow; dungeon gating)
- [ ] Load tests for large pushes & many events
- [ ] Linting & formatting (Go + templates)

### UX & Theming
- [ ] Responsive SSR templates (light/dark)
- [ ] Accessible components (a11y basics)
- [ ] Emoji/iconography mapping (Boss/Quest/Dungeon/Tavern)
- [ ] Theme variables (easy re-skin)
- [ ] i18n (EN / pt-BR)

### Docs & Community
- [ ] README quickstart (compose + first repo)
- [ ] ROADMAP.md (this checklist) kept in sync
- [ ] CONTRIBUTING.md (dev setup, style, commit conventions)
- [ ] CODE_OF_CONDUCT.md
- [ ] SECURITY.md (vuln reporting)
- [ ] Changelog & SemVer policy

- [ ] Example diagrams (mermaid) for Citadel → Campaign → Dungeon → Boss → Quest

