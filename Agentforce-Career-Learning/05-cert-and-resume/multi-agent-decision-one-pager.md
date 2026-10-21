# Multi-Agent Decision One-Pager

Fill after Project D. Use this in interviews.

## Use case

> _______________________________________________

## Decision: one agent vs multi-agent (SOMA)

| Criterion | Single agent (many topics) | Multi-agent (SOMA) |
| --- | --- | --- |
| Permissions differ by job | Hard to isolate | Clear boundaries |
| Specialist depth / prompts | One bloated instruction set | Focused specialists |
| Blast radius of mistakes | Higher | Contained |
| Latency / cost | Usually lower | Higher (handoffs) |
| Ops complexity | Lower | Higher |

**My choice for this use case:** ____________________  
**Why:** ____________________

## Protocols (exam + architecture literacy)

| Term | What it means (my words) | When I’d care |
| --- | --- | --- |
| **SOMA** | Single-org multi-agent architecture | Multiple agents in one Salesforce org |
| **MCP** | Model Context Protocol — standard way tools/context are exposed to models | Integrating tools/servers consistently |
| **A2A** | Agent-to-Agent protocol — agents communicating/coordinating | Cross-agent handoffs / interoperability |

## Tradeoff summary for THIS demo

| Dimension | Monolith agent | Coordinated agents |
| --- | --- | --- |
| Latency | | |
| Cost | | |
| Control / least privilege | | |
| Debuggability | | |
| Speed of delivery for team | | |

## Why multi-agent made work faster here

> (e.g. Intake removes classification load from specialists; specialists stay grounded and short; executor writes are rare and gated — humans spend time on exceptions only.)

## When I would NOT split

- One narrow job, same permissions, low traffic
- Team cannot operate two configs yet
- No clear handoff contract
