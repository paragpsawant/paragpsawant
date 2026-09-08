# Hi, I'm Parag 👋

**AI / backend engineer.** I build the deterministic control plane *around*
large language models — the layer that decides whether a model is safe to ship,
cheap to run, grounded in real evidence, and hard to break.

> My one design rule, in every agent I ship: **the model proposes; deterministic,
> tested code validates and executes.** The interesting engineering isn't the
> prompt — it's the guardrail the prompt can't talk its way past.

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)
![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
&nbsp;
![LLM Agents](https://img.shields.io/badge/LLM_Agents-6E56CF?style=flat-square)
![RAG](https://img.shields.io/badge/RAG-0EA5E9?style=flat-square)
![Evals](https://img.shields.io/badge/Evals_&_Guardrails-16A34A?style=flat-square)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

I'm a Senior Software Engineer at Microsoft (Copilot Studio, Copilot for Finance,
Power Platform), and on nights and weekends I build small, tested tools for the
unglamorous parts of putting AI in production. Everything below is real code with
a README that explains the *why*, tests that assert the hard part, and — where it
earns one — a design doc with trade-offs and reproducible benchmarks.

### Start here

**[llm-in-production](https://github.com/parag-labs/llm-in-production)** — field
notes on the seven things that will bite an LLM feature in production (cost, evals,
prompt injection, drift, grounding, rate limits, agent guardrails), each with the
pattern that fixes it and the small tool that implements it. If you read one thing,
read its pre-launch checklist.

### What I focus on

- **Agents that do real work, safely** — planner/executor splits with a policy gate
  and human-in-the-loop approval: [operations-agent](https://github.com/parag-labs/operations-agent),
  [incident-commander](https://github.com/parag-labs/incident-commander) (Go),
  [agent-guard](https://github.com/parag-labs/agent-guard) (zero-trust tool sandbox),
  [guardianforge](https://github.com/parag-labs/guardianforge) (fleet governance, Go + C#).
- **Grounded retrieval** — RAG you can prove: [ledger-rag](https://github.com/parag-labs/ledger-rag)
  ships a tamper-evident proof with every answer;
  [knowledge-workspace](https://github.com/parag-labs/knowledge-workspace) cites every claim.
- **Ship-it discipline** — [eval-forge](https://github.com/parag-labs/eval-forge) (CI eval gate),
  [prompt-shield](https://github.com/parag-labs/prompt-shield) (injection in / PII out),
  [token-lens](https://github.com/parag-labs/token-lens) (cost attribution),
  [quota-gate](https://github.com/parag-labs/quota-gate) (per-tenant budgets),
  [drift-watch](https://github.com/parag-labs/drift-watch) (PSI/KL drift).
- **Systems underneath** — consensus and correctness: [coracle](https://github.com/parag-labs/coracle)
  (Raft) + [flotilla](https://github.com/parag-labs/flotilla) (thousands of groups on one node),
  [deterministic-sim-testing](https://github.com/parag-labs/deterministic-sim-testing),
  [durable-execution](https://github.com/parag-labs/durable-execution).
- **On-device AI & interfaces** — ten Flutter apps with tested, deterministic cores,
  each with a live demo (on-device intelligence, health, privacy, adaptive UI).

### A few things I've built — with live demos

| Project | What it is | |
|---|---|---|
| **[agent-trace](https://github.com/parag-labs/agent-trace)** | visual timeline + replay for agent runs — where a run spent time, tokens, and money, then diff two runs | [▶ demo](https://parag-labs.github.io/agent-trace/) |
| **[agentforge-dashboard](https://github.com/parag-labs/agentforge-dashboard)** | register, monitor, and deeply compare agents — radar + trade-off insights, spatial agent map | [▶ demo](https://parag-labs.github.io/agentforge-dashboard/) |
| **[ledger-rag](https://github.com/parag-labs/ledger-rag)** | verifiable RAG — every answer ships a tamper-evident cryptographic proof (Python/C#/Java) | |
| **[agent-guard](https://github.com/parag-labs/agent-guard)** | zero-trust runtime sandbox for tool-calling agents: least-privilege policy + signed audit log | |
| **[infra-optimizer](https://github.com/parag-labs/infra-optimizer)** | AI infra optimizer in Rust — the model only picks among candidates Rust has already proven safe | |
| **[gpu-flock](https://github.com/parag-labs/gpu-flock)** | a few thousand boids flocking entirely on the GPU with WebGPU compute shaders | [▶ demo](https://parag-labs.github.io/gpu-flock/) |

More — ~40 focused projects, 13 live demos — under **[parag-labs](https://github.com/parag-labs)**.

### On writing cores three times

A lot of the cores are written in Python, **and** C#, **and** Java. That's not for
show: they're plain algorithms (a Merkle proof, a point-in-time join, a drift
statistic), and porting them keeps me honest that the logic is the logic — not a
trick of one language's libraries. Outside the org I also maintain
**[flatwire](https://github.com/flatwire-io/flatwire)** — streaming serialization
with one identical API across Python, Node, .NET, Rust, Go, and Java, published to
PyPI, npm, NuGet, crates.io, Maven Central, and Go.

### Reach me

- 🧰 Backend · distributed systems · applied cryptography · LLM & agent tooling
- ☁️ Azure (AKS, Container Apps, Cosmos DB), Docker/Kubernetes, CI/CD
- 💬 [linkedin.com/in/paragsawant](https://www.linkedin.com/in/paragsawant/)
