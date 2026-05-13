### Hi, I'm Denis 👋

> Product leader & engineer at the intersection of **B2B FinTech and AI**.
> Director of Product at **Cinimex Group** ([KZ](https://cmx.kz/en/) · [RU](https://www.cinimex.ru)) by day; shipping AI-native systems and infrastructure on GitHub to stay close to the metal.

[![ORCID](https://img.shields.io/badge/ORCID-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0007-8342-558X)
[![Google Scholar](https://img.shields.io/badge/Scholar-4285F4?logo=googlescholar&logoColor=white)](https://scholar.google.com/citations?user=CHw8i34AAAAJ&hl=en)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/denis-ermilov-42291a1b)

---

### Track record at a glance

- **20 years** in B2B FinTech and banking platforms
- Grew the practice I lead from **$0.2M → $15M annual revenue** and **9 → 150+ specialists**
- **8 national award-winning projects** across TAdviser IT Prize, CNews Innovation, FINNEXT, Best ESG, "Project of the Year"
- **Payment Hub** — large-scale RF cross-border infrastructure (TAdviser IT Prize 2023) · **VTB API Platform** — 2,000+ internal teams, 700+ APIs (CNews Innovation 2023) · **OpsNext** — 99% STP across 5.4B annual transactions · **Strela** — first corporate-deal personalization system in RF (FINNEXT 2025)
- **IEEE Senior Member** (#99277800) · **Patent holder** (RU 2012616579 — *Cinimex Test Tool*, deployed in 6 of the top-10 RF banks) · **Author** of *Digital Bank* (Amazon, 2023)

---

### What I'm building (personal lab on GitHub)

| | Project | Stack | Why it matters |
|---|---|---|---|
| 🤖 | **[ai-tab-optimizer](https://github.com/eiler2005/ai-tab-optimizer)** — local-first Chrome extension that turns 100+ tabs into structured, searchable knowledge | TS · Chrome MV3 · FastAPI · SQLite · Claude Code / Codex CLI | A real productivity problem solved with a privacy-respecting, AI-augmented workflow. 8 product views; discriminated-union message protocol; per-batch provider failover |
| 💸 | **[bnpl-flexipay-hub](https://github.com/eiler2005/bnpl-flexipay-hub)** — modular white-label Buy Now Pay Later platform | React 18 · Vite · TS · shadcn/ui · Tailwind | High-fidelity, fully-navigable prototype so a stakeholder can click through end-to-end *before* the first backend endpoint is written. Three role-based applications under one router |
| 🤝 | **[dealsnext-insight-hub](https://github.com/eiler2005/dealsnext-insight-hub)** — Lovable-built MVP for B2B deal personalization | TypeScript · Lovable · React · shadcn/ui | Indie companion to the corporate **DealsNext** platform (FINNEXT 2025 winner) — same thesis, prototyped solo with rapid AI tooling to test ideas before committing to a production stack |
| 🇬🇧 | **[FluentLoop](https://github.com/eiler2005/FluentLoop)** — single-user English-learning bot that lives in Telegram | Python 3.11 · Telethon · APScheduler · SQLAlchemy · Docker · DeepSeek | Spaced-repetition + mistake-pattern detection. 14 epics + 6-epic learning-engine roadmap, shipped end-to-end in one autonomous overnight build |
| 🧠 | **[clawden-ai](https://github.com/eiler2005/clawden-ai)** — always-on personal AI ops platform on Hetzner | Python 3.12 · OpenClaw · LightRAG · MCP · Telegram | AI that *pushes* relevant signals before I ask, instead of waiting in a chat window. Three-tier model dispatcher, knowledge-graph memory |
| 📨 | **[maxgram](https://github.com/eiler2005/maxgram)** — personal MAX → Telegram bridge: read and answer all MAX chats from Telegram, without installing MAX | Python · WebSocket userbot · SQLite · Docker · Ansible · Hetzner | Reverse-engineered an unofficial WebSocket API; idempotent message dedup; privacy-first (no message bodies stored, only routing metadata); supervisor runtime with persistent health model; Ansible-codified ops |
| 🛡️ | **[ghostroute](https://github.com/eiler2005/ghostroute)** — router-level VLESS+Reality routing for ASUS Merlin | Shell · iptables · sing-box · xray | Zero-config home network for ordinary devices, explicit egress control. Multi-channel data plane with explicit ownership boundaries; bilingual EN/RU operator docs |

> Plus a long-running side project from 2018: [backtestportaa](https://github.com/eiler2005/backtestportaa) — Java tool for back-testing investing portfolios with technical indicators.

---

### International work

Public, large-scale collaborations across borders:

- **Cinimex Group** operates across **CIS and Southeast Asia** with regional offices including a dedicated [Kazakhstan office](https://cmx.kz/en/) — gives the team a working footprint across multiple regulatory perimeters
- **Volkswagen Group AG** — joint dealer-network digital ecosystem and IDP platform with the Berlin office (Kubernetes / microservices, 40-person cross-border team)
- **Alibaba / AliPay** — adoption of **ISO 20022** for cross-border payments processed through Russia
- **Bank of Russia** — first **CBDC (digital ruble)** transactions in the country; first **B2B smart contracts in construction** (Mosinzhproekt); contributor to CBDC technical standards
- **Direct payment channels** built into Payment Hub: China (UnionPay, CIPS), India (NPCI, RuPay), Vietnam, Bangladesh — covering **~60% of RF cross-border trade** with the Asian region
- **McKinsey & Company · EPAM Systems** — joint delivery on enterprise digital-transformation programs
- Began my career at **Exigen Services** (now Emergn) — at the time a top-4 outsourcing firm globally, US clients, English-medium delivery

---

### How I think about building things

- **Start from the user, not the framework.** Every project begins with *"what does this make easier for the person using it?"* — only then does the stack become a question.
- **Ship narrow, then expand.** A prototype that does one thing well beats a backlog of half-built features. If real users don't pull on a feature, it doesn't get built next.
- **Defaults are policy.** Cosmetic choices — copy, ordering, what's pre-selected — have product consequences. They get the same care as architecture.
- **Documentation is part of the deliverable.** Every project ships with a real README, architecture notes, and CI from day one. If a reviewer can't understand the system from the repo, the system isn't done.
- **AI in the loop, not in the way.** Production tooling, not a demo — see the patterns below.

---

### How I build with AI in production

**Patterns I reach for:**

- **Discriminated-union message protocols** — every cross-process message is a member of one TypeScript union; adding one without handling it doesn't compile (45-type union in `ai-tab-optimizer`)
- **Per-batch provider failover** — Claude Code → Codex CLI → heuristic, decided per batch by a small policy module; transient rate limits don't kill long autonomous runs
- **Three-tier model dispatcher** — cheap classification → medium reasoning → expensive synthesis, picked automatically per task (`clawden-ai`'s OmniRoute)
- **Stop-and-resume autonomous runs** — run state in SQLite with per-tab status, pending queue, partial results, accumulated metadata; survives reload mid-1000-tab sweep
- **Knowledge-graph memory** — LightRAG over an Obsidian vault, fed continuously by event-driven bridges; replaces "chat history" as long-term context
- **Multi-channel data planes with explicit ownership boundaries** — no silent rewriting between layers (`ghostroute`'s A/B/C channels)
- **MCP-first context engineering** — custom MCP servers (`lean-ctx`) and tool-search budgets to keep agentic dev sessions within cache windows

**Tooling**

- **AI runtime** — Claude Code · Codex CLI · OpenClaw · MCP servers · LightRAG · DeepSeek · Yandex AI Studio · Anthropic / OpenAI APIs
- **Niche stack** — sing-box · xray · Reality protocol · Hetzner · Telethon · ASUS Merlin
- **Languages & web** — TypeScript · Python · Java · React · Vite · FastAPI · Tailwind · shadcn/ui · Docker · SQLite · PostgreSQL · Linux

---

### Beyond shipping code

- **Currently focused on**: building AI-native systems where **digital workers own entire operational functions** — autonomous teammates that observe, decide, escalate, and report, rather than chat assistants triggered on demand. The goal is measurable business outcomes: faster deal cycles, lower OPEX, and human teams freed for higher-leverage work. Applied to **B2B FinTech operations**, **CBDC and tokenized settlements**, and **cross-border payment infrastructure**. Published expert profile and articles on this thesis at [RBC Companies](https://companies.rbc.ru/experts/27146/denis-ermilov/)
- Author of ***Digital Bank*** (Amazon, 2023) — handbook on banking digital transformation
- **IEEE Senior Member** (#99277800) · **Skolkovo Foundation expert** since 2023 · **FSI grant jury member**
- 10+ peer-reviewed papers indexed at [Google Scholar](https://scholar.google.com/citations?user=CHw8i34AAAAJ&hl=en) and [ORCID](https://orcid.org/0009-0007-8342-558X)
- **Yandex Practicum** — System Architect program (2025) · **Karpov.Courses** — ML & System Design · **GoPractice** — Product Management Simulator · **ICAgile** Certified Professional
- Languages: Russian (native), English (C1)
- Open to interesting conversations on [LinkedIn](https://www.linkedin.com/in/denis-ermilov-42291a1b)

---

### GitHub at a glance

![Profile views](https://komarev.com/ghpvc/?username=eiler2005&style=flat&label=Profile+views&color=24292e)
![Followers](https://img.shields.io/github/followers/eiler2005?style=flat&logo=github&label=Followers&labelColor=24292e)
![Total Stars](https://img.shields.io/github/stars/eiler2005?style=flat&logo=github&label=Total%20Stars&labelColor=24292e)

---

<sub>This profile is maintained at [eiler2005/eiler2005](https://github.com/eiler2005/eiler2005).</sub>
