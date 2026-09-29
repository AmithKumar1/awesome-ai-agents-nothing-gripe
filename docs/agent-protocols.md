# Agent Protocols

The protocols that let agents connect to tools, delegate to each other, and render in frontends. All entries: [main list](../README.md#communication-protocols).

## The map

| Protocol | What it standardizes | Think of it as |
|---|---|---|
| [MCP](https://modelcontextprotocol.io) | Agent ↔ tools/data/prompts | "USB-C for AI" — how an agent reaches the outside world |
| [A2A](https://a2a-protocol.org) | Agent ↔ agent delegation | How opaque agents discover and hire each other |
| [ACP](https://zed.dev/acp) (Zed) | Editor ↔ coding agent | How an IDE talks to any coding agent |
| [AG-UI](https://github.com/ag-ui-protocol/ag-ui) | Agent ↔ frontend | How agent state streams into a UI |
| [ANP](https://agent-network-protocol.com/) | Agent identity & discovery | Decentralized identity (`did:wba`) for agents on the open internet |
| [AP2](https://ap2-protocol.org) | Agent payments | Scoped, revocable payment mandates for agentic commerce |
| [AGENTS.md](https://github.com/agentsmd/agents.md) | Repo ↔ coding agent | A README for robots — repo conventions agents read automatically |

## When each matters

- **Building any agent that uses tools** (files, APIs, databases): MCP is the default. It's the dominant tool-integration standard and is now under Linux Foundation governance (Agentic AI Foundation, Dec 2025).
- **Agents delegating to other agents** (different teams, vendors, or trust boundaries): A2A. Use MCP for tools, A2A for agent-to-agent work — they're complementary, not competing.
- **Building a coding agent that lives in editors**: ACP — one protocol, many editors.
- **Building a chat/product UI over an agent**: AG-UI streams state, events, and human-in-the-loop interactions into the frontend.
- **Agents transacting** (booking, buying, paying): AP2 gives scoped, revocable payment authorization instead of handing the agent a credit card.
- **Open-internet agent identity** (not inside one company's platform): ANP.
- **Making your repo agent-friendly**: add an `AGENTS.md` — it's read by OpenCode, Crush, Cline, Cursor, and others.

## Governance notes

- MCP was donated to the Linux Foundation in December 2025 — the clearest signal it's the durable standard.
- A2A reached v1.0.0 under the Linux Foundation; IBM's ACP merged into A2A (Aug 2025). Note the acronym collision: **IBM ACP** (now part of A2A) is unrelated to **Zed's ACP** (Agent Client Protocol, editor ↔ agent).
- AGENTS.md is also under Agentic AI Foundation governance.
