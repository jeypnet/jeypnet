# Connecting AI assistants to a sports marketplace

**Context:** JoGo.Team · sports marketplace · AI integration  
**My contribution:** AI-assisted solution design, implementation, testing, and operation of the platform's MCP integration.

## The problem

An assistant needs current platform information to help someone find a game. It needs a structured way to ask the platform what is actually available.

## The solution

The Model Context Protocol (MCP) integration gives compatible assistants a tool interface to JoGo.Team. The public discovery surface describes the available tools so an assistant can select a relevant operation and supply its arguments.

```text
Person asks about a game
        |
Assistant selects a platform tool
        |
JoGo returns structured information
        |
Assistant uses the returned information in its answer
```

## What this demonstrates

- Turning a customer workflow into a tool interface an assistant can use.
- Designing descriptions and schemas to reduce ambiguity about available actions.
- Connecting the assistant experience to an operational product.
- Separating public discovery from actions that require authorization.

## Inspect the public interface

[Visit JoGo.Team](https://jogo.team). Technical reviewers can inspect tool discovery using this read-only request; it does not book or publish a game:

```bash
curl --max-time 3 -sS -X POST https://jogo.team/mcp \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

The deployed interface can evolve. Use its current response for tool names and availability. This case study documents the integration approach without publishing production source code, customer records, internal logs, credentials, or adoption figures.

[Back to portfolio](../README.md)
