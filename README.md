# openclaw-addons

> The community hub for tools, skills, and infrastructure extensions for [OpenClaw](https://github.com/openclaw/openclaw) — the self-hosted AI agent platform.

OpenClaw gives you a personal AI agent that lives on your own machine: no subscriptions, no vendor lock-in, no data leaving your infrastructure. This repo is the index of everything the community has built on top of it — from OS-level daemons that keep your agent healthy 24/7, to skills that turn your agent into a full engineering team.

Everything here is open source, agent-operable, and designed around one rule: **if your agent can't run it without you, it doesn't belong here.**

Core guarantees across every entry:
- ✅ One-liner install
- ✅ Works on macOS and Linux
- ✅ Human-readable README + agent-readable `SKILL.md` or runbook in every repo
- ✅ No mandatory cloud services

---

## Getting Started

New to OpenClaw? Start here.

**1. Install OpenClaw**

```bash
npm install -g openclaw
openclaw gateway start
```

Full docs at [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw).

**2. Pick your infrastructure layer** (tools below) — these run at the OS level alongside your gateway and keep it healthy, observable, and backed up.

**3. Drop in skills** — these live in `~/.openclaw/workspace/skills/` and your agent discovers and uses them automatically when tasks match.

**4. Talk to your agent.** It knows about the tools it has. You don't need to invoke skills by name.

---

## Tools (infrastructure-level)

These run at the OS level alongside OpenClaw — as launchd services (macOS) or systemd units (Linux). Install them once and forget they exist until you need them.

| Tool | Problem it solves | Install |
|------|------------------|---------|
| [openclaw-postfix-pack](https://github.com/bkochavy/openclaw-postfix-pack) | **You can't tell which model actually sent a message.** `/status` reports config, not reality. This stamps every outbound message with the real model name — no guessing, no gaslighting. | `curl -fsSL https://raw.githubusercontent.com/bkochavy/openclaw-postfix-pack/main/install.sh \| bash` |
| [openclaw-watchdog](https://github.com/bkochavy/openclaw-watchdog) | **Your gateway crashes at 2am and nobody notices.** Watchdog monitors the process, auto-recovers it, and when a simple restart isn't enough, spins up Codex or Claude Code to diagnose and patch the root cause. | `curl -fsSL https://raw.githubusercontent.com/bkochavy/openclaw-watchdog/main/install.sh \| bash` |
| [openclaw-backup](https://github.com/bkochavy/openclaw-backup) | **One bad `openclaw.json` edit and your config is gone.** Daily encrypted backup to a private GitHub repo, with a verified push check and a Telegram alert if anything fails — before you even notice a problem. | `curl -fsSL https://raw.githubusercontent.com/bkochavy/openclaw-backup/main/install.sh \| bash` |

---

## Skills (agent-invocable)

Drop these into `~/.openclaw/workspace/skills/` and your agent picks them up immediately — no restart required. Each skill ships with a `SKILL.md` that your agent reads to understand when and how to use it.

| Skill | Problem it solves | Install |
|-------|------------------|---------|
| [openclaw-tailserve](https://github.com/bkochavy/openclaw-tailserve) | **Sharing a local file or port always takes too many steps.** TailServe wraps Tailscale to give your agent a single command that produces a verified HTTPS URL — shareable in Telegram, browser, or anywhere else — in under a second. | `npm install -g tailserve` |
| [openclaw-build](https://github.com/bkochavy/openclaw-build) | **Going from idea to shipped code still requires you in the loop.** Build runs a PRD interview, gets your approval on the spec, then hands off to a coding loop (Codex or Claude Code) and doesn't stop until it's done and tested. | `git clone https://github.com/bkochavy/openclaw-build ~/.openclaw/workspace/skills/openclaw-build` |
| [openclaw-agent-dashboard](https://github.com/bkochavy/openclaw-agent-dashboard) | **You have no idea what your sub-agents are actually doing.** The dashboard gives you a live browser view of every running tmux and coding session — task description, git status, token usage, and whether it's spinning or stuck. | `git clone https://github.com/bkochavy/openclaw-agent-dashboard ~/.openclaw/workspace/skills/openclaw-agent-dashboard && node ~/.openclaw/workspace/skills/openclaw-agent-dashboard/server.js` |

---

## Philosophy

Every tool and skill here follows the same design contract:

**For humans:** one-sentence problem statement, one-line install, plain English docs. You should be able to evaluate, install, and trust a tool in under 5 minutes.

**For agents:** a `SKILL.md` or agent-readable runbook section with exact commands, expected outputs, exit codes, and failure handling — so your OpenClaw agent can operate these tools autonomously without interrupting you.

**Cross-platform:** macOS (launchd) and Linux (systemd). No Homebrew dependency for core functionality. No cloud account required to get value.

---

## Adding to this list

Open a PR or issue with your tool or skill. Requirements:

- Open source (MIT or Apache 2.0)
- Works on a fresh OpenClaw install (macOS or Linux)
- Has both a human-facing README section and an agent-facing `SKILL.md` or runbook
- No hardcoded personal data, credentials, or user-specific paths
- Tested on at least one real OpenClaw deployment

We're not trying to be exhaustive — we're trying to be trustworthy. Quality over quantity.

---

## Related

- [OpenClaw](https://github.com/openclaw/openclaw) — the platform these tools extend
- [awesome-openclaw-skills](https://github.com/VoltAgent/awesome-openclaw-skills) — broader community skill list (19k+ stars, the definitive catalog)
