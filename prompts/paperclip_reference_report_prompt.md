# Paperclip Reference Report — Generation Prompt

**Captured:** 2026-07-20
**Purpose:** Preserve the exact tasking used to generate
`reports/paperclip/PAPERCLIP_COMPREHENSIVE_SOURCE_REPORT_2026-07-20.md`
so the report can be regenerated, extended, or audited later.

---

## Suggested repository structure

```
YT-Transcripts/
│
├── transcripts/
│   └── paperclip/
│       ├── transcript-01.md
│       └── transcript-02.md
│
├── reports/
│   └── paperclip/
│       ├── PAPERCLIP_COMPREHENSIVE_SOURCE_REPORT_2026-07-20.md
│       └── assets/
│
└── prompts/
    └── paperclip_reference_report_prompt.md
```

That keeps the raw transcripts, the report, and the prompt together. Later, the QSL
doctrine can reference this report without duplicating it.

Knowledge flow:

```
Raw Sources → Reference Reports → QSL Doctrine → Operational Playbooks → Client Deliverables
```

---

## Task: Create a Comprehensive Paperclip Reference Report

Analyze the two attached Paperclip interview/tutorial transcripts and produce a
detailed, durable reference report.

### Purpose

This report will serve as source material for:

- operating Paperclip effectively;
- designing governed AI organizations;
- building the future QSL operating handbook;
- creating client-facing services and demonstrations;
- preserving product details, workflows, terminology, examples, limitations, and emerging opportunities.

This is a reference-capture task, not a brief summary.

### Core Requirement

Preserve all meaningful details from both transcripts while reorganizing them into a
clear, professional, technically useful document.

Do not merely summarize the videos chronologically.

Extract, consolidate, and classify the information.

### Important Perspective

Clearly separate:

1. Claims or practices described by Paperclip's creator or tutorial presenters.
2. Directly observable Paperclip capabilities.
3. Opinions, promotional claims, predictions, and unverified assertions.
4. Operational lessons that can reasonably be inferred.
5. QSL-specific interpretations or recommendations.

Do not present marketing language as established fact.

The source material frequently emphasizes autonomous or "zero-human" companies. QSL
does not automatically adopt that philosophy.

QSL's current direction is governance-first:

- humans retain governing authority;
- agent authority is explicit, bounded, and revocable;
- new agents may be proposed by a CEO but require human approval;
- read-only and sandboxed access should be preferred initially;
- meaningful work requires evidence, review, and an explicit disposition;
- autonomy is enabled deliberately for approved, bounded objectives;
- the goal is trustworthy operations, not maximum autonomous activity.

Use these principles when identifying where QSL intentionally differs from the source
material, but do not distort what the speakers actually said.

### Required Sections

1. **Executive Overview** — what Paperclip is, the problem it attempts to solve, and its general operating model.
2. **Source Notes** — for each transcript: apparent speaker/presentation context; main focus; level of technical detail; promotional/sponsorship context; limitations of the source.
3. **Paperclip's Core Value Proposition** — multi-agent organization; task and issue management; persistent instructions; traceable conversations; cost tracking; retrospective inspection; organizational visibility; coordination across agent sessions; why Paperclip differs from direct work in Claude Code, Codex, OpenCode, Cursor, or similar tools.
4. **Architecture and Core Concepts** — instances; companies; missions and goals; projects; issues; agents; CEOs; managers and workers; organizational charts; heartbeats; routines; skills; memory; permissions; approvals; inbox notifications; workspaces; adapters; model/provider selection; costs and budgets; blocked, review, in-progress, and completed states; imports and exports; company templates. Include a text-based architecture diagram.
5. **Installation and Deployment** — local installation; dedicated machine; VPS; Docker deployment; Hostinger one-click deployment; authentication; admin credentials; environment variables; API keys; model subscriptions; SSH access; container access; CLI authentication; working directories; remote access through Tailscale; potential future hosted Paperclip service. Include warnings about secrets, root access, internet exposure, backups, provider terms, and subscription usage. Do not repeat passwords, API keys, login codes, or other secrets.
6. **Model and Adapter Configuration** — Claude Code; Codex; OpenCode; OpenRouter; Gemini; Cursor; OpenClaw gateway; direct APIs versus subscription-authenticated CLIs; different models for different agent roles; provider/model naming; free or experimental inference claims; model personality, strengths, and weaknesses; configuration validation and adapter testing. Highlight that provider selection may determine authentication behavior.
7. **Company Onboarding Workflow** — create company; define mission and goal; select adapter; specify working directory; test connection; launch the initial task; create or approve the first hire; establish projects and agents; assign work; monitor results.
8. **Issue-Based Work Model** — why Paperclip is presented as an issue-driven operating environment rather than a chatbot: creating issues; assigning issues; leaving issues unassigned for CEO triage; priorities; labels; attachments; dates; comments; review; approval; blocked work; manual state changes; immediate triggering; heartbeat pickup; summaries and artifacts.
9. **CEO Operating Model** — CEO heartbeat; delegation; proactive operation; checking idle agents; reviewing completed work; hiring; requesting Board approval; creating projects and tasks; maintaining momentum; assigning recurring work. Then a subsection **"QSL Governance Interpretation"**: the CEO may detect capability gaps and propose hires; the human Board approves organizational expansion; approved hiring packets define roles; the CEO does not receive blanket permission to invent agents or work; heartbeats should review evidence, states, approvals, risks, and budgets rather than manufacture busywork; proactive evidence gathering is preferable to uncontrolled task creation.
10. **Agent Creation and Hiring** — CEO-created agents; Board approval requests; organizational hierarchies; manual agent creation; specialization; reporting relationships; agent instruction templates; role-specific capabilities; assigning skills during hiring. Include a reusable hiring-packet template with: role; purpose; mission; authority; prohibited actions; tools; skills; reporting relationship; inputs; outputs; completion states; budget; escalation conditions; review requirements.
11. **Skills** — reusable capabilities; external skill libraries; skills.sh; examples from the transcripts; Remotion; spreadsheets; humanized writing; memory methods; engineering and design methods; QA patterns; role-specific attachment; universal versus specialized skills; prompt-context degradation from loading too many skills; skill selection and maintenance; security and provenance risks of third-party skills.
12. **Memory** — why agents need identity and continuity; persistent instructions; organizational memory; agent memory; project memory; PARA-style memory; what memory should and should not retain; contamination, stale context, and privacy risks; the difference between memory and authoritative evidence.
13. **Routines and Recurring Work** — recurring tasks; bookmark analysis example; overnight work; scheduled strategy reports; monitoring and continuous operation; when routines are useful; how they can waste tokens or create noise; required stopping and notification conditions.
14. **Review and Feedback Patterns** — agents checking one another's work; researcher-writer-editor-reviewer loops; QA review; escalation to CEO; final human review; comments on issues; returning work for revision; blocked and review queues. Explain why feedback loops are valuable, while warning that additional agents do not automatically guarantee correctness.
15. **Costs, Budgets, and Resource Control** — token and API cost tracking; subscriptions versus metered APIs; per-agent and company budgets; heartbeat frequency; parallel sessions; retries; corrective wakes; unnecessary activity; auxiliary models; operational cost review. Include QSL recommendations for conservative defaults.
16. **Security and Isolation** — risks of autonomous agents on personal computers; local file access; home-network exposure; credentials; credit cards and browser sessions; internet access; root privileges; Docker isolation limitations; VPS isolation; sandboxing; dedicated service accounts; least privilege; read-only access; branch protection; pull requests instead of direct main-branch commits; secrets management; backups; logs; revocation; client-environment boundaries; threat modeling. Distinguish actual capabilities described in the sources from speculative examples used by presenters.
17. **companies.sh and Shareable Companies** — companies.sh; one-command company installation; company templates; included agents and skills; G Stack example; export workflow; README and diagrams; GitHub sharing; proposed marketplace; reusable organizational patterns; standardization ambitions; portability to other orchestration platforms. Include supply-chain, trust, permission, skill-provenance, and malicious-template risks.
18. **Demonstrated Use Cases** — newsletter operations; content analysis; website optimization; pull requests; newsletter platform development; video creation; spreadsheets and data analysis; YouTube growth; analytics integration; ConvertKit integration; GitHub workflows; game development; strategy reports; bookmark analysis; startup office hours; install/customization services; software engineering organizations. For each, explain what was demonstrated, claimed, or merely proposed.
19. **Limitations and Unresolved Questions** — immature software; presenters' limited experience; need for manual intervention; agents stopping unexpectedly; proposed maximizer mode; excessive autonomy; monitoring burden; cost; model failures; weak task disposition; retries and loops; security uncertainty; provider terms; template trust; context degradation; evaluation difficulty; correctness limits; hallucinations; organizational complexity; unclear accountability; lack of evidence that "zero-human" businesses are dependable.
20. **QSL's Deliberate Divergence** — dedicated comparison table (Upstream/Presenter Emphasis vs QSL Direction) and a full explanation of QSL's operating principles.
21. **Revenue and Service Opportunities** — Paperclip installation; secure configuration; company-template customization; governance setup; skills evaluation; model/provider configuration; cost controls; workflow design; client sandbox demonstrations; security assessment workflows; managed monitoring; training and onboarding; reusable governed-company templates. Evaluate each by: time to first revenue; trust requirements; delivery difficulty; recurring-revenue potential; security risk; scalability. Do not oversell.
22. **QSL Implementation Recommendations** — incremental plan: Phase 0 — Preserve and verify source knowledge; Phase 1 — Governed Email sandbox; Phase 2 — Standard company governance template; Phase 3 — QSL Security sandbox company; Phase 4 — Read-only external connectors; Phase 5 — Evidence/recommendation/review demonstration; Phase 6 — Client pilot; Phase 7 — Productized service packages; Phase 8 — Reusable governed templates. For each phase, define success criteria and explicit non-goals.
23. **Operational Checklists** — new Paperclip instance; new company; new CEO; new agent; third-party skill; imported company; external connector; recurring routine; client sandbox; production approval; incident response; end-of-day review.
24. **Terminology and Glossary** — define all important terms from the transcripts and QSL interpretation.
25. **Claims and Verification Register** — table with: claim; source transcript; timestamp; claim type; confidence; verification required; notes. Examples: product age; feature availability; hosting claims; security claims; future features; companies.sh capabilities; marketplace plans; free inference; Tailscale access; export format; hosted version plans.
26. **Source-Derived Insights** — the strongest lessons that can be responsibly inferred.
27. **Open Questions** — prioritized research and testing backlog.
28. **Conclusion** — what Paperclip enables today, what remains uncertain, and why QSL's governance-first model is the preferred direction.

### Citation Requirements

Cite transcript timestamps throughout, using a consistent style such as:

- `[Transcript 1, 22:10–23:48]`
- `[Transcript 2, 05:31–06:59]`

Do not invent timestamps. When the same idea appears in both sources, cite both.

### Writing Style

- Professional engineering handbook/report.
- Comprehensive but organized.
- Preserve technical details.
- Avoid hype.
- Clearly mark uncertainty.
- Use diagrams, tables, workflows, templates, and checklists where useful.
- Do not repeat the same concept unnecessarily.
- Write in clean Markdown.
- Suitable for direct storage in a Git repository.

### File Output

Create: `PAPERCLIP_COMPREHENSIVE_SOURCE_REPORT_2026-07-20.md`

At the top include: Title; Date; Status: Source Reference; Scope; Source list;
Intended downstream uses; explicit note that this is not yet the canonical QSL doctrine.

End with: Recommended next actions; Suggested doctrine chapters that should later
absorb verified lessons; A short change-log section for future revisions.
