# Hi, I''m Parag 👋

Senior software engineer. I work on the unglamorous infrastructure *around* AI
systems - the parts that decide whether a model is safe to ship, cheap to run, and
hard to break.

Most of these started as a problem I hit at work and couldn''t find a clean, small
answer for, so I wrote one. Each is real, tested code with a README that explains
the *why* - and, where it earns one, a design doc on the trade-offs and benchmarks
with actual numbers.

### Start here

**[llm-in-production](https://github.com/parag-labs/llm-in-production)** - field
notes on the seven things that will bite an LLM feature in production (cost, evals,
prompt injection, drift, grounding, rate limits, agent guardrails), each with the
pattern that fixes it and the small tool that implements it. It ties the rest of
the work together.

### A few things I''ve built (all under [parag-labs](https://github.com/parag-labs))

| | |
|---|---|
| **[ledger-rag](https://github.com/parag-labs/ledger-rag)** | verifiable RAG - every answer ships a tamper-evident proof |
| **[agent-guard](https://github.com/parag-labs/agent-guard)** | zero-trust runtime sandbox for tool-calling agents |
| **[token-lens](https://github.com/parag-labs/token-lens)** | attribute LLM cost & latency to feature / tenant / model |
| **[mini-raft](https://github.com/parag-labs/mini-raft)** and **[multi-raft](https://github.com/parag-labs/multi-raft)** | Raft consensus, and the layer that runs thousands of groups |
| **[deterministic-sim-testing](https://github.com/parag-labs/deterministic-sim-testing)** | replay any distributed-systems bug from a single seed |
| **[gpu-flock](https://github.com/parag-labs/gpu-flock)** | a few thousand boids flocking entirely on the GPU ([demo](https://parag-labs.github.io/gpu-flock/)) |

A lot of the cores are written three times - Python, C#, and Java. That''s not for
show: they''re plain algorithms (a Merkle proof, a point-in-time join, a drift
statistic), and porting them keeps me honest that the logic is the logic, not a
trick of one language''s libraries.

Outside the org, I also maintain
**[flatwire](https://github.com/flatwire-io/flatwire)** - streaming serialization
with one identical API across Python, Node, .NET, Rust, Go, and Java.

- 🔭 Building small, tested tools in Python, C#, and Java
- 🧰 Backend · distributed systems · applied cryptography · LLM tooling
- 💬 [linkedin.com/in/paragsawant](https://www.linkedin.com/in/paragsawant/)