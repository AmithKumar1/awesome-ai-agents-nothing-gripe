# Evaluation and Observability

Before an agent touches production, you need two things: a way to score it (evals) and a way to watch it (observability). All entries: [main list](../README.md#evals--benchmarks) and [main list](../README.md#agent-observability).

## Benchmarks — what to measure

Pick benchmarks that match the agent's job:

- **General assistants** (web search + tools + reasoning): [GAIA](../README.md#evals--benchmarks) (real-world questions, difficulty tiers).
- **Coding agents**: [SWE-bench](../README.md#evals--benchmarks) (resolve real GitHub issues; the Verified subset is the cleaned leaderboard), [SWE-agent](../README.md#autonomous-coding-agents) as the academic reference implementation.
- **Browser agents**: [WebArena](../README.md#evals--benchmarks) (realistic web tasks; VisualWebArena adds visual reasoning), [ClawBench](../README.md#evals--benchmarks) (everyday consumer tasks, 2026).
- **Computer-use agents**: [OSWorld](../README.md#evals--benchmarks) (the standard OS-level benchmark), [AndroidWorld](../README.md#evals--benchmarks) (mobile).
- **Tool-calling accuracy**: [BFCL](../README.md#evals--benchmarks) (Berkeley Function Calling Leaderboard; AST-matched at scale), [ToolBench](../README.md#evals--benchmarks) (breadth across thousands of real APIs).
- **Customer-support agents**: [τ-bench](../README.md#evals--benchmarks) (realistic tools + user simulator).
- **Holistic multi-domain**: [AgentBench](../README.md#evals--benchmarks) (8 environments: OS, DB, knowledge graphs, games).

Vendor-reported benchmark numbers (e.g. "first to cross OSWorld") should be treated as marketing until independently reproduced — leaderboards, not press releases, are the source of truth.

## Observability — what to watch

- [LangSmith](../README.md#agent-observability): tracing + evals + prompt management, best for LangChain/LangGraph stacks.
- [Langfuse](../README.md#agent-observability): open-source tracing, evals, prompt management, OTel ingestion. Acquired by ClickHouse (Jan 2026).
- [Arize Phoenix](../README.md#agent-observability): OTel-native tracing with RAG/agent evaluation; strong notebook ergonomics.
- [Helicone](../README.md#agent-observability) is in maintenance mode since March 2026 — fine if you're already on it, avoid for greenfield.

Framework-native options also exist: the [OpenAI Agents SDK](../README.md#agent-frameworks--sdks) ships built-in tracing, and most managed platforms ([Vertex AI Agent Builder](../README.md#agent-development-platforms), [Azure AI Foundry](../README.md#agent-development-platforms)) bundle observability.

## The production checklist

1. **Trajectory evals**, not just final answers — did the agent take a sane path? (This is what tools like LangSmith and Phoenix are built to inspect.)
2. **Guardrails** ([NeMo Guardrails](../README.md#agent-security--guardrails), [Lakera Guard](../README.md#agent-security--guardrails)) on inputs and outputs.
3. **Sandboxed execution** ([E2B](../README.md#agent-sandboxes--tool-platforms), [Firecracker](../README.md#agent-sandboxes--tool-platforms)) for any agent-generated code.
4. **Human-in-the-loop** checkpoints on consequential actions — every serious computer-use system ([Anthropic Computer Use](../README.md#computer-use--gui-agents), [OpenAI CUA](../README.md#computer-use--gui-agents)) treats this as non-optional.
