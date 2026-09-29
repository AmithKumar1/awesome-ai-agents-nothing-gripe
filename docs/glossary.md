# Glossary

The terms this ecosystem can't stop inventing, defined once.

- **Agent** — an AI system that perceives, decides, and acts toward a goal, typically by looping: observe → reason → use tools → observe again.
- **Agentic** — the industry adjective for "built around agents" (agentic AI, agentic commerce, agentic IDE).
- **A2A (Agent2Agent)** — open protocol for discovery, delegation, and artifacts between opaque agents. See [protocols](agent-protocols.md).
- **ACP** — ambiguous acronym: (1) IBM's Agent Communication Protocol, merged into A2A; (2) Zed's Agent Client Protocol, editor ↔ coding agent. This list uses ACP for Zed's.
- **AG-UI** — protocol for streaming agent state/events into frontends.
- **AGENTS.md** — portable repo-guidance file that coding agents read automatically.
- **ANP (Agent Network Protocol)** — decentralized agent identity/discovery (`did:wba`).
- **AP2 (Agent Payments Protocol)** — scoped, revocable payment authorization for agentic commerce.
- **Checkpointing** — persisting agent state mid-run so execution can pause, resume, or replay (core to LangGraph and durable-execution frameworks like Kitaru).
- **Computer use** — agents that operate a GUI via screenshots and coordinates, like a human (Anthropic Computer Use, OpenAI CUA).
- **CUA** — Computer-Using Agent; OpenAI's model/API for computer use.
- **Eval** — a benchmark or test suite that scores agent behavior (SWE-bench, GAIA, τ-bench…).
- **GAIA** — general-assistant benchmark: real-world questions needing search + tools + reasoning.
- **Guardrails** — programmable constraints on agent inputs/outputs (NeMo Guardrails, Lakera Guard).
- **Handoff** — passing control (and context) from one agent to another; the core primitive of the OpenAI Agents SDK and Swarm.
- **MCP (Model Context Protocol)** — standard for connecting agents to tools, data, prompts, resources. See [protocols](agent-protocols.md).
- **Memory (agent)** — persistent context across sessions: short-term (mem0), knowledge-graph (Zep/Graphiti), self-editing blocks (Letta).
- **Observability** — tracing and debugging agent runs (LangSmith, Langfuse, Phoenix).
- **Orchestration** — coordinating multiple agents: supervisors, swarms, hierarchies, group chats.
- **OSWorld** — the standard OS-level computer-use benchmark/environment.
- **RAG (retrieval-augmented generation)** — grounding agent answers in retrieved documents; the specialty of LlamaIndex and Haystack.
- **Sandbox** — isolated execution environment for untrusted agent code (E2B, Firecracker microVMs).
- **SOP (standard operating procedure)** — MetaGPT's conceit: agents follow role-based SOPs like a software company.
- **SWE-bench** — the code-agent gold standard: resolve real GitHub issues.
- **τ-bench (tau-bench)** — customer-support agent eval with a simulated user.
- **Tool calling / function calling** — the mechanism by which an agent invokes external functions; measured by BFCL and ToolBench.
- **Trajectory** — the full sequence of an agent's actions and observations; what you inspect when debugging.
