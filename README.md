# opencode-nats

NATS messaging plugin for [OpenCode](https://opencode.ai) — enables inter-agent communication via NATS message bus.

## Installation

Copy `plugin.ts` to your OpenCode project's `.opencode/plugins/` directory, or install as a dependency:

```bash
npm install opencode-nats
```

## Configuration

Set the NATS server URL via environment variable:

```bash
export OPENCODE_NATS_URL=nats://localhost:14222
```

Defaults to `nats://localhost:14222` if not set.

## Subject Convention

Messages follow the `{target}.in.{from}` convention:

| Subject | Direction | Purpose |
|---------|-----------|---------|
| `opencode.in.*` | Inbound | Messages addressed to OpenCode. Leaf = sender ID. |
| `animus.in.opencode` | Outbound | Send messages to Animus. |
| `claude.in.opencode` | Outbound | Send messages to Claude Code. |
| `nexibot.in.opencode` | Outbound | Send messages to Nexibot. |

## Tools

| Tool | Description |
|------|-------------|
| `nats_publish` | Publish a message to a NATS subject |
| `nats_request` | Send a request and wait for a reply (request/reply pattern) |
| `nats_subscribe` | Subscribe to a subject and collect messages |
| `nats_status` | Check NATS connection status |

## License

MIT
