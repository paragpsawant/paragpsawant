# Hi, I'm Parag 👋

**Senior software engineer — I build across the whole stack, centered on AI.**
From speculative decoding and verifiable RAG to ten on-device mobile apps and a
WebGPU renderer: the deterministic AI core *and* the mobile, web, and GPU
surfaces on top of it.

> My one design rule, in every agent I ship: **the model proposes; deterministic,
> tested code validates and executes.** The interesting engineering isn't the
> prompt — it's the guardrail the prompt can't talk its way past.

**44 repos · 1,140+ tests green in CI · 14 live demos · cores in 7 languages · 8 with reproducible benchmarks**

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)
![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![WebGPU](https://img.shields.io/badge/WebGPU-005A9C?style=flat-square&logo=webgpu&logoColor=white)
&nbsp;
![LLM Agents](https://img.shields.io/badge/LLM_Agents-6E56CF?style=flat-square)
![RAG](https://img.shields.io/badge/RAG-0EA5E9?style=flat-square)
![Distributed Systems](https://img.shields.io/badge/Distributed_Systems-334155?style=flat-square)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

> **Open to Senior / Staff Software Engineering roles** — AI systems, backend &
> distributed systems, and the product surfaces (web, mobile, GPU) on top.

<p align="center">
  <a href="https://parags.dev"><img src="https://img.shields.io/badge/Portfolio-parags.dev-6E56CF?style=for-the-badge&logo=cloudflare&logoColor=white" alt="Portfolio — parags.dev"/></a>
  <a href="https://huggingface.co/cleanroom-ai"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20New-cleanroom--ai-FFD21E?style=for-the-badge" alt="New — cleanroom-ai privacy tools on Hugging Face"/></a>
</p>

> 🆕 **[cleanroom-ai](https://huggingface.co/cleanroom-ai)**: clean it before you share it. Six privacy tools whose
> OCR, speech and PII models run **entirely in your browser**, so nothing gets uploaded:
> [Screenshot Redactor](https://huggingface.co/spaces/cleanroom-ai/pii-privacy-redaction) ·
> [Log Scrubber](https://huggingface.co/spaces/cleanroom-ai/log-secret-scrubber) ·
> [PDF Redactor](https://huggingface.co/spaces/cleanroom-ai/pdf-redaction) ·
> [Audio Redactor](https://huggingface.co/spaces/cleanroom-ai/audio-pii-redaction) ·
> [Photo Share-Safe](https://huggingface.co/spaces/cleanroom-ai/photo-exif-privacy) ·
> [Video Redactor](https://huggingface.co/spaces/cleanroom-ai/video-redaction)

<p align="center">
  <a href="https://parag-labs.github.io/agentforge-dashboard/"><img src="assets/hero-agentforge.png" width="49%" alt="AgentForge — agent-fleet cockpit with cost, trust, and grounded insights (live demo)"/></a>
  <a href="https://parag-labs.github.io/agent-trace/"><img src="assets/hero-agent-trace.png" width="49%" alt="agent-trace — per-run cost/token/latency timeline with a budget gate (live demo)"/></a>
</p>
<p align="center">
  <a href="https://parag-labs.github.io/aura-surface/"><img src="assets/mobile-aura.png" width="24%" alt="AuraSurface — emotion-responsive mobile UI (live demo)"/></a>
  <a href="https://parag-labs.github.io/morph-ui/"><img src="assets/mobile-morph.png" width="24%" alt="MorphUI — generative interface engine (live demo)"/></a>
  <a href="https://parag-labs.github.io/thumb-sphere/"><img src="assets/mobile-thumb.png" width="24%" alt="ThumbSphere — thumb-zone mobile design system (live demo)"/></a>
</p>
<p align="center"><sub><b>Every image links to a live demo.</b> Top: AI dashboards (<a href="https://parag-labs.github.io/agentforge-dashboard/">AgentForge</a>, <a href="https://parag-labs.github.io/agent-trace/">agent-trace</a>). Bottom: three of ten on-device <a href="https://github.com/parag-labs">Flutter apps</a> — plus a <a href="https://parag-labs.github.io/gpu-flock/">WebGPU boids renderer</a>.</sub></p>

I'm a Senior Software Engineer at Microsoft, and on nights and weekends I build
small, tested tools for the unglamorous parts of putting AI in production.
Everything below is real code with a README that explains the *why*, tests that
assert the hard part, and — where it earns one — a design doc with trade-offs and
reproducible benchmarks.

### At Microsoft (2018–present)

Production AI and platform work at scale — the day job behind the side projects:

- **Copilot Studio** — shipped an in-house AI agent (Workflows Agents) into Microsoft
  365 Copilot, leading the First Run Experience squad; re-architected a large
  enterprise service into distributed microservices and built the reverse-proxy layer
  routing between customer-managed and data planes — systems used globally at
  enterprise scale.
- **Zero-Trust platform** — built three production AI agents on the team: an **E2E failure-
  triage agent** that auto-diagnoses failed pipeline runs and files bugs (turning hours
  of manual triage into minutes), a PR review & security agent, and a **RAG** architecture
  knowledge agent with citation-backed answers across repos and specs.
- **Copilot for Finance** — greenfield microservices (telemetry, metadata store, auth),
  RESTful APIs, App Store publication, and CI/CD automation for faster, more frequent
  releases.

### Start here

**[llm-in-production](https://github.com/parag-labs/llm-in-production)** — field
notes on the seven things that will bite an LLM feature in production (cost, evals,
prompt injection, drift, grounding, rate limits, agent guardrails), each with the
pattern that fixes it and the small tool that implements it. If you read one thing,
read its pre-launch checklist.

The whole model of how these fit on the request path:

```mermaid
flowchart LR
  U["Request"] --> IN["Guard input<br/>(prompt-shield)"]:::g
  IN --> Q["Budget check<br/>(quota-gate · token-lens)"]:::g
  Q --> M["Model"]:::m
  M --> OUT["Redact output<br/>(prompt-shield)"]:::g
  OUT --> R["Response"]:::ok
  M -.->|trace + cost| LOGS["Attribution<br/>(agent-trace)"]:::ok
  M -.->|grounded by| RAG["Cited retrieval<br/>(ledger-rag)"]:::ok
  classDef g fill:#faf5ff,stroke:#a855f7,color:#4c1d95;
  classDef m fill:#eff6ff,stroke:#3b82f6,color:#1e3a8a;
  classDef ok fill:#f0fdf4,stroke:#22c55e,color:#14532d;
```

### What I focus on

- **Agents that do real work, safely** — planner/executor splits with a policy gate
  and human-in-the-loop approval: [operations-agent](https://github.com/parag-labs/operations-agent),
  [incident-commander](https://github.com/parag-labs/incident-commander) (Go),
  [agent-guard](https://github.com/parag-labs/agent-guard) (zero-trust tool sandbox),
  [guardianforge](https://github.com/parag-labs/guardianforge) (fleet governance, Go + C#).
- **Grounded retrieval** — RAG you can prove: [ledger-rag](https://github.com/parag-labs/ledger-rag)
  ships a tamper-evident proof with every answer;
  [knowledge-workspace](https://github.com/parag-labs/knowledge-workspace) cites every claim;
  [repo-index](https://github.com/parag-labs/repo-index) turns any repo into a citable knowledge
  base and answers only from retrieved source.
- **Ship-it discipline** — [eval-forge](https://github.com/parag-labs/eval-forge) (CI eval gate),
  [prompt-shield](https://github.com/parag-labs/prompt-shield) (injection in / PII out),
  [token-lens](https://github.com/parag-labs/token-lens) (cost attribution),
  [quota-gate](https://github.com/parag-labs/quota-gate) (per-tenant budgets),
  [drift-watch](https://github.com/parag-labs/drift-watch) (PSI/KL drift).
- **Systems underneath** — consensus and correctness: [coracle](https://github.com/parag-labs/coracle)
  (Raft) + [flotilla](https://github.com/parag-labs/flotilla) (thousands of groups on one node),
  [deterministic-sim-testing](https://github.com/parag-labs/deterministic-sim-testing),
  [durable-execution](https://github.com/parag-labs/durable-execution).
- **Model internals & LLM correctness** — [spec-decode](https://github.com/parag-labs/spec-decode)
  implements speculative decoding from scratch and *proves* it's exact (the emitted
  distribution provably equals sampling the target), with honest speedup benchmarks;
  [metamorph](https://github.com/parag-labs/metamorph) is metamorphic testing for LLMs —
  invariance under paraphrase, reorder, and negation, shrinking each failure to a minimal prompt;
  [honest-transformer](https://github.com/parag-labs/honest-transformer) is a transformer forward
  pass with **bit-identical logits across Python, C#, and Java**; and
  [batch-invariant](https://github.com/parag-labs/batch-invariant) shows — and fixes — the
  reduction-order bug that makes a decoded token depend on its batch-mates.
- **Interfaces, mobile & graphics** — ten on-device **Flutter** apps, each a tested,
  deterministic core with a live demo ([intent-canvas](https://github.com/parag-labs/intent-canvas),
  [morph-ui](https://github.com/parag-labs/morph-ui), [aura-surface](https://github.com/parag-labs/aura-surface),
  [thumb-sphere](https://github.com/parag-labs/thumb-sphere), and more); **web** dashboards in
  React / Next / React Flow (the agent tooling above); and [gpu-flock](https://github.com/parag-labs/gpu-flock),
  thousands of boids computed and drawn entirely on the GPU with **WebGPU** compute shaders.

### Featured work

| Project | What it is | | CI |
|---|---|---|---|
| **[screenshot-redactor](https://github.com/cleanroom-ai/screenshot-redactor)** | hide API keys, passwords, PII, faces & QR codes in screenshots, 100% in the browser; OCR + PII models on ONNX Runtime Web, nothing uploaded | [▶ demo](https://huggingface.co/spaces/cleanroom-ai/pii-privacy-redaction) | ![ci](https://github.com/cleanroom-ai/screenshot-redactor/actions/workflows/ci.yml/badge.svg) |
| **[log-secret-scrubber](https://github.com/cleanroom-ai/log-secret-scrubber)** | scrub API keys, tokens, cookies, emails & IPs from logs, .env files and HAR captures before sharing; structure-aware, 100% in the browser | [▶ demo](https://huggingface.co/spaces/cleanroom-ai/log-secret-scrubber) | ![ci](https://github.com/cleanroom-ai/log-secret-scrubber/actions/workflows/ci.yml/badge.svg) |
| **[pdf-redaction](https://github.com/cleanroom-ai/pdf-redaction)** | true PDF redaction: detects PII & secrets, flattens pages, then verifies no text remains; nothing uploaded | [▶ demo](https://huggingface.co/spaces/cleanroom-ai/pdf-redaction) | ![ci](https://github.com/cleanroom-ai/pdf-redaction/actions/workflows/ci.yml/badge.svg) |
| **[audio-pii-redaction](https://github.com/cleanroom-ai/audio-pii-redaction)** | bleeps names, phone numbers, card numbers & emails in recordings with Whisper + PII NER running in the browser | [▶ demo](https://huggingface.co/spaces/cleanroom-ai/audio-pii-redaction) | ![ci](https://github.com/cleanroom-ai/audio-pii-redaction/actions/workflows/ci.yml/badge.svg) |
| **[photo-exif-privacy](https://github.com/cleanroom-ai/photo-exif-privacy)** | strips GPS, camera serials & thumbnails from photos, and blurs faces & plates, entirely on-device | [▶ demo](https://huggingface.co/spaces/cleanroom-ai/photo-exif-privacy) | ![ci](https://github.com/cleanroom-ai/photo-exif-privacy/actions/workflows/ci.yml/badge.svg) |
| **[video-redaction](https://github.com/cleanroom-ai/video-redaction)** | finds and tracks keys, names, emails & faces through screen recordings, then re-encodes a redacted WebM in the browser | [▶ demo](https://huggingface.co/spaces/cleanroom-ai/video-redaction) | ![ci](https://github.com/cleanroom-ai/video-redaction/actions/workflows/ci.yml/badge.svg) |
| **[agent-trace](https://github.com/parag-labs/agent-trace)** | visual timeline + replay for agent runs — where a run spent time, tokens, and money, then diff two runs | [▶ demo](https://parag-labs.github.io/agent-trace/) | ![ci](https://github.com/parag-labs/agent-trace/actions/workflows/build.yml/badge.svg) |
| **[agentforge-dashboard](https://github.com/parag-labs/agentforge-dashboard)** | register, monitor, and deeply compare agents — radar + trade-off insights, spatial agent map | [▶ demo](https://parag-labs.github.io/agentforge-dashboard/) | ![ci](https://github.com/parag-labs/agentforge-dashboard/actions/workflows/ci.yml/badge.svg) |
| **[ledger-rag](https://github.com/parag-labs/ledger-rag)** | verifiable RAG — every answer ships a tamper-evident cryptographic proof (Python/C#/Java) | | ![ci](https://github.com/parag-labs/ledger-rag/actions/workflows/tests.yml/badge.svg) |
| **[agent-guard](https://github.com/parag-labs/agent-guard)** | zero-trust runtime sandbox for tool-calling agents: least-privilege policy + signed audit log | | ![ci](https://github.com/parag-labs/agent-guard/actions/workflows/tests.yml/badge.svg) |
| **[infra-optimizer](https://github.com/parag-labs/infra-optimizer)** | AI infra optimizer in Rust — the model only picks among candidates Rust has already proven safe | | ![ci](https://github.com/parag-labs/infra-optimizer/actions/workflows/ci.yml/badge.svg) |
| **[gpu-flock](https://github.com/parag-labs/gpu-flock)** | a few thousand boids flocking entirely on the GPU with WebGPU compute shaders | [▶ demo](https://parag-labs.github.io/gpu-flock/) | ![ci](https://github.com/parag-labs/gpu-flock/actions/workflows/validate.yml/badge.svg) |
| **[intent-canvas](https://github.com/parag-labs/intent-canvas)** | intent-first mobile home — express a goal in plain language, get a living workspace of modules; on-device deterministic intent engine (Flutter) | [▶ demo](https://parag-labs.github.io/intent-canvas/) | ![ci](https://github.com/parag-labs/intent-canvas/actions/workflows/ci.yml/badge.svg) |

More — 44 focused projects, 14 live demos — under **[parag-labs](https://github.com/parag-labs)**.

### A deep-dive: verifiable RAG

Most RAG systems ask you to *trust* that an answer came from your corpus.
**[ledger-rag](https://github.com/parag-labs/ledger-rag)** makes it checkable: every
retrieved chunk is a leaf in a Merkle tree, and each answer ships an **inclusion
proof** binding it to a signed root — so a third party can verify the evidence set
wasn't altered after the fact, without re-reading the corpus. The design doc owns the
boundary honestly (*"tamper-evident ≠ tamper-proof"*, the way certificate transparency
does), and the same core is written three times — Python, C#, Java — so the property
is the property, not a trick of one language's crypto library.

### Measured, not asserted

Where performance is a claim, there's a committed script and a graph. Example — why
consistent hashing instead of `hash % N`, from
[consistent-hash](https://github.com/parag-labs/consistent-hash):

![remap cost: consistent hashing vs hash % N](https://raw.githubusercontent.com/parag-labs/consistent-hash/main/bench/results/remap_vs_modulo.png)

Adding a node to a 64-node cluster remaps **~1%** of keys with a consistent-hash ring;
plain `hash % N` remaps **~98.5%** — nearly the entire keyspace, every time. Eight
repos ship a `BENCHMARKS.md` like this, measured on a plain machine from a script you
can re-run.

### On writing cores three times

A lot of the cores are written in Python, **and** C#, **and** Java. That's not for
show: they're plain algorithms (a Merkle proof, a point-in-time join, a drift
statistic), and porting them keeps me honest that the logic is the logic — not a
trick of one language's libraries.

Outside the org I also maintain **[flatwire](https://github.com/flatwire-io/flatwire)** —
streaming serialization with one identical API across six languages, published to
every major registry:

![PyPI](https://img.shields.io/badge/PyPI-3775A9?style=flat-square&logo=pypi&logoColor=white)
![npm](https://img.shields.io/badge/npm-CB3837?style=flat-square&logo=npm&logoColor=white)
![NuGet](https://img.shields.io/badge/NuGet-004880?style=flat-square&logo=nuget&logoColor=white)
![crates.io](https://img.shields.io/badge/crates.io-000000?style=flat-square&logo=rust&logoColor=white)
![Maven Central](https://img.shields.io/badge/Maven_Central-C71A36?style=flat-square&logo=apachemaven&logoColor=white)
![Go](https://img.shields.io/badge/pkg.go.dev-00ADD8?style=flat-square&logo=go&logoColor=white)

### Reach me

- 🧰 Backend · distributed systems · applied cryptography · LLM & agent tooling
- ☁️ Azure (AKS, Container Apps, Cosmos DB), Docker/Kubernetes, CI/CD
- 🌐 Portfolio: [parags.dev](https://parags.dev)
- 💬 [linkedin.com/in/paragsawant](https://www.linkedin.com/in/paragsawant/)
