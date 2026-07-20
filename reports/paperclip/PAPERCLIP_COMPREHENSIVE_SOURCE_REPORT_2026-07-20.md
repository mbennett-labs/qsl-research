# Paperclip Comprehensive Source Report

- **Date:** 2026-07-20
- **Status:** Source Reference
- **Scope:** Consolidated reference capture of two Paperclip video transcripts (founder interview and full tutorial), covering product concepts, installation, configuration, operating models, skills, memory, routines, costs, security, shareable companies, demonstrated use cases, limitations, and QSL-specific interpretation.
- **Sources:**
  - **Transcript 1** — `transcripts/paperclip/transcript-01.md` — "Founder of Paperclip shows how" (interview/screen-share with Paperclip's anonymous founder; sponsor: Zapier). Duration ~20:49.
  - **Transcript 2** — `transcripts/paperclip/transcript-02.md` — "Paperclip Is Insane - Full Tutorial" (TechWithTim tutorial; sponsor/partner: Hostinger). Duration ~38:43.
- **Intended downstream uses:**
  1. Operating Paperclip effectively.
  2. Designing governed AI organizations.
  3. Building the future QSL operating handbook.
  4. Creating client-facing services and demonstrations.
  5. Preserving product details, workflows, terminology, examples, limitations, and emerging opportunities.
- **Doctrinal status:** This document is a **source reference report**, not the canonical QSL doctrine. Verified lessons here should later be absorbed into dedicated QSL doctrine chapters (see "Suggested doctrine chapters" at the end). Where QSL interpretation is added, it is explicitly labeled.
- **Confidence:** Medium-high for workflow and configuration content (two independent sources align); low for performance, security, cost, and roadmap claims (unverified; see Section 25).
- **Reviewed:** No — pending human review (15 min max) before downstream use.

## Pipeline Context

This report is one stage in the YT-Transcripts knowledge flow:

```
VIDEO
  │
  ▼
Raw Transcript
  (YT-Transcripts)
  │
  ▼
Comprehensive Reference Report        ◄── this document
  (Kimi/Claude)
  │
  ▼
Human Review (15 min max)
  │
  ▼
Commit to YT-Transcripts
  │
  ▼
Pull only useful concepts into:
  • QSL Doctrine
  • Paperclip Docs
  • TheBinMap
  • Client Playbooks
```

Nothing downstream should cite this report as authority until the Human Review step is complete and Section 25 (Claims and Verification Register) has been worked.

## Citation and Evidence Conventions

- Citations use the form `[Transcript 1, 01:18–02:21]` and `[Transcript 2, 21:45–22:35]`. Timestamps correspond to segment boundaries in the source transcript files (source format `HH:MM:SS`, rendered here as `MM:SS`; all videos are under one hour).
- Evidence classes used throughout:
  - **[Observed]** — directly demonstrated on screen in the source.
  - **[Claimed]** — stated by a speaker as fact, not independently verified.
  - **[Promotional]** — marketing, sponsorship, or visionary framing.
  - **[Speculative]** — hypothetical examples or predictions by presenters.
  - **[Inferred]** — reasonable operational lesson drawn from the sources.
  - **[QSL]** — QSL-specific interpretation or recommendation; not from the sources.
- Both transcripts are auto-generated (NoteGPT) captions. Product names and CLI commands are occasionally garbled (e.g., "OpenClaude" is almost certainly **OpenClaw**; "NPX paper clip AI onboard" is treated as an approximate rendering of the onboarding command). Uncertain renderings are flagged where they matter.

## Table of Contents

1. Executive Overview
2. Source Notes
3. Paperclip's Core Value Proposition
4. Architecture and Core Concepts
5. Installation and Deployment
6. Model and Adapter Configuration
7. Company Onboarding Workflow
8. Issue-Based Work Model
9. CEO Operating Model
10. Agent Creation and Hiring
11. Skills
12. Memory
13. Routines and Recurring Work
14. Review and Feedback Patterns
15. Costs, Budgets, and Resource Control
16. Security and Isolation
17. companies.sh and Shareable Companies
18. Demonstrated Use Cases
19. Limitations and Unresolved Questions
20. QSL's Deliberate Divergence
21. Revenue and Service Opportunities
22. QSL Implementation Recommendations
23. Operational Checklists
24. Terminology and Glossary
25. Claims and Verification Register
26. Source-Derived Insights
27. Open Questions
28. Conclusion
- Appendix A. Actionable Takeaways
- Recommended Next Actions / Doctrine Chapters / Change Log

---

# 1. Executive Overview

**What Paperclip is.** Paperclip is an open-source orchestration framework for running a multi-agent "AI company": a persistent organization of AI agents (a CEO, managers, and workers) that coordinate through a shared, issue-based project-management system rather than through ad-hoc chat sessions [Transcript 2, 00:00–00:51] [Transcript 1, 00:00–00:53]. It is self-hosted (local machine, dedicated machine, or VPS/Docker) and model-agnostic: agents are executed through "adapters" to CLI tools such as Claude Code or Codex, or to direct API providers [Transcript 2, 03:16–04:05] [Transcript 2, 16:52–17:40].

**The problem it attempts to solve.** The founder states he built Paperclip because running multiple companies from the terminal with Claude Code and Cursor produced too many parallel sessions with no durable record of "what anybody was doing or what anyone was working on" [Transcript 1, 01:18–02:21]. A second stated problem is agent amnesia: coding agents "wake up" each invocation "insanely capable, but they have no idea who they are or what they're supposed to be working on or what they worked on yesterday" [Transcript 1, 01:49–02:41]. Paperclip's answer is a task-manager-like system in which conversations, costs, instructions, skills, and outcomes are tracked and retrospectively inspectable [Transcript 1, 01:18–02:21].

**General operating model.** The human operator acts as a "board of directors": they create a company with a mission and goal, connect at least one model adapter, and launch an initial task that causes the CEO agent to request its first hire [Transcript 2, 19:42–20:26] [Transcript 2, 00:50–01:44]. Thereafter the CEO runs on a configurable "heartbeat" (default hourly; the tutorial presenter used 600 seconds), triaging unassigned issues, delegating to specialist agents, requesting Board approval for new hires, and surfacing items to the operator's inbox [Transcript 2, 21:45–22:35] [Transcript 2, 22:10–23:07] [Transcript 2, 26:29–27:16]. Work proceeds as issues moving through backlog → to-do → in-progress → in-review/blocked → done states [Transcript 2, 28:33–29:27].

**Positioning vs. reality.** The creator frames Paperclip as enabling a "zero human business" and claims to have "one shot an entire company" while also saying "I don't want to oversell it" [Transcript 1, 00:00–00:53]. The tutorial presenter reports meaningful outputs after ~48 hours (newsletter analysis, website PR, a new repo) while also noting the product is immature and still requires substantial human involvement [Transcript 2, 00:00–00:51] [Transcript 2, 38:00–38:49]. The founder states Paperclip was "3 weeks old" at the time of the interview and that a "maximizer mode" to keep agents working continuously was not yet released [Transcript 1, 09:04–10:17]. QSL treats the zero-human framing as aspirational marketing, not an operating model; see Section 20.

---

# 2. Source Notes

## 2.1 Transcript 1 — "Founder of Paperclip shows how" (interview)

| Attribute | Assessment |
|---|---|
| Apparent speaker / context | Paperclip's founder (anonymous, cartoon avatar; states he comes from "the crypto world" and values anonymity) interviewed by a host ("Andrew") via screen share [Transcript 1, 00:55–01:41]. Recorded on companies.sh launch day [Transcript 1, 06:30–07:33]. |
| Main focus | Product vision, live demo of the founder's own company, skills (skills.sh), companies.sh one-command company installs, G Stack template, routines, export/marketplace ideas. |
| Technical detail | Low-to-moderate. Concepts and demos, little configuration depth; commands shown briefly (`npx` onboarding, `companies.sh add …`) [Transcript 1, 11:14–12:47]. |
| Promotional / sponsorship context | "Presented by Zapier, the AI automation company" [Transcript 1, 00:00–00:53]. Launch-day framing; founder explicitly says "I don't want to oversell it. I just want to show what's possible today" — while also making maximal claims ("zero human business", "one shot an entire company") [Transcript 1, 00:00–00:53]. |
| Limitations | Creator is inherently biased; demos are on his own prepared companies; anonymity prevents credential verification; transcript is auto-generated with garbled command renderings; product was ~3 weeks old at recording [Transcript 1, 09:04–10:17]. |

## 2.2 Transcript 2 — "Paperclip Is Insane - Full Tutorial" (TechWithTim)

| Attribute | Assessment |
|---|---|
| Apparent speaker / context | Independent YouTube tutorial presenter (TechWithTim), ~48 hours of hands-on use at recording time [Transcript 2, 00:00–00:51]. |
| Main focus | End-to-end setup: Hostinger VPS one-click Docker deployment, admin credentials, SSH + container CLI authentication (Claude Code / Codex subscriptions), company creation, heartbeat configuration, issue workflow, hiring, prompts, goals, integrations. |
| Technical detail | High for setup and day-one operation; low for internals (describes Paperclip as "an orchestration platform around the existing LLMs" that one "could remake… in a few days") [Transcript 2, 37:09–38:06]. |
| Promotional / sponsorship context | Hostinger partner; presenter discloses a 10% discount code for 12+ month plans [Transcript 2, 05:40–06:29]. Title/thumbnail framing ("Insane") is hype; in-video tone is more measured. |
| Limitations | Self-described novice ("I'm new to using this as well… brand new tech") [Transcript 2, 33:14–33:55]; security examples (agents buying courses, using credit cards) are speculative illustrations, not observed events [Transcript 2, 03:40–04:28]; some uncertainty about provider terms of service ("I'm not exactly sure if they're allowing this or not") [Transcript 2, 13:58–14:49]; auto-generated transcript renders "OpenClaw" as "OpenClaude" and some commands approximately. |

## 2.3 Cross-source limitations

- Neither source shows the Paperclip source code, docs, or repository; all capability statements are screen-share or verbal claims.
- Timestamps are segment-level (20–60s granularity), so citations locate topics, not exact sentences.
- No source demonstrates a business operating dependably without human intervention; both include continuous human approvals and manual fixes.

---

# 3. Paperclip's Core Value Proposition

The sources collectively present the following value claims. Classification: **[Claimed]** unless noted.

1. **Multi-agent organization.** A persistent org chart of agents (CEO, managers, workers) with reporting relationships, instead of isolated chat/coding sessions [Transcript 2, 00:50–01:44] [Transcript 1, 00:27–01:23]. **[Observed]** in both demos.
2. **Task and issue management.** Work is created, assigned, prioritized, and tracked as issues on list/Kanban views — "project management built for agents" [Transcript 2, 28:33–29:27] [Transcript 1, 06:00–06:59]. **[Observed]**.
3. **Persistent instructions.** Each agent carries standing instructions (system prompts / role definitions) so it wakes knowing "who they are… what they're supposed to be working on" [Transcript 1, 01:49–02:41] [Transcript 2, 34:23–35:17]. **[Observed]** configuration screens.
4. **Traceable conversations.** "All the conversations are tracked" and every run can be reopened [Transcript 1, 01:18–02:21] [Transcript 2, 24:59–25:44]. **[Observed]**.
5. **Cost tracking.** Per-run token/cost visibility when using metered APIs; budgets and spending limits configurable [Transcript 2, 02:04–02:51] [Transcript 2, 24:59–25:44] [Transcript 2, 07:34–08:18]. **[Observed]**.
6. **Retrospective inspection.** "You can go back and see how they did it, if they did a good job, if something went wrong, how to fix it" [Transcript 1, 01:18–02:21]. **[Observed]** via run history and issue summaries [Transcript 2, 29:24–30:13].
7. **Organizational visibility.** Org chart, dashboard of live sessions, inbox of items needing attention, success-rate stats [Transcript 2, 25:44–26:54] [Transcript 2, 26:29–27:16]. **[Observed]**.
8. **Coordination across agent sessions.** Persistent Claude Code/Codex sessions that "stay persistent and can kind of go and message each other" via the platform's issue/task APIs [Transcript 2, 37:09–38:06]; feedback loops where agents review each other's output [Transcript 2, 33:57–34:48]. **[Observed/Claimed]**.
9. **Skills and memory attachment.** Agents can be given reusable "skills" and long-term memory methods at hire time [Transcript 1, 04:31–05:23] [Transcript 1, 05:31–06:30]. **[Observed]**.
10. **Shareable companies.** Export/import of whole companies (agents + skills + structure) via companies.sh [Transcript 1, 07:57–09:13] [Transcript 1, 18:41–19:35]. **[Observed]** import; export shown.

**Why not just use Claude Code / Codex / OpenCode / Cursor directly?** Both sources answer explicitly: for a single fast interaction, direct tools remain better — "if you simply wanted to kind of chat… you can still use Claude for that directly" [Transcript 1, 14:58–16:01], and Paperclip is "overkill for simple tasks" [Transcript 2, 37:09–38:06]. Paperclip's claimed advantage appears when "you are trying to manage 50 different things with your agents and you can't remember what every tab is doing" [Transcript 1, 14:58–16:01], i.e., durable oversight, delegation, and audit of many concurrent autonomous sessions — the exact pain that motivated the founder [Transcript 1, 01:18–02:21] and that the tutorial presenter echoes after two days of unattended runs [Transcript 2, 02:52–03:39].

---

# 4. Architecture and Core Concepts

Paperclip's own internals are not shown in the sources; the architecture below is reconstructed from the UI, setup flow, and presenter descriptions. The tutorial presenter's summary: "this is effectively an orchestration platform around the existing LLMs… different Claude Code/Codex sessions that stay persistent and can kind of go and message each other… sending effectively API requests to create different issues and tasks" [Transcript 2, 37:09–38:06]. **[Claimed/Observed mix]**

## 4.1 Concept definitions

| Concept | What the sources say | Evidence |
|---|---|---|
| **Instance** | A deployed Paperclip server (local machine, dedicated machine, or VPS in Docker). On Hostinger the home directory contains `instances/paperclip` [Transcript 2, 17:41–18:33]. One instance hosts multiple companies [Transcript 2, 37:09–38:06]. | Observed |
| **Company** | The top-level organizational unit: name + mission/goal, its own agents, projects, issues, goals, and budgets. Multiple companies per instance [Transcript 2, 15:58–16:50] [Transcript 2, 37:09–38:06]. | Observed |
| **Mission / Goal** | Set at company creation; "super important that you're very specific… but don't make it super long" — like a corporate mission statement with more specifics [Transcript 2, 15:58–16:50]. Subgoals can refine a main goal [Transcript 2, 26:53–27:45]. | Observed |
| **Project** | A grouping of related issues inside a company; issues are filed under projects [Transcript 2, 23:52–24:34] [Transcript 2, 30:56–31:42]. The CEO may create projects autonomously [Transcript 2, 22:39–23:22]. | Observed |
| **Issue** | The unit of work (see Section 8). Created by humans or agents; has assignee, priority, labels, attachments, dates, comments, state [Transcript 2, 24:37–25:21] [Transcript 2, 28:33–29:27]. | Observed |
| **Agent** | A persistent, instruction-carrying worker backed by a model adapter session (Claude Code, Codex, etc.) [Transcript 2, 37:09–38:06]. Wakes stateless per invocation and relies on Paperclip for identity/context [Transcript 1, 01:49–02:41]. | Observed |
| **CEO** | The first agent; the operator's primary interface. Runs the heartbeat, triages unassigned issues, delegates, proposes hires, escalates to the inbox [Transcript 2, 21:18–22:12] [Transcript 2, 22:10–23:07]. | Observed |
| **Managers / workers** | Hierarchical org chart below the CEO (e.g., CTO with coders under it [Transcript 1, 00:27–01:23]; founding engineer reporting to CEO [Transcript 2, 23:00–23:48]). "Agents can then hire their own agents" for deeper hierarchies [Transcript 2, 01:17–02:03]. | Observed (hierarchy); claimed (deep nesting) |
| **Organizational chart** | Visual tree of agents and reporting lines [Transcript 2, 23:00–23:48] [Transcript 1, 00:55–01:41]. | Observed |
| **Heartbeat** | A scheduled wake of the **CEO only**: "by default every hour the CEO will be triggered to start executing… look at any of the tasks that are in the pipeline" [Transcript 2, 21:45–22:35]. Configurable interval; presenter used 600s [Transcript 2, 22:10–23:07]. Manual trigger button exists [Transcript 2, 24:13–25:01]. | Observed |
| **Routines** | Recurring work definitions (e.g., nightly bookmark sync → strategy report) [Transcript 1, 16:02–17:18]. | Observed |
| **Skills** | Reusable capability packages attached to agents (Section 11) [Transcript 1, 02:45–03:56]. | Observed |
| **Memory** | Persistent context via instructions and memory skills (e.g., PARA method) (Section 12) [Transcript 1, 05:31–06:30]. | Observed (mechanism); claimed (effectiveness) |
| **Permissions** | Per-agent toggles, e.g., CEO's "can create agents" [Transcript 2, 22:39–23:22]; "capabilities" section exists in agent configuration [Transcript 2, 35:37–36:21]. | Observed |
| **Approvals** | Human approval requests, e.g., hire requests arriving in the inbox, approved one by one [Transcript 2, 32:53–33:35]; issue-state approvals via comments [Transcript 2, 29:48–30:30]. | Observed |
| **Inbox** | Operator notification queue: "stuff that it wants you to be aware of… issue done, waiting for review, hire requests"; only what the CEO judges relevant [Transcript 2, 26:29–27:16]. | Observed |
| **Workspaces / working directory** | A filesystem directory per company/agent where the agent operates; created manually and referenced by path during setup [Transcript 2, 17:41–18:33] [Transcript 2, 18:07–18:55]. | Observed |
| **Adapters** | Connector layer to model runtimes: Claude Code, Codex (recommended starters), plus Cursor, Pi, OpenCode, Gemini, "process", and OpenClaw gateway [Transcript 2, 16:52–17:40]. (Transcript says "Open Claude gateway" — treated as OpenClaw.) | Observed |
| **Model/provider selection** | Per-agent choice of provider/model; different agents may use different subscriptions or API keys [Transcript 2, 07:34–08:18]. | Observed |
| **Costs / budgets** | Token stats per run, spend dashboards, monthly budgets, per-agent spending limits (API-key usage) [Transcript 2, 24:59–25:44] [Transcript 2, 07:34–08:18]. | Observed |
| **States** | Kanban: backlog, to-do, in-progress, in-review, blocked, done (plus cancelled) [Transcript 2, 28:33–29:27] [Transcript 2, 36:44–37:34]. | Observed |
| **Imports / exports** | Import company packages via `companies.sh add …` [Transcript 1, 11:44–12:47]; export a company as a shareable package with README and diagram [Transcript 1, 18:41–19:35]. | Observed |
| **Company templates** | Pre-built companies (agents + skills + structure), e.g., G Stack [Transcript 1, 07:57–09:13]. | Observed |

## 4.2 Text-based architecture diagram

```
┌──────────────────────────── PAPERCLIP INSTANCE ───────────────────────────────┐
│  Self-hosted server: local machine | dedicated machine | VPS (Docker)         │
│  Remote access: Tailscale (per founder) [T1 13:18–14:24]                      │
│                                                                               │
│  Web UI ── Dashboard │ Org chart │ Issues (List/Kanban) │ Inbox │ Goals │     │
│            Costs/Budgets │ Runs & token stats │ Routines                       │
│                                                                               │
│  ┌──────────────────────────── COMPANY A ────────────────────────────┐        │
│  │ Mission + Goals (+ subgoals)                                      │        │
│  │                                                                   │        │
│  │   HUMAN "BOARD"                                                   │        │
│  │     │  approves hires, reviews work, unblocks, comments           │        │
│  │     ▼                                                             │        │
│  │   CEO AGENT  ── heartbeat every N sec (default 3600; demo 600)    │        │
│  │     │  triages unassigned issues; delegates; does some work       │        │
│  │     │  proposes new agents ──► Board approval (inbox)             │        │
│  │     ├──► Manager agent(s) ──► Worker agents (org chart, any depth)│        │
│  │     │       each agent = persistent instructions + skills +       │        │
│  │     │       memory + adapter + workspace + (optional) budget      │        │
│  │     │                                                             │        │
│  │   Projects ──► Issues: backlog → to-do → in-progress →            │        │
│  │                  in-review ⇄ blocked → done  (+ comments, labels, │        │
│  │                  attachments, dates, run logs, summaries)         │        │
│  │   Routines: recurring issue generators (e.g., nightly reports)    │        │
│  └───────────────────────────────────────────────────────────────────┘        │
│  ┌──────────────── COMPANY B ────────────────┐  (multiple companies OK)       │
│  └────────────────────────────────────────────┘                               │
│                                                                               │
│  ADAPTER LAYER:  Claude Code | Codex | OpenCode | Gemini | Cursor | Pi |      │
│                  process | OpenClaw gateway                                   │
│       auth: subscription CLI login  OR  direct API keys                       │
│       ▼                                                                       │
│  PROVIDERS: Anthropic, OpenAI, Google, OpenRouter (incl. free/experimental)   │
│                                                                               │
│  HOST FILESYSTEM: per-company working directories (agent workspaces)          │
└───────────────────────────────────────────────────────────────────────────────┘

 companies.sh  ── one-command import of company templates (agents + skills)
 Export        ── company → package (README + diagram) → GitHub / marketplace
```

## 4.3 Coordination mechanics (as described)

- The CEO heartbeat is the only autonomous scheduler mentioned; other agents run when triggered by delegation, assignment, or manual action [Transcript 2, 22:10–23:07].
- Inter-agent coordination happens through the issue system: delegation, comments, state changes, and review queues rather than direct chat [Transcript 2, 37:09–38:06] [Transcript 2, 33:57–34:48].
- The dashboard exposes each agent's live underlying session (e.g., a Claude Code session), including queued/waiting sessions [Transcript 2, 25:44–26:54].

---

# 5. Installation and Deployment

> **Secrets handling:** the tutorial displays password/SSH/code entry on screen. No secrets are reproduced in this report. Treat any credential shown in the source videos as compromised and rotate before reuse. **[QSL]**

## 5.1 Deployment options discussed

| Option | Source guidance | Notes |
|---|---|---|
| **Local (own computer)** | Possible ("I have seen some people doing that") but the presenter "really would recommend against that" [Transcript 2, 03:40–04:28]. | Security exposure (Section 16); machine must run 24/7; single point of loss (fire/theft) if work isn't synced off-box [Transcript 2, 03:40–04:28]. |
| **Dedicated machine** | Acceptable alternative to a VPS; ~$1,000–$1,500 hardware cost cited [Transcript 2, 04:31–05:17]. | Mainly sensible if running local LLMs. |
| **VPS (recommended)** | "As little as $7 per month" with one-click setup [Transcript 2, 04:31–05:17]. | Presenter's default for all his agents. |
| **Docker** | Hostinger deploys Paperclip inside a Docker container — "one of the most secure ways to do it" (presenter's claim) and enables one-click deploy [Transcript 2, 07:56–08:39]. | Docker isolation limits: see Section 16. **[QSL]** |
| **Hostinger one-click** | Select plan (KVM 1/2/3; presenter recommends KVM 2), press deploy, provide a few configuration values [Transcript 2, 04:54–05:41] [Transcript 2, 05:40–06:29]. | Sponsored segment; discount code requires 12+ month plan [Transcript 2, 05:40–06:29]. **[Promotional context]** |
| **Future hosted service** | Founder: "we will be creating a Paperclip cloud-hosted version" [Transcript 1, 13:18–14:24]. | Roadmap claim; not available. **[Claimed]** |

## 5.2 Setup flow as demonstrated (Hostinger path)

1. **Provision:** choose KVM plan, duration, optional daily auto-backup, region [Transcript 2, 05:40–06:29].
2. **Admin credentials:** set admin name (default `admin` suggested), admin email, strong/auto-generated admin password — "when you deploy this Paperclip instance, it will be available over the internet" [Transcript 2, 06:04–06:47].
3. **Optional API keys at deploy time:** Anthropic, OpenAI, Gemini, or Cursor; at least one recommended but can deploy without and authenticate CLIs later [Transcript 2, 06:47–07:35] [Transcript 2, 07:56–08:39].
4. **Access the UI:** Docker manager → Paperclip project → "open" → auth screen; sign in with the admin email/password [Transcript 2, 08:40–09:25] [Transcript 2, 09:02–09:55].
5. **Credential recovery:** admin password is retrievable from the container's **environment variables** in the Docker manager UI [Transcript 2, 09:02–09:55]. **[QSL: env-var secrets in plain UI is a finding — see Section 16.]**
6. **CLI/subscription authentication (if not using API keys):**
   - SSH to the VPS as root (`ssh root@<host>`); change the default random root password first [Transcript 2, 10:19–11:09] [Transcript 2, 11:04–11:53].
   - Enter the container: `docker ps` → copy container ID → `docker exec -it <container_id> /bin/bash` [Transcript 2, 11:52–12:38] [Transcript 2, 12:41–13:30].
   - Claude Code: run `claude`, choose subscription login, open the URL in a browser, authorize, paste the returned code [Transcript 2, 13:58–14:49] [Transcript 2, 14:46–15:39].
   - Codex: `codex login`; on headless/remote machines use `codex login --device-auth` (link + code flow) [Transcript 2, 13:31–14:26].
   - Trust the workspace folder when prompted, then `/exit` [Transcript 2, 15:33–16:23].
7. **Working directory:** create a folder for company work (`mkdir`, `cd`, `pwd` to obtain the full path) and paste it into the company setup [Transcript 2, 17:41–18:33] [Transcript 2, 18:07–18:55].
8. **Local (non-Docker) path:** run the installer/onboarding command, then open the printed port to reach the login screen [Transcript 2, 08:40–09:25]. Founder demo: run the `npx` onboarding command ("paper clip AI onboard" per transcript), which walks through onboarding and installs Paperclip [Transcript 1, 11:14–12:14]. **[Command spelling unverified.]**

## 5.3 Remote access

- **Tailscale** (free plan) on laptop + phone to reach a self-hosted instance remotely; founder reports the mobile web UI "works quite well" [Transcript 1, 13:18–14:24]. **[Claimed, plausible]**

## 5.4 Deployment warnings (consolidated)

- **Internet exposure:** a VPS-deployed UI is reachable from the internet; weak admin passwords are unacceptable [Transcript 2, 06:04–06:47]. **[QSL: additionally restrict by IP/Tailscale where possible.]**
- **Root access:** setup requires root SSH; root password starts random/unknown and must be reset [Transcript 2, 11:04–11:53]. **[QSL: disable root password login + use keys after setup.]**
- **Provider terms:** subscription-based CLI use may violate provider ToS — "some of them allow this, some of them do not" [Transcript 2, 07:11–07:58]; presenter reiterates uncertainty [Transcript 2, 13:58–14:49].
- **Subscription capacity:** cheaper subscriptions "will run out quickly" under agent load; plan API fallback [Transcript 2, 15:12–15:53].
- **Backups:** enable the provider's daily auto-backup or equivalent; agent work on a single machine is losable [Transcript 2, 05:40–06:29] [Transcript 2, 03:40–04:28].
- **Secrets hygiene:** never paste real API keys into issues (the presenter does this with ConvertKit as a demo shortcut [Transcript 2, 27:19–28:10]) — treat as an anti-pattern. **[QSL]**

---

# 6. Model and Adapter Configuration

## 6.1 Adapters named in the sources

- **Recommended starters:** Claude Code and Codex — "the two recommended, just to start for our first agent" [Transcript 2, 16:52–17:40].
- **Additional adapter types shown:** Cursor, Pi, OpenCode, Gemini, "the process", and the OpenClaw gateway (transcript: "Open Claude gateway"), the latter noted as "a little bit more complex in the config" [Transcript 2, 16:52–17:40].
- **OpenClaw interoperability:** OpenClaw agents can connect into Paperclip — "they can bring their OpenClaw into Paperclip" [Transcript 1, 19:37–20:24] [Transcript 2, 07:11–07:58].
- **OpenRouter via OpenCode:** OpenRouter hosts a model leaderboard, including pre-release models tested under anonymous names (founder claims e.g. Grok) and periodically free models (e.g., "step 3.5 flash free"), enabling "essentially free inference" [Transcript 1, 12:16–13:17]. **[Claimed — verify availability/quality before relying on it.]**

## 6.2 Authentication models — provider selection determines auth behavior

| Mode | How it works | Source |
|---|---|---|
| **Direct API keys** | Enter Anthropic/OpenAI/Gemini/Cursor key at deploy or in config; metered spend; supports budgets/spending limits [Transcript 2, 06:47–07:35] [Transcript 2, 07:34–08:18]. | Observed |
| **Subscription-authenticated CLIs** | Log into Claude Code / Codex / Gemini CLI **on the host** (SSH → container shell for Docker) so Paperclip agents ride the subscription [Transcript 2, 10:19–11:09] [Transcript 2, 13:58–14:49]. | Observed; ToS risk flagged in-source |

Consequence: the choice between "API key" and "subscription CLI" changes (a) where authentication happens (deploy-time env vs. interactive host login), (b) cost behavior (metered vs. plan quota), and (c) compliance exposure [Transcript 2, 07:11–07:58] [Transcript 2, 15:12–15:53]. **[Inferred]**

## 6.3 Model-per-role

- Different agents can run on different providers/subscriptions/tokens within one company [Transcript 2, 07:34–08:18].
- Founder: his "main coder" is "either Claude or Codex"; day-to-day agent users report models have "really different personalities and different strengths and weaknesses" [Transcript 1, 00:27–01:23]. **[Opinion — treat as practitioner heuristic, not benchmark data.]**
- **[QSL]** Match model to role critically and record the choice in the hiring packet (Section 10): e.g., strong reasoning models for reviewer/CEO roles; cheaper models for routine triage. Validate per-role before production.

## 6.4 Validation and testing

- The onboarding UI includes an adapter **Test** button: green on success; failure names the cause (e.g., OpenAI key unset; "Codex CLI is installed, but your authentication is not ready") [Transcript 2, 18:54–19:42]. Always test before launching the company; on a self-managed (non-Docker) machine the relevant CLI must be installed and authed or the test fails [Transcript 2, 19:17–19:42].

---

# 7. Company Onboarding Workflow

Complete flow reconstructed from Transcript 2 (setup) and Transcript 1 (founder demo):

1. **Create company** — after first login, the UI prompts to create a company [Transcript 2, 09:54–10:44] [Transcript 2, 15:58–16:50].
2. **Define mission and goal** — specific but concise; the presenter revised his draft ("optimize my content pipeline…") into a more specific version ("grow my YouTube channel… by automating processes, reviewing content ideas, creating scripts, reviewing previous performance") [Transcript 2, 15:58–16:50] [Transcript 2, 16:23–17:20].
3. **Select adapter** — Claude Code or Codex recommended for the first agent; other agents may use other providers later [Transcript 2, 16:52–17:40].
4. **Specify working directory** — a pre-created folder path on the host (or VPS) [Transcript 2, 17:41–18:33] [Transcript 2, 18:07–18:55].
5. **Test connection** — green = proceed; fix auth if the test fails [Transcript 2, 18:54–19:42].
6. **Launch the initial task** — default first task instructs the CEO to hire its first employee; "create and open issue" starts the company [Transcript 2, 19:42–20:26].
7. **Approve the first hire** — the CEO requests a founding engineer; the human approves; the org chart shows CEO → founding engineer [Transcript 2, 23:00–23:48].
8. **Establish projects and agents** — the CEO (with "can create agents" permission) creates projects and requests further hires, or the human instructs the CEO to hire specific roles [Transcript 2, 22:39–23:22] [Transcript 2, 30:56–31:42]. Manual agent creation exists ("plus" button) but the presenter recommends routing hires through the CEO [Transcript 2, 23:00–23:48].
9. **Assign work** — create issues (assigned to the CEO for delegation, to a specific agent, or unassigned for triage) [Transcript 2, 30:33–31:18]; recommended sequence: structure first (agents + integrations), then direct work [Transcript 2, 32:08–32:56].
10. **Monitor results** — dashboard sessions, inbox, issue states, run logs, token/cost stats [Transcript 2, 25:44–26:54] [Transcript 2, 26:29–27:16].

Founder-side equivalent (template path): `npx` onboarding → `companies.sh add …` → confirm agent/skill listing → company imported and ready [Transcript 1, 11:14–12:14] [Transcript 1, 11:44–12:47].

---

# 8. Issue-Based Work Model

**"This isn't a chatbot."** The presenter is explicit: you do not converse with Paperclip; you create issues, and the company executes them [Transcript 2, 20:30–21:22]. The founder agrees the model trades latency for manageability: for a fast single exchange, use Claude directly; Paperclip's value is coordinating many concurrent workstreams [Transcript 1, 14:58–16:01].

## 8.1 Mechanics

- **Creating issues:** title + description; optionally project, priority, labels, file attachments, start/end dates [Transcript 2, 24:13–25:01] [Transcript 2, 24:37–25:21].
- **Assigning:** to a specific agent (runs immediately upon assignment per presenter: "as soon as you do that, the agent will automatically pick it up" — he adds "I believe" for the immediate-trigger behavior) [Transcript 2, 24:13–25:01] [Transcript 2, 30:33–31:18]. **[Partially claimed — verify.]**
- **Unassigned issues:** sit in the task list until the next CEO heartbeat, when the CEO triages and assigns them [Transcript 2, 30:33–31:18].
- **Priorities:** "critical" priority = work "right away" at next pickup [Transcript 2, 24:13–25:01].
- **States / Kanban:** backlog → to-do → in-progress → in-review / blocked → done; cancelled exists [Transcript 2, 28:33–29:27] [Transcript 2, 36:44–37:34]. Manual drag/state change by the human is supported [Transcript 2, 29:24–30:13].
- **Blocked:** agent marks an issue blocked with the reason and what it needs (e.g., no GitHub account connected → "requires manual intervention"); human fixes and returns it to to-do/backlog [Transcript 2, 28:33–29:27] [Transcript 2, 29:24–30:13].
- **Review & approval:** "in review" means waiting on the human; commenting "Approved" on the issue is picked up at the next heartbeat and work proceeds; or move the issue manually (e.g., back to in-progress) [Transcript 2, 29:48–30:30].
- **Comments:** humans and agents comment on issues to steer work mid-run [Transcript 2, 29:48–30:30] [Transcript 2, 31:45–32:30].
- **Summaries/artifacts:** completed issues end with a summary of what was done; runs are inspectable live and after the fact [Transcript 2, 29:24–30:13] [Transcript 2, 31:45–32:30].
- **Immediate triggering vs heartbeat pickup:** assigned issue ≈ immediate; unassigned ≈ next heartbeat [Transcript 2, 30:33–31:18]; manual "run heartbeat" button forces a CEO wake [Transcript 2, 24:13–25:01].

## 8.2 Operating style the sources recommend

- Give **high-level objectives**, not micro-instructions: say "review all of my past YouTube data and generate a report," not "open a PR, run this command" [Transcript 2, 20:57–21:40].
- Expect to spend your time in the issues/Kanban, inbox, and reviews — not in a chat window [Transcript 2, 28:33–29:27].

## 8.3 Gap vs. QSL disposition model **[QSL]**

The sources describe work as ending with a summary and a state change, but show no formal **evidence → review → disposition** record (what was produced, against which criteria, reviewed by whom, approved/returned why). QSL should layer this onto the issue model: every meaningful issue closes with linked artifacts, a verification note, reviewer identity, and an explicit disposition (accepted / returned / escalated).

---

# 9. CEO Operating Model

## 9.1 What the sources recommend

- **Heartbeat-driven operation.** Only the CEO runs a heartbeat; it wakes on the configured interval (default 1 hour; demo 600s), inspects the pipeline, and delegates or works [Transcript 2, 21:45–22:35] [Transcript 2, 22:10–23:07]. A manual "run heartbeat" button exists for on-demand wakes [Transcript 2, 24:13–25:01].
- **Delegation-first.** Humans assign issues to the CEO; the CEO routes them to the org [Transcript 2, 20:30–21:22] [Transcript 2, 21:18–22:12].
- **Proactivity must be prompted.** Without an explicit operating protocol, the CEO "just says, 'Hey, I don't have anything to do.' … it's more reactive" [Transcript 2, 34:23–35:17]. The presenter's fix is a detailed CEO system prompt + strict per-heartbeat protocol:
  - "check the status of every employee";
  - "assign work to every idle agent" ("super important, so it's actually proactive");
  - "review all the completed work";
  - "draft and queue the emails";
  - "review metrics and adjust the strategy";
  - phased heartbeat protocol: "Phase one, status check. Phase two, review the completed work. Phase three…" [Transcript 2, 34:50–35:34] [Transcript 2, 35:37–36:21].
  - He generated these prompts by asking Claude to write them from his intent [Transcript 2, 34:23–35:17]. "When you give these agents repeatable workflows, this is almost like a skill file… it starts to become a lot more useful" [Transcript 2, 35:37–36:21].
- **Hiring with Board approval.** CEO requests hires; human approves (e.g., founding engineer, then batches of specialists) [Transcript 2, 23:00–23:48] [Transcript 2, 32:53–33:35]. Presenter recommends keeping the CEO's "can create agents" permission enabled [Transcript 2, 22:39–23:22].
- **Maintaining momentum.** Founder demo: prompt the CEO to "follow up on all the work and like keep people moving" — the CEO then walks the issue list verifying completion [Transcript 1, 10:10–11:19]. Founder also notes Paperclip is "still working on making sure that Paperclip keeps your agents working"; unreleased "maximizer mode" is meant to "ensure that your agents never stop working" [Transcript 1, 09:04–10:17].
- **Recurring work.** Routines (Section 13) are the mechanism for scheduled recurring output [Transcript 1, 16:02–17:18].

## 9.2 QSL Governance Interpretation **[QSL]**

QSL adopts the CEO-heartbeat pattern but re-scopes its authority:

- The CEO may **detect capability gaps and propose hires**; the human **Board approves all organizational expansion**. Paperclip's approval-request mechanic supports this natively [Transcript 2, 23:00–23:48] — QSL makes the gate non-optional rather than a toggleable permission.
- Every hire is defined by an **approved hiring packet** (Section 10) specifying role, authority, prohibitions, tools, budget, and review requirements. The CEO does **not** receive blanket permission to invent agents or invent work.
- Heartbeats should **review evidence, states, approvals, risks, and budgets** — verify that in-progress work is on-objective, completed work has evidence and correct disposition, blocked items have escalation paths, and spend is within budget — rather than "manufacture busywork" to keep agents busy. QSL deliberately rejects the "assign work to every idle agent" default [Transcript 2, 34:50–35:34] and the "never stop working" maximizer framing [Transcript 1, 09:04–10:17]: **an idle agent with no authorized work is a correct state, not a defect.**
- **Proactive evidence gathering** (status checks, drift detection, risk flags, budget reports) is preferable to uncontrolled task creation. A QSL CEO heartbeat ends in one of: `no-action-required`, `recommendation-for-Board`, or `execution-of-previously-authorized-work`.

---

# 10. Agent Creation and Hiring

## 10.1 What the sources show

- **CEO-created agents with Board approval.** The default path: the CEO decides it needs roles (e.g., founding engineer, then specialists like sponsorship manager, thumbnail designer) and files hire requests the human approves one by one [Transcript 2, 00:50–01:44] [Transcript 2, 23:00–23:48] [Transcript 2, 32:53–33:35].
- **Human-directed hiring via the CEO.** Founder: create an issue telling the CEO to "hire a video writer and give him the Remotion skill" — the CEO hires and equips the agent [Transcript 1, 03:20–04:35] [Transcript 1, 04:31–05:23].
- **Manual creation.** A "+" button lets the human configure an agent directly, though the presenter recommends going through the CEO [Transcript 2, 23:00–23:48].
- **Hierarchies.** Agents report to agents (founding engineer → CEO); "agents can then hire their own agents and you can have much more complex org charts" [Transcript 2, 01:17–02:03]; no hard limit on agent count or depth, but the presenter judges ~7–15 agents practical and "hard to monitor" beyond that [Transcript 2, 33:34–34:21].
- **Specialization and instruction templates.** Each agent gets a role-specific system prompt: researcher ("this is what you do… this is the output format, these are the rules"), founding engineer ("commit stuff to git, don't push to main, make sure you make a pull request"), reviewer, etc. — "a slimmer system prompt" than the CEO's [Transcript 2, 35:37–36:21].
- **Skills at hire time.** Skills are attached during hiring (video writer + Remotion; data analyst + Excel/XLS) [Transcript 1, 04:31–05:23] [Transcript 1, 15:30–16:34].

## 10.2 Reusable QSL hiring-packet template **[QSL]**

Every proposed agent — whether the CEO proposes it or a human does — is approved against this packet before creation:

```markdown
# Agent Hiring Packet

- Agent name / handle:
- Proposed by: [CEO | human]            Date:
- Company / project:

## Role
- Title:
- Reports to:                           (explicit single manager)
- Direct reports:                       (default: none)

## Purpose
- Why this capability is needed (capability gap detected):
- Objectives this role serves (link goals/issues):

## Mission
- One-paragraph standing mission for this agent:

## Authority (explicit, bounded, revocable)
- May do:                               (enumerated actions, e.g., "open PRs to repo X")
- May NOT do without new approval:      (e.g., merge, spend, publish, message externals)
- Prohibited actions (hard):            (e.g., no credential handling, no main-branch commits)
- Autonomy level: [read-only | sandbox | bounded-execute | supervised-execute]

## Tools & Access
- Adapter / model:
- Working directory / repos:            (least privilege; read-only where possible)
- External accounts/connectors:         (dedicated service accounts only)
- Secrets needed:                       (via secrets store; never in issues/prompts)

## Skills
- Attached skills + version + provenance reviewed by:

## Inputs
- What this agent consumes (issues, data sources, artifacts):

## Outputs
- Expected artifacts and formats (reports, PRs, analyses):

## Completion states & evidence
- Definition of done; evidence required with each completion:

## Budget
- Token/$ budget per [day|week|month]; heartbeat/trigger limits:

## Escalation conditions
- When to block and escalate to manager/CEO/Board (e.g., ambiguity, risk, cost overrun):

## Review requirements
- Who reviews outputs; review cadence; disposition options (accept/return/escalate):

## Approval
- Board approver:                       Date:
- Review-by date (authority re-confirmation):
```

---

# 11. Skills

## 11.1 What skills are (per sources)

Reusable capability packages that "teach your agents different types of abilities" — founder's examples: web design best practices, making videos with Remotion, generating AI images [Transcript 1, 02:45–03:56]. "It gives your agent superpowers" **[Promotional phrasing]** [Transcript 1, 02:45–03:56]. skills.sh is named as the external library, attributed by the founder to "the guys at Vercel" [Transcript 1, 01:49–02:41] [Transcript 1, 02:45–03:56]. **[Attribution unverified.]**

## 11.2 Examples appearing in the transcripts

| Skill | Use shown/claimed | Source |
|---|---|---|
| **Remotion** (video) | Video writer agent scripted and produced a 60-second animated launch video for companies.sh (plan → messaging hierarchy → shot list → render), using the existing Paperclip brand guide | [Transcript 1, 03:20–04:35] |
| **Excel/XLS + Google Sheets** | Data analyst hired with spreadsheet skills for data work | [Transcript 1, 04:31–05:23] [Transcript 1, 15:30–16:34] |
| **Humanizer** | Improves AI writing quality ("write a little bit better") | [Transcript 1, 05:31–06:30] |
| **Memory (PARA method)** | Tiago Forte's PARA method; attributed to Nat Eliason; "gives your agents memory over a long period of time" | [Transcript 1, 05:31–06:30] |
| **G Stack set** (Garry Tan / YC) | Office-hours Q&A, planning, engineering planning, design consultations, QA-engineer review pattern — YC accelerator practices as invocable skills | [Transcript 1, 06:30–07:33] [Transcript 1, 07:01–08:04] [Transcript 1, 07:57–09:13] |
| **Web design best practices / AI images** | Named as skill examples | [Transcript 1, 02:45–03:56] |

## 11.3 Attachment model: universal vs. specialized

- Skills can be **universal** (available to every agent in the company — e.g., humanizer, memory in the founder's org) or **role-specific** (attached at hire) [Transcript 1, 06:00–06:59] [Transcript 1, 04:31–05:23].
- **Context degradation warning (founder):** "one of the downsides of models of today is that if you load too many skills in, they start to lose track and your performance degrades. You really only want to enable the skills for the agents that are actually going to use them" [Transcript 1, 06:00–06:59]. **[Claimed, consistent with known context-window behavior — treat as an operating rule.]**

## 11.4 Skill selection and maintenance

- Prefer few, high-relevance skills per role; audit universal skills periodically. **[QSL/Inferred from Transcript 1, 06:00–06:59]**
- Skill ideas/methodologies circulate as repos (e.g., G Stack); companies.sh bundles skills with agents as installable companies [Transcript 1, 07:57–09:13].

## 11.5 Security and provenance risks **[QSL]**

Third-party skills are executable prompt/code supply chain:

- A malicious or sloppy skill can instruct agents to exfiltrate data, weaken review steps, or override role instructions — amplified because skills propagate through templates (companies.sh) to many agents at once.
- QSL rules: install skills only from reviewed sources; pin versions; read the full skill content before approval (it is prompt text — treat it as code); record provenance in the hiring packet; re-review on update; sandbox first run; never let a skill expand an agent's authority beyond its packet.

---

# 12. Memory

## 12.1 Why agents need identity and continuity

Founder's core diagnosis: "your agents wake up every time you hit them… insanely capable, but they have no idea who they are or what they're supposed to be working on or what they worked on yesterday" [Transcript 1, 01:49–02:41]. Paperclip's answer is layered persistence:

| Layer | Mechanism per sources | Source |
|---|---|---|
| **Identity/role (agent memory)** | Persistent per-agent instructions/system prompts ("my UX designer… my video writer") | [Transcript 1, 01:49–02:41] [Transcript 2, 35:37–36:21] |
| **Long-term memory skill** | PARA-method memory skill (attributed to Nat Eliason) "gives your agents memory over a long period of time" | [Transcript 1, 05:31–06:30] |
| **Organizational memory** | Tracked conversations, issues, comments, run logs — the company record | [Transcript 1, 01:18–02:21] |
| **Project memory** | Projects group issues/context per workstream | [Transcript 2, 23:52–24:34] |

The founder's contrast case: his OpenClaw setup "started to fall apart and I couldn't understand what it was doing or what it was remembering or forgetting" — motivating human-legible memory in Paperclip [Transcript 1, 20:00–20:49].

## 12.2 What memory should and should not retain **[QSL]**

- **Retain:** role charter; durable decisions and their rationale; approved procedures; pointers to authoritative artifacts (repos, dashboards, docs); lessons explicitly accepted in review.
- **Do not retain:** secrets/credentials; personal data beyond need; superseded instructions (version them out); unverified inferences promoted to "facts"; raw transcripts of every run (that's the log system, not memory).

## 12.3 Contamination, staleness, and privacy risks **[QSL]**

- **Contamination:** a wrong conclusion written to memory is re-read as fact by every future wake — memory needs the same review discipline as code.
- **Staleness:** goals and constraints change; stale memory silently steers agents off-objective. Give memories owners and review-by dates.
- **Privacy:** agent memory on a VPS may hold client data; honor client boundaries and retention limits (Section 16).

## 12.4 Memory vs. authoritative evidence **[QSL]**

Memory is a **pointer and context system**, not a source of truth. For QSL doctrine: when memory and an authoritative artifact disagree (repo state, approved packet, signed report), the artifact wins; memory must be corrected. Completed-work claims require linked evidence in the issue — an agent "remembering" it did something is not evidence.

---

# 13. Routines and Recurring Work

## 13.1 What the sources show

- **Definition:** "routines is where you have work that needs to happen on a recurring basis" [Transcript 1, 16:02–17:18].
- **Bookmark-analysis example (founder):** a routine instructing his "strategic ops" agent to sync his Twitter/X bookmarks and write a strategy report for Paperclip against provided guidelines; each morning he reviews the generated report (e.g., an Anthropic tweet about a new heartbeat pattern; telemetry approaches for tracking agents) [Transcript 1, 16:02–17:18] [Transcript 1, 16:39–17:45].
- **Overnight operation:** "when I show up every morning, my agents have actually started to do some legwork from things that I was thinking about yesterday… have my agents work for me while I'm asleep" [Transcript 1, 17:13–18:07]. The tutorial presenter echoes this: "I've just been sleeping. I wake up and all this work is done" [Transcript 2, 02:52–03:39].
- **Monitoring/continuous operation:** heartbeat + routines + inbox produce a system that runs unattended and surfaces exceptions [Transcript 2, 21:45–22:35] [Transcript 2, 26:29–27:16].

## 13.2 When routines are useful **[Inferred/QSL]**

- Scheduled evidence gathering and digest reports (analytics summaries, inbox triage, news/competitor scans).
- Periodic hygiene checks (budget burn, stuck issues, stale reviews).
- Recurring deliverables with stable format (weekly strategy report).

## 13.3 How routines waste tokens or create noise **[QSL]**

- Every routine run costs tokens; a routine without a consumer is pure burn (see Section 15).
- Overnight autonomy multiplies the blast radius of a bad instruction — a mis-specified routine can generate confidently wrong "strategy" every night.
- Noise risk: routine outputs landing in the inbox train the operator to ignore the inbox.

**QSL-required stopping and notification conditions for any routine:** (1) stop and notify on repeated failure, budget breach, or missing input data; (2) produce nothing when there is nothing new ("no-change" runs must be near-zero cost); (3) every routine has an owner, a review-by date, and an explicit output consumer; (4) routines never create new *unauthorized* work — they may only gather, summarize, and recommend.

---

# 14. Review and Feedback Patterns

## 14.1 Patterns in the sources

- **Agents checking each other (founder):** "a lot of the best companies have relatively sophisticated patterns of agents checking each other's work, agents giving work back to one another" — cited as the motivation for shareable company patterns [Transcript 1, 07:57–09:13]. G Stack's QA-engineer role (have a QA engineer review created work) is included as a template role [Transcript 1, 07:57–09:13].
- **Researcher–writer–editor–reviewer loop (tutorial):** "having like a newsletter researcher, a newsletter drafter, a newsletter editor, and then a newsletter reviewer… they cycle the information to each other… these agents are checking their own work, and then finally it gets submitted to the CEO and then me for final review before we actually go live" [Transcript 2, 33:57–34:48].
- **Escalation and queues:** blocked and in-review states concentrate human attention where it is needed [Transcript 2, 28:33–29:27]; inbox surfaces review/hire items [Transcript 2, 26:29–27:16].
- **Returning work for revision:** comments on issues steer rework; issues can be moved back to in-progress [Transcript 2, 29:48–30:30].
- **Final human review before external effect:** presenter's newsletter loop ends with him before anything "goes live" [Transcript 2, 33:57–34:48]; GitHub access is PR-only [Transcript 2, 28:08–28:58].

## 14.2 Value and limits **[QSL]**

Feedback loops are genuinely valuable: they catch errors, enforce format/quality standards, and create natural evidence trails. **But additional agents do not automatically guarantee correctness:** correlated models make correlated mistakes; a reviewer agent sharing the writer's blind spots gives false confidence; and each review layer multiplies cost and latency. QSL rules: (1) reviewer agents must review *against explicit criteria* (checklists, tests, style guides), not vibes; (2) external effects (publishes, merges, spends, messages) always terminate at an accountable human; (3) measure whether review layers actually catch defects — remove layers that never do.

---

# 15. Costs, Budgets, and Resource Control

## 15.1 What the sources show

- **Token and API cost tracking:** per-run input-token stats and spend dashboards when running on metered APIs [Transcript 2, 24:59–25:44] [Transcript 2, 02:04–02:51]; per-issue cost visible on runs [Transcript 2, 31:45–32:30].
- **Subscriptions vs. metered APIs:** two funding modes (Section 6.2). With subscriptions, the presenter skips budgets ("you don't really need to do that"); with API keys, "you probably want to set a monthly budget" and per-agent spending limits exist [Transcript 2, 24:59–25:44] [Transcript 2, 07:34–08:18]. Cheap subscriptions exhaust quickly under agent load [Transcript 2, 15:12–15:53].
- **Heartbeat frequency ↔ cost:** shortening the CEO heartbeat from 1 hour to 600s increases activity *and* spend — "if you don't want to use a lot of money, then you can… change… how much it runs" [Transcript 2, 22:10–23:07].
- **Parallel sessions:** the dashboard shows multiple concurrent agent sessions; parallelism multiplies concurrent spend [Transcript 2, 25:44–26:54].
- **Retries / corrective wakes / unnecessary activity:** the founder admits agents currently stop unexpectedly and need nudges ("follow up on all the work… keep people moving") [Transcript 1, 10:10–11:19]; unreleased "maximizer mode" aims at continuous work [Transcript 1, 09:04–10:17]. Each corrective wake costs tokens. **[Inferred]**
- **Free/experimental inference:** OpenRouter free-tier and anonymous pre-release models floated as a cost saver [Transcript 1, 12:16–13:17]. **[Claimed — quality/privacy trade-offs unevaluated.]**

## 15.2 QSL conservative defaults **[QSL]**

1. Start every company **read-only/sandboxed** with **hard per-agent and per-company budgets**; budgets are part of the hiring packet (Section 10).
2. Default CEO heartbeat: **hourly or longer**; shorten only with evidence that latency matters more than cost.
3. **No idle-agent busyness rule:** heartbeats verify state and report; they do not invent work (Section 9.2).
4. Cap **parallel sessions** per company; serialize unless throughput is demonstrably needed.
5. **Retry discipline:** max retries per issue, then block + escalate — never loop autonomously.
6. Use **cheaper auxiliary models** for triage/summarization where quality allows; reserve premium models for review/CEO judgment; record model choice per role.
7. **Weekly operational cost review**: spend by agent/company vs. value of dispositions produced; kill or fix routines that produce unreviewed output.
8. Treat "free inference" as experimental only: no client data, no production dependence.

---

# 16. Security and Isolation

## 16.1 Risks stated in the sources

The tutorial presenter's warning against personal-machine deployment [Transcript 2, 03:40–04:28]:

- **Local file access / home-network exposure:** "fully autonomous AI agents running on your own device with access to all of your files, your computer, your home network."
- **Root-level control:** "full root control of your computer and can effectively do anything that they want."
- **Speculative misuse examples:** "they can go rogue, they can go to the internet, they can buy a course, they can access your credit cards" — **[Speculative illustrations, not observed events.]**
- **Availability risk:** device must run 24/7; local loss (fire/theft) destroys unsynced work.

Observed security-relevant mechanics: internet-reachable admin UI with password auth [Transcript 2, 06:04–06:47]; admin password stored in container **environment variables viewable in the Docker manager UI** [Transcript 2, 09:02–09:55]; **root SSH** setup [Transcript 2, 10:19–11:09]; Docker-container deployment [Transcript 2, 07:56–08:39]; API keys entered at deploy or pasted into issues (ConvertKit demo) [Transcript 2, 06:47–07:35] [Transcript 2, 27:19–28:10]; agent GitHub account with **PR-only** repo access ("can make PRs, but it can't commit to the main branch") [Transcript 2, 28:08–28:58]; agent instruction "don't push to main, make sure you make a pull request" [Transcript 2, 35:37–36:21]; Tailscale-based remote access [Transcript 1, 13:18–14:24].

## 16.2 Capability vs. speculation

- **Described/observed:** agents execute real shell-level work inside their environment; adapters run coding CLIs; workspaces are real directories; integrations (GitHub, ConvertKit) use real credentials; the UI is internet-facing.
- **Speculative:** rogue purchases, credit-card use — presenter hypotheticals illustrating why isolation matters, not demonstrated behavior [Transcript 2, 03:40–04:28].
- **Founder's related motivation (observed claim):** loss of oversight of agent behavior drove Paperclip's creation [Transcript 1, 01:18–02:21] [Transcript 1, 20:00–20:49].

## 16.3 Isolation and control layers (QSL consolidation) **[QSL]**

| Layer | Guidance |
|---|---|
| **Machine isolation** | VPS or dedicated machine; never a personal daily-driver [Transcript 2, 03:40–04:28]. Separate host per client. |
| **Container isolation** | Docker helps but is **not a security boundary** against a determined workload: container runs as root-accessible via `docker exec`, shares the host kernel, and its env vars (including the admin password) are UI-visible [Transcript 2, 09:02–09:55] [Transcript 2, 11:52–12:38]. Harden: non-root containers, no `--privileged`, restricted volume mounts, no host Docker socket. |
| **Network isolation** | Prefer Tailscale/private access over public UI exposure [Transcript 1, 13:18–14:24]; if public, enforce strong auth + TLS + IP allowlisting; egress filtering on the agent network. |
| **Identity & privilege** | Dedicated service accounts per integration (presenter created a separate GitHub account for the agent [Transcript 2, 27:19–28:10] — good pattern); least privilege scopes; read-only first. |
| **Repo safety** | Branch protection + PR-only agent access; human merge [Transcript 2, 28:08–28:58] [Transcript 2, 35:37–36:21]. |
| **Secrets management** | Never in issues/comments/prompts (ConvertKit demo is an anti-pattern [Transcript 2, 27:19–28:10]); use a secrets store; rotate anything ever exposed to a transcript, issue, or screen share. |
| **Root & SSH** | Replace password SSH with keys; disable root login after setup; the root reset shown is setup-only [Transcript 2, 11:04–11:53]. |
| **Backups & logs** | Daily backups (offered at deploy [Transcript 2, 05:40–06:29]); retain run logs/issues as audit trail [Transcript 1, 01:18–02:21]; ship logs off-box. |
| **Revocation** | Agent authority must be revocable: kill switch per agent (disable adapter auth, revoke tokens, stop container), per-company pause, and credential rotation runbook. |
| **Client boundaries** | Separate instance/host, accounts, repos, and budgets per client; no shared memory across clients; contractual data-handling terms. |
| **Threat modeling** | Assume prompt injection via any ingested content (bookmarks, emails, web pages) [Transcript 1, 16:02–17:18 shows ingestion routines]; assume template/skill supply-chain attacks (Sections 11.5, 17.3); model agent compromise as "insider with keys." |

---

# 17. companies.sh and Shareable Companies

## 17.1 What the sources claim and show

- **Positioning:** "companies.sh, which is like the app store for agentic companies" — launched the morning of the interview [Transcript 1, 00:00–00:53] [Transcript 1, 02:45–03:56]. **[Promotional framing.]**
- **One-command install:** `companies.sh add paperclipai/companies/gstack` (transcript rendering approximate); the installer asks which service/instance to import into, lists how many agents and skills the company includes, and asks for confirmation [Transcript 1, 11:44–12:47].
- **What a template includes:** agents with their roles plus all their skills pre-installed [Transcript 1, 07:57–09:13].
- **G Stack example:** Garry Tan's (YC president) skill set — office hours, planning, engineering planning, design consultation, QA-engineer review — packaged as a one-shot company [Transcript 1, 06:30–07:33] [Transcript 1, 07:01–08:04] [Transcript 1, 07:33–08:22]. Demoed live: installed, then an "office hours" issue produced structured startup advice (forcing questions, demand reality, "services don't scale") [Transcript 1, 14:26–15:31] [Transcript 1, 17:13–18:07].
- **Standardization ambition:** deliberately not on a Paperclip domain — "this is a standard that we hope for other companies to use to make shareable companies" [Transcript 1, 07:57–09:13]. Portability to other orchestration platforms is an aspiration, not demonstrated. **[Claimed.]**
- **Export workflow:** "export company" produces a packaged company "with a README and diagram and all these things," submittable to GitHub or to the Paperclip team [Transcript 1, 18:41–19:35].
- **Marketplace ideas:** host suggests selling company structures; founder floats a "claw hub"/"clip mart" or teaming with Nat Eliason's existing "Claw Mart" for buying/selling individual agents [Transcript 1, 19:08–20:06]. **[Speculative/roadmap.]**
- **Rationale:** capture and share effective multi-agent *patterns* ("agents checking each other's work… no place where you can actually share those patterns") [Transcript 1, 07:57–09:13].

## 17.2 Value

Reusable organizational patterns could compress weeks of prompt/role design into minutes and give newcomers working governance-by-default structures — **if** templates are trustworthy. **[Inferred]**

## 17.3 Supply-chain and trust risks **[QSL]**

- A company template is a bundle of **instructions, skills, and implied permissions** — i.e., executable influence over future agent behavior. A malicious template can embed data exfiltration, backdoor roles ("QA agent" that always approves), or hidden external calls.
- Risks: unknown provenance; skill nesting (skills pulling other skills); permission creep at import; stale/insecure defaults; typo-squatted template names; marketplace incentives favoring flash over safety.
- **QSL import rules:** import only into a **sandbox instance**; full human read of every agent instruction and skill before enabling; strip network/write permissions to least privilege; pin and hash versions; run with read-only access first; require Board sign-off recorded in a review artifact before any production use. Treat "one-command company install" as "one-command **audit obligation**" (Section 23 checklist).

---

# 18. Demonstrated Use Cases

Classification per case: **[D]emonstrated on screen / [C]laimed by speaker / [P]roposed only.**

| # | Use case | Status | Detail & source |
|---|---|---|---|
| 1 | **Newsletter operations** | D (partial) | Live company with CEO + founding engineer + newsletter researcher/reviewer/writer; agents analyzed past newsletters and produced improvement reports [Transcript 2, 00:50–01:44] [Transcript 2, 02:28–03:17]. Goal: grow subscriptions/revenue, automate newsletter creation [Transcript 2, 01:40–02:28]. Output quality not independently verified. |
| 2 | **Content analysis** | D | Newsletter performance analysis reports [Transcript 2, 02:28–03:17]; YouTube performance review proposed as goal [Transcript 2, 16:23–17:20]. |
| 3 | **Website optimization** | C | "It already pushed a PR here with a bunch of changes last night" to the TechWithTim site [Transcript 2, 02:28–03:17]. PR shown briefly; quality unverified. |
| 4 | **Pull requests / GitHub workflows** | D | Dedicated agent GitHub account, repo creation, PR flow with main-branch protection [Transcript 2, 27:19–28:10] [Transcript 2, 28:08–28:58]. |
| 5 | **Newsletter platform development** | C | Agents "created their own new repo" building a newsletter platform with interactive dashboard [Transcript 2, 02:28–03:17]. Early-stage; completeness unknown. |
| 6 | **Video creation** | D | Remotion-skill video writer: plan → script → animated 60s launch video using brand guide [Transcript 1, 03:20–04:35] [Transcript 1, 04:31–05:23]. |
| 7 | **Spreadsheets / data analysis** | P→D (hire only) | Data analyst hired with XLS/Google Sheets skill during demo; no data output shown [Transcript 1, 04:31–05:23] [Transcript 1, 15:30–16:34]. |
| 8 | **YouTube growth** | P | Mission/goal configured; hires made (thumbnail designer, sponsorship manager); no outcomes yet [Transcript 2, 16:23–17:20] [Transcript 2, 30:56–31:42] [Transcript 2, 33:14–33:55]. |
| 9 | **Analytics integration** | P | Subgoal: connect YouTube analytics with provided credentials [Transcript 2, 27:19–28:10]. |
| 10 | **ConvertKit integration** | C | "I had it connect to my ConvertKit" via API key in an issue [Transcript 2, 27:19–28:10]. Resulting behavior not shown. |
| 11 | **Game development** | D (early) | "Don Cheetos" game studio org (creative/narrative/art directors); Godot bullet-hell project with folder structure created; CEO checked issue completion [Transcript 1, 09:04–10:17] [Transcript 1, 10:10–11:19]. Playable game not shown. |
| 12 | **Strategy reports** | D | Nightly bookmark-analysis routine producing morning strategy reports [Transcript 1, 16:02–17:18] [Transcript 1, 16:39–17:45]. |
| 13 | **Startup office hours** | D | G Stack office-hours skill evaluated the "Paperclip install service" idea and returned structured skepticism [Transcript 1, 14:26–15:31] [Transcript 1, 17:13–18:07]. |
| 14 | **Install/customization services** | P (and tested) | Proposed as a business idea, citing the OpenClaw installer economy [Transcript 1, 14:26–15:31]; the office-hours skill itself flagged "services don't scale" [Transcript 1, 17:13–18:07]. |
| 15 | **Software engineering organization** | D (self-hosting) | Paperclip runs its own company: CEO, CTO, coders [Transcript 1, 00:27–01:23]. Depth of actual engineering output not shown. |

---

# 19. Limitations and Unresolved Questions

From the sources (labeled) plus QSL analysis:

1. **Immature software.** "Paperclip is 3 weeks old today" [Transcript 1, 09:04–10:17]; tutorial presenter: "brand new tech… definitely not 100% there yet" [Transcript 2, 33:14–33:55] [Transcript 2, 38:00–38:49].
2. **Presenters' limited experience.** ~48 hours for the tutorial [Transcript 2, 00:00–00:51]; founder demos are curated.
3. **Manual intervention still required.** Connecting GitHub/ConvertKit/APIs, unblocking issues, approving hires: "There's some stuff that you do manually need to do, like they can't do everything on their own" [Transcript 2, 32:08–32:56] [Transcript 2, 28:33–29:27].
4. **Agents stop unexpectedly.** Keeping agents working is an unsolved problem; "maximizer mode" is announced but not released [Transcript 1, 09:04–10:17]; CEO needs prompting to "keep people moving" [Transcript 1, 10:10–11:19].
5. **Excessive-autonomy risk.** Default-recommended "can create agents" + short heartbeats + proactive prompts = rapid org growth and spend without proportional value [Transcript 2, 22:39–23:22] [Transcript 2, 34:50–35:34]. **[QSL concern.]**
6. **Monitoring burden.** Even ~10 agents are "hard to monitor" [Transcript 2, 33:34–34:21]; overnight operation shifts work to morning review [Transcript 1, 17:13–18:07].
7. **Cost uncertainty.** Heartbeat frequency, parallelism, retries, and review loops multiply spend; no source quantifies a monthly figure [Transcript 2, 22:10–23:07] [Transcript 2, 25:44–26:54].
8. **Model failures and correctness limits.** No source measures output correctness; review loops are asserted, not validated [Transcript 2, 33:57–34:48]. Hallucination risk is unaddressed in both transcripts.
9. **Weak task disposition.** Issues end with summaries, but there's no demonstrated acceptance criteria, evidence linking, or rejection telemetry (Section 8.3). **[QSL observation.]**
10. **Retries and loops.** No demonstrated cap on retry behavior for stuck work; blocked states rely on humans [Transcript 2, 28:33–29:27].
11. **Security uncertainty.** Docker called "one of the most secure ways" by the presenter without evidence [Transcript 2, 07:56–08:39]; env-var secrets, root setup, internet-facing UI (Section 16).
12. **Provider terms.** Subscription-CLI orchestration may violate ToS; presenter unsure [Transcript 2, 07:11–07:58] [Transcript 2, 13:58–14:49].
13. **Template trust.** companies.sh imports executable org structures; no provenance/review mechanism shown [Transcript 1, 11:44–12:47].
14. **Context degradation.** Too many skills degrade performance [Transcript 1, 06:00–06:59]; long-horizon memory quality unproven [Transcript 1, 05:31–06:30].
15. **Evaluation difficulty.** No benchmarks; "meaningful outputs" is the presenter's judgment after 2 days [Transcript 2, 32:32–33:13].
16. **Organizational complexity.** Deep hierarchies are possible but unbounded complexity has no demonstrated management tooling beyond the org chart [Transcript 2, 33:34–34:21].
17. **Unclear accountability.** When an agent company takes a harmful action, responsibility allocation (operator? CEO agent? template author?) is unaddressed in the sources. **[QSL concern.]**
18. **No evidence "zero-human" businesses are dependable.** Both demos include continuous human approval, unblocking, and steering; the zero-human framing is aspirational [Transcript 1, 00:00–00:53] [Transcript 2, 38:00–38:49].

---

# 20. QSL's Deliberate Divergence

| Upstream/Presenter Emphasis | QSL Direction |
|---|---|
| Zero-human business [Transcript 1, 00:00–00:53] | Human-governed operations |
| Maximum activity ("never stop working" maximizer mode) [Transcript 1, 09:04–10:17] | Purposeful bounded execution |
| CEO creates work ("assign work to every idle agent") [Transcript 2, 34:50–35:34] | CEO advances approved objectives |
| Broad agent creation ("hire seven new employees"; "can create agents" recommended on) [Transcript 2, 30:56–31:42] [Transcript 2, 22:39–23:22] | Board-approved capability expansion |
| Persistent autonomy | Revocable autonomy |
| Output production | Evidence-backed state transition |
| Agent self-review [Transcript 2, 33:57–34:48] | Agent review plus accountable human review |
| Easy template installation (one-command companies) [Transcript 1, 11:44–12:47] | Verified, sandboxed, least-privilege import |
| "Never stop working" [Transcript 1, 09:04–10:17] | Stop when no authorized work remains |

## QSL operating principles (full statement)

1. **Humans retain governing authority.** The Board (human) owns mission, goals, hiring, budgets, and external effects. Agents advise and execute within granted bounds.
2. **Agent authority is explicit, bounded, and revocable.** Every agent operates under an approved hiring packet (Section 10) enumerating permitted actions, prohibited actions, tools, and budget. Revocation is a tested procedure, not a hope.
3. **Organizational expansion requires human approval.** A CEO may *propose* hires with justification; it may not create agents unilaterally. Paperclip's approval mechanic is kept on and treated as mandatory [Transcript 2, 23:00–23:48].
4. **Read-only and sandboxed access first.** New agents, connectors, skills, and templates start with the minimum access needed to demonstrate value; write access is earned per integration.
5. **Meaningful work requires evidence, review, and explicit disposition.** An issue is not "done" because an agent says so; it closes with artifacts, verification, reviewer identity, and an accept/return/escalate decision.
6. **Autonomy is enabled deliberately, for approved bounded objectives.** Heartbeats verify and recommend; they do not manufacture activity. Idle is acceptable; unauthorized busyness is a defect.
7. **The goal is trustworthy operations, not maximum autonomous activity.** Success is measured in verified, reviewed outcomes per dollar — not agent count, run count, or hours of unattended operation.

---

# 21. Revenue and Service Opportunities

Source signals: the founder demoed the idea "install Paperclip for people," citing the existing OpenClaw installer economy [Transcript 1, 14:26–15:31]; the G Stack office-hours skill then stress-tested it — "Who's paying for this today?… services don't scale" [Transcript 1, 17:13–18:07]. QSL should therefore bias toward **productized, governance-differentiated packages** rather than hourly installation labor. Ratings are QSL judgment (Low/Med/High), not source claims. **[QSL]**

| Opportunity | Time to first revenue | Trust required | Delivery difficulty | Recurring potential | Security risk | Scalability | Verdict |
|---|---|---|---|---|---|---|---|
| Paperclip installation (VPS/Docker/auth) | Fast (days) | Low-Med | Low-Med (tutorial-length setup) | Low | Med (root, keys) | Low | Entry-point service; bundle, don't sell alone |
| Secure configuration hardening | Fast | Med | Med | Low-Med | High (you touch their secrets) | Low-Med | Strong attach to installation |
| Company-template customization | Fast-Med | Med | Med | Med | Med | Med | Core offer; differentiate on governed templates |
| Governance setup (packets, approvals, budgets, CEO protocol) | Fast-Med | High | Med | Med (reviews) | Low-Med | Med | QSL's differentiator; lead with this |
| Skills evaluation & curation | Med | Med-High | Med | Med (re-review on updates) | Med | Med | Pairs with template work |
| Model/provider configuration & ToS check | Fast | Med | Low-Med | Low | Low | Med | Good add-on; ToS ambiguity creates demand [Transcript 2, 07:11–07:58] |
| Cost-control setup (budgets, heartbeats, model tiers) | Fast | Med | Low-Med | Med (monthly cost reviews) | Low | Med-High | Easy recurring component |
| Workflow design (issue model, review loops, routines) | Med | High | Med-High | Med | Low | Med | High-value consulting |
| Client sandbox demonstrations | Fast | Low | Low-Med | Low | Low (if properly sandboxed) | Med | Marketing engine for everything above |
| Security assessment of agent environments | Med | High | High | Med-High (periodic) | Med | Med | Strong differentiator; needs real expertise |
| Managed monitoring / end-of-day review | Med (needs trust) | Very High | Med | **High** | High (ongoing access) | Med | Best recurring revenue; sell only after proven internal practice |
| Training & onboarding workshops | Med | Med | Low-Med | Low-Med | Low | Med | Scales via recorded + live mix |
| Reusable governed-company templates (product) | Slow (build first) | Med (once proven) | High (to build well) | **High** (product) | Med (supply-chain responsibility) | **High** | The scalable endgame; companies.sh-compatible exports [Transcript 1, 18:41–19:35] |

**Do-not-oversell notes:** no source demonstrates a profitable autonomous business; sell *governed capability and oversight*, not "zero-human" outcomes; every client engagement starts in a sandbox with explicit data boundaries (Section 16).

---

# 22. QSL Implementation Recommendations

Incremental plan; each phase lists **success criteria** and **explicit non-goals**. **[QSL]**

## Phase 0 — Preserve and verify source knowledge
- **Do:** store this report and transcripts in Git; work the Claims Register (Section 25); read official Paperclip docs/repo; verify commands, adapter list, and feature availability against the live product.
- **Success criteria:** every High-priority claim in Section 25 marked Verified/Corrected/Refuted with links.
- **Non-goals:** no client promises; no production deployment; no doctrine changes yet.

## Phase 1 — Governed Email sandbox
- **Do:** one VPS instance; one company whose only domain is a **dedicated sandbox email account**; CEO with a QSL heartbeat protocol (review/recommend, no autonomous sending); read-only mail access first, draft-only second.
- **Success criteria:** 2 weeks running; every agent action traceable to an issue; zero unauthorized sends; cost within a pre-set budget; daily human review ≤ 15 min.
- **Non-goals:** no real client mailboxes; no outbound sending autonomy; no other integrations.

## Phase 2 — Standard company governance template
- **Do:** codify the QSL company baseline: mission/goal format, CEO heartbeat prompt (Section 9.2), hiring-packet requirement, PR-only repo pattern, budget defaults, review/disposition states; store as an exportable company template.
- **Success criteria:** a fresh company instantiated from the template passes the Section 23 checklists with no manual fixes; template exported and versioned in Git.
- **Non-goals:** no publishing to companies.sh yet; no client-specific content.

## Phase 3 — QSL Security sandbox company
- **Do:** a second company that *uses* Phase 2's template to perform internal security review of Phase 1: read-only inspection of configs, logs, budgets; threat-model the deployment (Section 16.3).
- **Success criteria:** written assessment with findings and fixes; demonstrates agents reviewing infrastructure under governance; all work evidence-backed.
- **Non-goals:** no automated remediation; no access to anything beyond the sandbox.

## Phase 4 — Read-only external connectors
- **Do:** add read-only connectors one at a time (e.g., analytics dashboards, public GitHub repos) with dedicated service accounts and scoped tokens.
- **Success criteria:** each connector passes the external-connector checklist; revocation tested per connector; no write scopes anywhere.
- **Non-goals:** no write access; no credential sharing between connectors; no client data.

## Phase 5 — Evidence/recommendation/review demonstration
- **Do:** build the flagship internal demo: an agent team that investigates a bounded question, produces an evidence-linked report, self-reviews against criteria, and presents a disposition-ready recommendation to a human Board.
- **Success criteria:** a 15-minute live demo a skeptical viewer finds credible; every claim in the output traceable to evidence; human disposition recorded.
- **Non-goals:** no autonomy theater; no claims beyond what the demo shows.

## Phase 6 — Client pilot
- **Do:** one friendly client; separate instance/host; sandboxed company; narrowly scoped objective; weekly human reviews; QSL-managed budgets.
- **Success criteria:** client-visible value within 30 days; zero security incidents; documented review trail; explicit client go/no-go.
- **Non-goals:** no production write access to client systems; no "zero-human" messaging; no multi-client scaling yet.

## Phase 7 — Productized service packages
- **Do:** package Phase 1–6 learnings into fixed-scope offers (Section 21): Secure Install, Governance Setup, Cost Control, Skills Audit, Managed Review.
- **Success criteria:** each package has a one-page spec, price, delivery checklist, and at least one delivery (paid or pilot).
- **Non-goals:** no bespoke unscoped engagements; no resale of unvetted third-party templates.

## Phase 8 — Reusable governed templates
- **Do:** publish/sell QSL governed-company templates (possibly via companies.sh-compatible export [Transcript 1, 18:41–19:35]) with provenance documentation and support terms.
- **Success criteria:** templates install cleanly in a fresh sandbox; documented skill provenance; first external user completes onboarding with the template checklist.
- **Non-goals:** no anonymous marketplace dumping; no templates with unreviewed third-party skills.

---

# 23. Operational Checklists

Concise, printable. **[QSL]** (Items marked ▲ reflect source mechanics; the rest are QSL controls.)

### 23.1 New Paperclip instance
- [ ] VPS/dedicated host (not a personal machine) ▲ [Transcript 2, 03:40–04:28]
- [ ] Strong unique admin credentials; stored in a password manager ▲ [Transcript 2, 06:04–06:47]
- [ ] Access restricted (Tailscale/private network preferred) ▲ [Transcript 1, 13:18–14:24]
- [ ] SSH: keys only, root password login disabled after setup ▲ [Transcript 2, 11:04–11:53]
- [ ] Docker hardened (non-root, no privileged, minimal mounts)
- [ ] Daily backups enabled and restore-tested ▲ [Transcript 2, 05:40–06:29]
- [ ] No secrets in env vars visible to UI users where avoidable ▲ [Transcript 2, 09:02–09:55]
- [ ] Log retention + off-box copy
- [ ] Instance owner + review-by date recorded

### 23.2 New company
- [ ] Specific, concise mission/goal ▲ [Transcript 2, 15:58–16:50]
- [ ] 3–4 goals max, with subgoals ▲ [Transcript 2, 26:53–27:45]
- [ ] Dedicated working directory, least privilege ▲ [Transcript 2, 17:41–18:33]
- [ ] Adapter tested green before launch ▲ [Transcript 2, 18:54–19:42]
- [ ] Company budget set (even on subscriptions)
- [ ] Board (human) named; review cadence set
- [ ] Template/governance baseline applied (Phase 2)

### 23.3 New CEO
- [ ] Heartbeat interval justified (start ≥ 1 hour) ▲ [Transcript 2, 21:45–22:35]
- [ ] QSL heartbeat protocol installed (review/recommend; no busywork)
- [ ] "Can create agents" = propose-only; approvals mandatory ▲ [Transcript 2, 22:39–23:22]
- [ ] Inbox routing verified (hire requests, blocked, review) ▲ [Transcript 2, 26:29–27:16]
- [ ] Budget + model recorded
- [ ] First-run supervised (manual heartbeats) ▲ [Transcript 2, 24:13–25:01]

### 23.4 New agent
- [ ] Hiring packet complete and Board-approved (Section 10)
- [ ] Role system prompt with rules/output format ▲ [Transcript 2, 35:37–36:21]
- [ ] Minimal skills attached (degradation risk) ▲ [Transcript 1, 06:00–06:59]
- [ ] Tools least-privilege; read-only where possible
- [ ] Reporting relationship set in org chart ▲ [Transcript 2, 23:00–23:48]
- [ ] Escalation conditions defined
- [ ] Budget + revocation tested

### 23.5 Third-party skill
- [ ] Source/provenance identified and trusted ▲ (skills.sh ecosystem [Transcript 1, 02:45–03:56])
- [ ] Full content read (it is prompt text = code)
- [ ] Version pinned + hash recorded
- [ ] Role-justified; not universal by default ▲ [Transcript 1, 06:00–06:59]
- [ ] Sandbox first run; behavior observed
- [ ] Re-review on update scheduled

### 23.6 Imported company (companies.sh)
- [ ] Imported to sandbox instance only ▲ [Transcript 1, 11:44–12:47]
- [ ] Agent/skill inventory reviewed at import prompt ▲
- [ ] Every instruction + skill read by a human
- [ ] Permissions stripped to least privilege before first run
- [ ] Read-only first run; outputs inspected
- [ ] Board sign-off recorded before any real use

### 23.7 External connector
- [ ] Dedicated service account ▲ (agent GitHub account pattern [Transcript 2, 27:19–28:10])
- [ ] Scoped token; read-only first; **never pasted into issues** (anti-pattern ▲ [Transcript 2, 27:19–28:10])
- [ ] PR-only / no main-branch commits for repos ▲ [Transcript 2, 28:08–28:58]
- [ ] Revocation path tested
- [ ] Data flows documented (what leaves the instance)

### 23.8 Recurring routine
- [ ] Named owner + consumer of the output ▲ (bookmark routine model [Transcript 1, 16:02–17:18])
- [ ] Schedule justified; near-zero cost when no change
- [ ] Stop-and-notify conditions (failure repeats, budget breach, missing inputs)
- [ ] Gathers/summarizes/recommends only — creates no unauthorized work
- [ ] Review-by date set

### 23.9 Client sandbox
- [ ] Separate host/instance per client
- [ ] No client production credentials; synthetic/scoped data
- [ ] Written scope: objectives, allowed actions, data boundaries
- [ ] Demo script + 15-minute review walkthrough ready (Phase 5)
- [ ] Exit/wipe procedure agreed

### 23.10 Production approval
- [ ] All prior checklists green
- [ ] Budgets + alerts live
- [ ] Disposition workflow (evidence → review → accept/return) demonstrated
- [ ] Incident response runbook in place
- [ ] Board approval recorded with review-by date

### 23.11 Incident response
- [ ] Stop: pause company / revoke adapter auth / stop container
- [ ] Contain: revoke exposed tokens; isolate host
- [ ] Preserve: export issues, runs, logs before changes ▲ (runs are inspectable [Transcript 2, 24:59–25:44])
- [ ] Assess: what acted, with what authority, what evidence
- [ ] Notify: Board + affected clients
- [ ] Learn: post-incident note feeding doctrine updates

### 23.12 End-of-day review (human, ≤15 min) ▲ (morning-report pattern [Transcript 1, 16:39–17:45])
- [ ] Inbox cleared: hires, blocked, review items ▲ [Transcript 2, 26:29–27:16]
- [ ] Completed issues sampled: evidence present, disposition recorded
- [ ] Spend vs. budget ▲ [Transcript 2, 24:59–25:44]
- [ ] Routines produced consumed output (else pause them)
- [ ] Any unauthorized work created? (If yes: incident)
- [ ] Tomorrow's priorities queued as issues

---

# 24. Terminology and Glossary

| Term | Meaning (source-based unless marked QSL) |
|---|---|
| **Adapter** | Connector between a Paperclip agent and a model runtime (Claude Code, Codex, OpenCode, Gemini, Cursor, Pi, process, OpenClaw gateway) [Transcript 2, 16:52–17:40]. |
| **Agent** | Persistent, instruction-carrying worker executed via an adapter session; stateless at wake, contextualized by Paperclip [Transcript 1, 01:49–02:41]. |
| **Board / Board of Directors** | The human operator(s) with approval authority over hires, reviews, and direction [Transcript 2, 00:50–01:44] [Transcript 2, 21:18–22:12]. |
| **Blocked (state)** | Issue state: work cannot proceed; reason + required intervention recorded [Transcript 2, 28:33–29:27]. |
| **CEO (agent)** | Top agent; runs the heartbeat; triages, delegates, proposes hires; the operator's primary interface [Transcript 2, 21:18–22:12]. |
| **Company** | Top-level organizational unit in Paperclip: mission, goals, agents, projects, issues, budgets [Transcript 2, 15:58–16:50]. |
| **companies.sh** | Registry/site for one-command installation of shareable company templates; intended as a cross-platform standard [Transcript 1, 07:57–09:13]. |
| **Company template** | Exportable/importable bundle of agents + skills + structure, with README and diagram [Transcript 1, 18:41–19:35]. |
| **Disposition** **[QSL]** | The recorded outcome of reviewed work: accepted / returned / escalated, with evidence. |
| **G Stack** | Garry Tan's (YC) skill collection (office hours, planning, engineering, design, QA) packaged as a company [Transcript 1, 06:30–08:04]. |
| **Heartbeat** | Scheduled CEO wake that scans the pipeline and triggers work; default 1 hour; only the CEO has one [Transcript 2, 21:45–22:35] [Transcript 2, 22:10–23:07]. |
| **Hiring packet** **[QSL]** | Board-approved specification defining an agent's role, authority, tools, budget, and review terms (Section 10.2). |
| **Inbox** | Operator notification queue for items the CEO judges human-worthy (hires, blocked, reviews) [Transcript 2, 26:29–27:16]. |
| **Instance** | A deployed Paperclip server hosting one or more companies [Transcript 2, 17:41–18:33]. |
| **Issue** | Unit of work with assignee, priority, labels, attachments, dates, comments, state [Transcript 2, 24:37–25:21]. |
| **Kanban / states** | backlog → to-do → in-progress → in-review / blocked → done (plus cancelled) [Transcript 2, 28:33–29:27]. |
| **Maximizer mode** | Announced-but-unreleased feature to keep agents working continuously [Transcript 1, 09:04–10:17]. **[QSL: philosophically opposed; see Section 20.]** |
| **Memory (PARA)** | Long-term agent memory skill based on Tiago Forte's PARA method, attributed to Nat Eliason [Transcript 1, 05:31–06:30]. |
| **Mission / Goal** | Company-level objective text set at creation; specificity without bloat recommended [Transcript 2, 15:58–16:50]. |
| **OpenClaw** | Adjacent agent tool ("OpenClaude" in auto-transcript); interoperable with Paperclip; inspired Paperclip's oversight design [Transcript 1, 19:37–20:49]. |
| **OpenRouter** | Model marketplace/router with leaderboard, anonymous pre-release models, and some free models [Transcript 1, 12:16–13:17]. |
| **Org chart** | Visual agent hierarchy (CEO → managers → workers) [Transcript 2, 23:00–23:48]. |
| **Project** | Grouping of issues within a company [Transcript 2, 23:52–24:34]. |
| **Review (state)** | Issue awaiting human approval; comment-based approval picked up at next heartbeat [Transcript 2, 29:48–30:30]. |
| **Routine** | Recurring scheduled work definition (e.g., nightly bookmark strategy report) [Transcript 1, 16:02–17:18]. |
| **Run** | A single agent execution; inspectable with stats and cost [Transcript 2, 24:59–25:44]. |
| **Skill** | Reusable capability package attachable to agents (e.g., Remotion, XLS, humanizer) [Transcript 1, 02:45–03:56]. |
| **skills.sh** | External skill library, attributed by the founder to Vercel [Transcript 1, 02:45–03:56]. |
| **Subscription CLI auth** | Using Claude Code/Codex/Gemini subscription logins on the host instead of metered API keys; ToS-sensitive [Transcript 2, 07:11–07:58]. |
| **Workspace / working directory** | Host filesystem directory where a company/agent operates [Transcript 2, 17:41–18:55]. |
| **Zero-human business** | Founder's framing for fully autonomous company operation [Transcript 1, 00:00–00:53]. **[QSL does not adopt; see Section 20.]** |

---

# 25. Claims and Verification Register

Confidence: High = consistent across sources or directly observable in demo; Medium = single-source, plausible; Low = promotional/speculative/uncertain transcription. All rows require verification against the live product/docs before downstream doctrinal use.

| # | Claim | Source | Timestamp | Type | Confidence | Verification required | Notes |
|---|---|---|---|---|---|---|---|
| 1 | Paperclip is open-source and free to self-host | T2 | 00:00–00:51 | Product | High | Locate repo; confirm license | "Tens of thousands of GitHub stars" is hype-flavored; verify count |
| 2 | Paperclip was "3 weeks old" at T1 recording | T1 | 09:04–10:17 | Product age | Medium | Date the video; check repo history | Anchors maturity expectations |
| 3 | "Zero human business" is achievable today | T1 | 00:00–00:53 | Promotional | Low | None possible short-term | Contradicted by constant human approvals in both demos |
| 4 | "One shot an entire company" | T1 | 00:00–00:53 | Promotional | Low | Define terms; reproduce | Founder hedges: "I don't want to oversell it" |
| 5 | CEO-only heartbeat; default 1 hour; configurable (600s demo) | T2 | 21:45–22:35; 22:10–23:07 | Feature | High | Confirm in product config | Cost driver; Section 15 |
| 6 | Only CEO heartbeats; other agents triggered by delegation/assignment | T2 | 22:10–23:07 | Feature | Medium | Confirm no per-agent schedules beyond routines | Routines may wake other agents [T1 16:02–17:18] |
| 7 | Assigning an issue triggers near-immediate pickup | T2 | 24:13–25:01; 30:33–31:18 | Feature | Medium | Test | Presenter hedges ("I believe") |
| 8 | CEO can create agents (permission toggle); hires require human approval | T2 | 22:39–23:22; 23:00–23:48; 32:53–33:35 | Feature | High | Confirm toggle semantics | Approval inbox observed |
| 9 | Agents can hire sub-agents; no depth limit | T2 | 01:17–02:03; 33:34–34:21 | Feature | Medium | Test nested hiring | Governance risk; Section 20 |
| 10 | Adapters: Claude Code, Codex, Cursor, Pi, OpenCode, Gemini, process, OpenClaw gateway | T2 | 16:52–17:40 | Feature | Medium-High | Confirm adapter list in docs | "Open Claude gateway" read as OpenClaw |
| 11 | Subscription CLI auth works headless (`claude`, `codex login --device-auth`) | T2 | 13:06–14:49 | Feature | High | Reproduce in sandbox | ToS exposure unresolved |
| 12 | Subscription-orchestration may violate provider ToS | T2 | 07:11–07:58; 13:58–14:49 | Legal | Medium | Read Anthropic/OpenAI terms | Presenter explicitly unsure |
| 13 | Docker deployment via Hostinger one-click; "one of the most secure ways" | T2 | 07:56–08:39 | Hosting/Security | Medium (deploy) / Low (security superlative) | Deploy; threat-model | Sponsored segment |
| 14 | VPS cost "as little as $7/month" | T2 | 04:31–05:17 | Cost | Medium | Check current Hostinger pricing | Promotional context |
| 15 | Admin password visible via container environment variables | T2 | 09:02–09:55 | Security | High (observed) | Confirm; assess exposure | Feeds hardening checklist |
| 16 | Tailscale enables secure remote/mobile access; mobile UI works well | T1 | 13:18–14:24 | Feature | Medium | Test mobile UI | Plausible, standard pattern |
| 17 | Cloud-hosted Paperclip version planned | T1 | 13:18–14:24 | Roadmap | Low-Medium | Watch official channels | No date given |
| 18 | companies.sh provides one-command company installs | T1 | 11:44–12:47 | Feature | High (demoed) | Run in sandbox | Exact command syntax uncertain (transcription) |
| 19 | companies.sh is an open standard, intentionally not Paperclip-branded | T1 | 07:57–09:13 | Governance claim | Medium | Inspect site/spec | Portability unproven |
| 20 | Company export includes README + diagrams, shareable via GitHub | T1 | 18:41–19:35 | Feature | Medium-High | Export a test company | Format details unverified |
| 21 | Marketplace for buying/selling companies/agents planned ("clip mart"/Claw Mart tie-in) | T1 | 19:08–20:06 | Roadmap | Low | Watch announcements | Brainstorm-level in video |
| 22 | OpenRouter hosts anonymous pre-release models + free models ("free inference") | T1 | 12:16–13:17 | Cost/Feature | Medium | Check OpenRouter | Quality/privacy unevaluated |
| 23 | Loading too many skills degrades model performance | T1 | 06:00–06:59 | Model behavior | Medium-High | Test empirically | Consistent with known LLM behavior |
| 24 | PARA memory skill gives agents long-term memory | T1 | 05:31–06:30 | Feature | Medium | Test retention behavior | Attributed to Nat Eliason |
| 25 | skills.sh is "from the guys at Vercel" | T1 | 02:45–03:56 | Attribution | Medium | Verify ownership | — |
| 26 | G Stack = Garry Tan's YC methods as skills (office hours, planning, design, QA) | T1 | 06:30–08:04 | Third-party content | Medium-High | Inspect G Stack repo | Host corroborates use |
| 27 | Agents pushed a real PR to presenter's website overnight; built a new repo/platform | T2 | 02:28–03:17 | Outcome | Medium | Inspect PR/repo quality | Shown briefly; quality unverified |
| 28 | Routines support scheduled recurring work (bookmark strategy report) | T1 | 16:02–17:45 | Feature | High | Reproduce | Output usefulness is founder's judgment |
| 29 | Paperclip runs Paperclip's own company (CEO/CTO/coders) | T1 | 00:27–01:23 | Dogfooding | Medium | — | Org chart shown; output depth unknown |
| 30 | Founder anonymous "from the crypto world" | T1 | 00:55–01:41 | Speaker | Medium | — | Affects trust calibration |
| 31 | You could rebuild Paperclip's core "in a few days" | T2 | 37:09–38:06 | Opinion | Low-Medium | — | Presenter estimate; signals thin moat |
| 32 | Inbox shows only what the CEO judges human-worthy | T2 | 26:29–27:16 | Feature | Medium | Test filtering behavior | Missed-signal risk; Section 23.12 |

---

# 26. Source-Derived Insights

The strongest lessons that can be responsibly inferred:

1. **The durable product idea is oversight, not autonomy.** Both sources independently converge on the same pain: many agent sessions without a system of record [Transcript 1, 01:18–02:21] [Transcript 2, 37:09–38:06]. Tracked conversations, costs, states, and approvals are the value; autonomy is the demo.
2. **Issue-driven work beats chat for multi-agent systems.** Issues create addressable, assignable, reviewable units of work with state — the foundation for any governance layer [Transcript 2, 20:30–21:22].
3. **Identity + memory + skills are the agent stack.** Persistent instructions (who am I), memory (what happened), and skills (what can I do) — each attachable per role — is a reusable organizational design pattern [Transcript 1, 01:49–02:41] [Transcript 1, 06:00–06:59].
4. **Proactivity is a prompt-engineering problem.** A CEO without an explicit operating protocol idles; a phased heartbeat protocol changes behavior materially [Transcript 2, 34:23–35:17]. Governance protocols are likewise prompt-level enforceable.
5. **Human approval gates already exist in the product.** Hire approvals, review states, blocked queues — QSL's governance model can be implemented largely by *configuring* Paperclip rather than fighting it [Transcript 2, 23:00–23:48] [Transcript 2, 28:33–29:27].
6. **Skill discipline matters.** Few, role-matched, provenance-checked skills; more is actively worse [Transcript 1, 06:00–06:59].
7. **Templates are the scaling vector — and the threat vector.** companies.sh can spread good patterns or malicious ones at the same speed [Transcript 1, 07:57–09:13] [Transcript 1, 11:44–12:47].
8. **Cost control is an operating habit, not a feature.** Heartbeat intervals, budgets, session parallelism, and routine hygiene determine the bill [Transcript 2, 22:10–23:07] [Transcript 2, 24:59–25:44].
9. **Feedback loops are the quality story — with limits.** Researcher→writer→editor→reviewer→CEO→human chains are the demonstrated quality mechanism, but they multiply cost and don't guarantee correctness [Transcript 2, 33:57–34:48].
10. **The honest demo includes the humans.** Both videos show constant approvals, unblocking, and steering — evidence that "human-governed" is not a compromise but the current reality of well-run agent organizations [Transcript 2, 38:00–38:49].

---

# 27. Open Questions

Prioritized research and testing backlog:

**P0 (blocks any client work):**
1. Verify installation commands, adapter list, and auth flows against the live product/docs (transcript renderings uncertain) [T1 11:14–12:47] [T2 16:52–17:40].
2. Read Anthropic/OpenAI terms for subscription-CLI orchestration; decide QSL's compliant auth posture [T2 07:11–07:58].
3. Threat-model the Docker deployment: container escape surface, env-var secret exposure, UI auth strength, update mechanism [T2 07:56–08:39] [T2 09:02–09:55].
4. Measure real cost: tokens per CEO heartbeat (idle vs. active), per routine run, per review loop; establish budget baselines [T2 22:10–23:07].
5. Test hire-approval enforcement: can a CEO bypass or socially-engineer approvals? Is "can create agents" granular [T2 22:39–23:22]?

**P1 (needed for Phase 1–3):**
6. Disposition mechanics: can issue states/custom fields carry evidence links and review outcomes durably?
7. Memory behavior: what does the PARA skill actually persist, where, and how is it corrected/erased (client data handling) [T1 05:31–06:30]?
8. Routine failure modes: retry policy, duplicate output, cost when inputs are missing [T1 16:02–17:18].
9. companies.sh supply chain: template format, signing/provenance, permission manifest at import [T1 11:44–12:47].
10. Skill loading mechanics: order, precedence, conflict behavior when skills contradict role prompts [T1 06:00–06:59].
11. Multi-company isolation on one instance: shared credentials? cross-company visibility [T2 37:09–38:06]?

**P2 (strategic):**
12. Export format fidelity: does a re-imported company reproduce prompts, skills, permissions, budgets exactly [T1 18:41–19:35]?
13. Status of maximizer mode, hosted cloud version, marketplace — monitor official channels [T1 09:04–10:17] [T1 13:18–14:24] [T1 19:08–20:06].
14. Evaluation harness: how to measure agent output correctness per role (review-loop effectiveness metrics).
15. OpenClaw-gateway adapter: migration/interop path for existing OpenClaw users as a service opportunity [T1 19:37–20:24] [T2 16:52–17:40].
16. Legal/liability posture for operating agent companies on behalf of clients (contracts, insurance, disclosure).

---

# 28. Conclusion

**What Paperclip enables today:** a self-hosted, model-agnostic, issue-driven control plane for multi-agent work, with persistent agent identities, per-role skills and memory, CEO-heartbeat coordination, human approval gates, cost/run visibility, routines for recurring work, and import/export of whole company structures. Both sources show the same credible core: not autonomy, but *legibility and coordination* of many agent sessions [Transcript 1, 01:18–02:21] [Transcript 2, 37:09–38:06].

**What remains uncertain:** output correctness at scale; security of the default deployment; ToS compliance of subscription auth; real monthly costs; template supply-chain safety; every roadmap item (maximizer mode, hosted cloud, marketplace); and the entire "zero-human business" thesis — for which neither source provides evidence, and both quietly refute through constant human approvals [Transcript 1, 00:00–00:53] [Transcript 2, 32:08–32:56].

**Why QSL's governance-first model is the preferred direction:** the product's own best moments in these sources are governance moments — a human approving hires, a reviewer agent gating publication, PR-only repo access, a blocked issue asking for help. QSL simply makes those moments the system rather than the exception: explicit bounded authority, Board-approved expansion, evidence-backed dispositions, revocable autonomy, and a bias for trustworthy operation over maximum activity. That posture is also the credible market position: clients will pay for agent capability they can defend to their own stakeholders, not for demos of unattended companies.

---

# Appendix A. Actionable Takeaways

## High Priority
1. Complete Phase 0 verification of P0 claims (Section 25, rows 1, 5–8, 10–13, 15).
2. Adopt the issue-driven, human-gated operating model as QSL's baseline: hires, reviews, and external effects always pass a human [Transcript 2, 23:00–23:48] [Transcript 2, 28:33–29:27].
3. Write the QSL CEO heartbeat protocol (review/recommend, no busywork) before any sandbox run (Section 9.2).
4. Stand up no agent environment outside an isolated VPS/Docker host with restricted network access [Transcript 2, 03:40–04:28].
5. Institute the hiring packet (Section 10.2) as the single path to agent creation.

## Medium Priority
6. Build the governance company template (Phase 2) encoding budgets, PR-only repos, review states.
7. Establish skill provenance review (Section 11.5) before installing any third-party skill.
8. Define cost baselines: measure heartbeat/routine/review-loop token burn; set conservative defaults (Section 15.2).
9. Draft secrets-handling rules: never in issues; dedicated service accounts; rotation runbook [anti-pattern: Transcript 2, 27:19–28:10].
10. Create the 15-minute evidence/recommendation/review demo (Phase 5).

## Low Priority
11. Evaluate Tailscale remote/mobile access for operator convenience [Transcript 1, 13:18–14:24].
12. Track companies.sh standard/spec evolution for future template distribution [Transcript 1, 07:57–09:13].
13. Experiment with OpenRouter free models for non-sensitive triage tasks only [Transcript 1, 12:16–13:17].
14. Monitor maximizer mode / hosted cloud / marketplace announcements [Transcript 1, 09:04–10:17] [Transcript 1, 13:18–14:24].

## Questions to Verify
- Exact onboarding and companies.sh command syntax [Transcript 1, 11:14–12:47].
- Adapter roster and OpenClaw gateway configuration [Transcript 2, 16:52–17:40].
- Subscription-CLI ToS compliance [Transcript 2, 07:11–07:58].
- Immediate-trigger behavior of assigned issues [Transcript 2, 24:13–25:01].
- Export format fidelity and re-import behavior [Transcript 1, 18:41–19:35].
- Inbox filtering reliability (missed signals) [Transcript 2, 26:29–27:16].

## Potential Revenue Ideas
Ranked summary of Section 21: start with Secure Install + Governance Setup bundles; grow Managed Monitoring (recurring) and Cost-Control reviews; endgame is versioned, provenance-documented governed-company templates as a product. Heed the office-hours warning: package services as products — "services don't scale" [Transcript 1, 17:13–18:07].

## Potential Doctrine Updates
- Agent Governance chapter: hiring packets, bounded/revocable authority, Board approval mechanics.
- Evidence & Disposition chapter: completion requires artifacts + review + recorded outcome.
- Skills & Templates Supply-Chain chapter: provenance, pinning, sandbox import.
- Cost Stewardship chapter: heartbeat economics, budgets, routine hygiene.
- Isolation & Secrets chapter: VPS/Docker hardening, service accounts, no-secrets-in-issues.
- Routines chapter: stopping conditions, output consumers, no unauthorized work creation.

## Potential Paperclip Improvements
(Feedback candidates for upstream or QSL wrappers.)
1. First-class task disposition (evidence links, review outcome, approver identity) on issue close.
2. Secrets store integration so credentials never touch issues/env-var UIs.
3. Retry caps and loop detection with auto-block + escalate.
4. Import-time permission manifest and diff view for company templates.
5. "Governor mode": heartbeat that audits and recommends instead of maximizing activity — QSL's answer to maximizer mode [Transcript 1, 09:04–10:17].
6. Per-agent budget enforcement independent of API-key metering (works under subscription auth too).

---

# Recommended Next Actions

1. Human review of this report (≤15 min): confirm structure, correct any mis-cited timestamps, approve for commit.
2. Commit repo structure (`transcripts/`, `reports/`, `prompts/`) to Git.
3. Execute Phase 0 (Section 22): verify P0 rows in the Claims Register against official Paperclip sources; log corrections in the change log below.
4. Schedule Phase 1 sandbox build (Governed Email company) only after P0 verification closes.
5. Pull approved concepts into downstream docs (QSL Doctrine, Paperclip Docs, TheBinMap, Client Playbooks) **only** after review marks this report `Reviewed: Yes`.

# Suggested Doctrine Chapters (to absorb verified lessons later)

1. **Governed Agent Organizations** — CEO/Board model, hiring packets, bounded and revocable authority.
2. **Issue-Driven Operations** — states, dispositions, evidence requirements, review queues.
3. **Agent Identity, Memory, and Skills** — persistent instructions, PARA-style memory rules, skill provenance and minimalism.
4. **Heartbeat Economics** — scheduling, budgets, retries, routine hygiene, cost review.
5. **Isolation and Secrets** — deployment hardening, service accounts, network restrictions, incident response.
6. **Template Supply Chain** — companies.sh-style imports, sandbox verification, export standards for QSL templates.
7. **Client Engagement Patterns** — sandbox pilots, 15-minute review ritual, productized governance services.

# Change Log

| Date | Change | Author |
|---|---|---|
| 2026-07-20 | Initial comprehensive source report created from Transcripts 1–2; repo structure established (transcripts/, reports/, prompts/); transcript metadata + takeaways added. | Kimi (pending human review) |
| — | *Future: record verification outcomes for Section 25 rows, corrections, and doctrine absorption events here.* | — |





