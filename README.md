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
| [openclaw-prd-writer](https://github.com/bkochavy/openclaw-prd-writer) | Turn a rough idea into a build-ready spec through structured conversation. Two approval gates. | `git clone ... ~/.openclaw/workspace/skills/openclaw-prd-writer` |
| [openclaw-coding-loops](https://github.com/bkochavy/openclaw-coding-loops) | Run Codex/Claude Code in persistent tmux loops with retry, memory, and completion notification. | `git clone ... ~/.openclaw/workspace/skills/openclaw-coding-loops` |
| [openclaw-deck](https://github.com/bkochavy/openclaw-deck) | Multi-column web UI — chat with multiple agents side by side in your browser. | `npx openclaw-deck` |

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
