# Choosing an Agent Framework

There is no single best agent framework — only the one that fits your stack, team, and production constraints. This guide maps the [frameworks in the main list](../README.md#agent-frameworks--sdks) to decisions.

## Start with your constraints

**Language and stack.** TypeScript shops: [Mastra](../README.md#agent-frameworks--sdks) (full agent framework) or the [Vercel AI SDK](../README.md#agent-frameworks--sdks) (streaming-first SDK for agent UIs). Python shops: the field is wide — see below. .NET/C# shops: [Semantic Kernel](../README.md#agent-frameworks--sdks) or the converged [Microsoft Agent Framework](../README.md#agent-frameworks--sdks).

**Model.** If you're all-in on one vendor, its first-party SDK is the path of least resistance: [Claude Agent SDK](../README.md#agent-frameworks--sdks) for Claude (MCP-native), [OpenAI Agents SDK](../README.md#agent-frameworks--sdks) for OpenAI (handoff-centric, tracing built in), [Google ADK](../README.md#agent-frameworks--sdks) for Gemini (A2A built in, pairs with Vertex AI). If you're model-agnostic or multi-model, pick a neutral framework: [LangGraph](../README.md#agent-frameworks--sdks), [CrewAI](../README.md#agent-frameworks--sdks), [Pydantic-AI](../README.md#agent-frameworks--sdks), [smolagents](../README.md#agent-frameworks--sdks).

**Cloud.** Each cloud has a native agent path: AWS → [Amazon Strands Agents](../README.md#agent-frameworks--sdks) (framework) + [Bedrock Agents / AgentCore](../README.md#agent-development-platforms) (managed runtime); Google Cloud → [Google ADK](../README.md#agent-frameworks--sdks) + [Vertex AI Agent Builder](../README.md#agent-development-platforms); Azure → [Semantic Kernel](../README.md#agent-frameworks--sdks) / [Microsoft Agent Framework](../README.md#agent-frameworks--sdks) + [Azure AI Foundry](../README.md#agent-development-platforms).

## The decision tree

1. **Do you need multi-agent coordination, or one agent with tools?** For a single agent with tools, a minimal library ([smolagents](../README.md#agent-frameworks--sdks), [Pydantic-AI](../README.md#agent-frameworks--sdks)) or a vendor SDK is enough. For coordinated agents, see [Multi-Agent Orchestration](../README.md#multi-agent-orchestration): [LangGraph](../README.md#agent-frameworks--sdks) (graphs, checkpointing), [CrewAI](../README.md#agent-frameworks--sdks) (role-based teams), [Google ADK](../README.md#agent-frameworks--sdks) (hierarchical), [AG2](../README.md#agent-frameworks--sdks) (conversable agents).
2. **Is your workload RAG-centric?** [LlamaIndex](../README.md#agent-frameworks--sdks) and [Haystack](../README.md#agent-frameworks--sdks) are document-first frameworks; start there if retrieval quality is the bottleneck.
3. **Do you need durable, long-running execution?** Look at [LangGraph's checkpointing](../README.md#agent-frameworks--sdks) or [Kitaru](../README.md#multi-agent-orchestration) for replay and stateful flows.
4. **Do you want to optimize prompts automatically instead of hand-tuning?** [DSPy](../README.md#agent-frameworks--sdks) compiles LM pipelines rather than relying on hand-written prompts.
5. **Enterprise .NET or Microsoft 365?** [Microsoft Agent Framework](../README.md#agent-frameworks--sdks) is the converged path; AutoGen is legacy (continued as [AG2](../README.md#agent-frameworks--sdks)).

## Prototype vs production

For prototypes, pick whatever your team already knows — [LangChain](../README.md#agent-frameworks--sdks), [CrewAI](../README.md#agent-frameworks--sdks), or a vendor SDK. For production, the questions that matter are: state management and checkpointing, evals ([see guide](evaluation-and-observability.md)), observability ([LangSmith](../README.md#agent-observability), [Langfuse](../README.md#agent-observability), [Arize Phoenix](../README.md#agent-observability)), guardrails ([NeMo Guardrails](../README.md#agent-security--guardrails)), and how the agent is hosted ([platforms](../README.md#agent-development-platforms) or your own infra with [sandboxes](../README.md#agent-sandboxes--tool-platforms)).

Avoid building new work on [Flowise](../README.md#agent-development-platforms) (sunsetting), [OpenAI Swarm](../README.md#multi-agent-orchestration) (archived), or [Helicone](../README.md#agent-observability) (maintenance mode) — see [status changes](status-changes.md).
