# openclaw-addons

> A curated collection of community tools and skills for OpenClaw — the self-hosted AI agent platform.

Everything here is open source, battle-tested in production, and built around a shared philosophy:
- One-liner install
- Works on macOS and Linux
- Human-readable README + agent-readable runbook in every repo
- No mandatory cloud services

---

## Tools (infrastructure-level)

These run at the OS level alongside OpenClaw.

| Tool | What it does | Install |
|------|-------------|---------|
| [openclaw-postfix-pack](https://github.com/bkochavy/openclaw-postfix-pack) | Stamps every message with the actual model that sent it. `/status` lies. This doesn't. | `curl -fsSL https://raw.githubusercontent.com/bkochavy/openclaw-postfix-pack/main/install.sh \| bash` |
| [openclaw-watchdog](https://github.com/bkochavy/openclaw-watchdog) | Auto-recovers the gateway when it crashes. Codex or Claude Code diagnoses and repairs it. | `curl -fsSL https://raw.githubusercontent.com/bkochavy/openclaw-watchdog/main/install.sh \| bash` |
| [openclaw-backup](https://github.com/bkochavy/openclaw-backup) | Daily backup of your config to a private GitHub repo. Verified push + Telegram alert on failure. | `curl -fsSL https://raw.githubusercontent.com/bkochavy/openclaw-backup/main/install.sh \| bash` |

---

## Skills (agent-invocable)

Drop these into `~/.openclaw/workspace/skills/` and your agent can use them immediately.

| Skill | What it does | Install |
|-------|-------------|---------|
| [openclaw-build](https://github.com/bkochavy/openclaw-build) | Idea to shipped code. PRD interview → approved spec → Ralph coding loop (Codex or Claude Code). | `git clone ... ~/.openclaw/workspace/skills/openclaw-build` |
| [openclaw-agent-dashboard](https://github.com/bkochavy/openclaw-agent-dashboard) | Browser dashboard showing all running tmux/Ralph coding sessions. Status, task progress, git info. | `node server.js` from skill dir |

---

## Philosophy

Every tool here follows the same pattern:

**For humans:** one-sentence problem statement, one-line install, plain English docs.

**For agents:** a `skill/SKILL.md` or agent-readable section with exact commands, exit codes, and runbook so your OpenClaw agent can operate these tools without you.

**Cross-platform:** macOS (launchd) and Linux (systemd). No Homebrew dependency for core functionality.

---

## Adding to this list

Open a PR or issue. Requirements:
- Open source (MIT or Apache 2)
- Works on a fresh OpenClaw install (macOS or Linux)
- Has both a human section and an agent section in the README
- No hardcoded personal data

---

## Related

- [OpenClaw](https://github.com/openclaw/openclaw) — the platform these tools extend
- [awesome-openclaw-skills](https://github.com/VoltAgent/awesome-openclaw-skills) — broader community skill list
