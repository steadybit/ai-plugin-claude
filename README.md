# Steadybit plugin for Claude

[Steadybit](https://steadybit.com) is a chaos engineering platform: teams inject faults such as latency, CPU stress or
pod failures into their own systems and check that those systems keep working. This plugin connects Claude to your
Steadybit account so you can work with it in conversation:

- Explore your environments, teams and targets (hosts, containers, Kubernetes resources, cloud resources) and the
  available attacks, checks and load tests.
- Assess reliability: service risk scores, reliability advice, and trends of experiment runs and risk over time.
- Design experiments from a description, from Steadybit's suggestions or from templates, and save or update them.
- Run an experiment after you confirm it, cancel a running one, and get an explanation of a run.

## Get started

Install the plugin, connect Steadybit (you sign in with your Steadybit account; a new user can create a free 30-day
trial with sample data on the way) and ask:

> Get me started with Steadybit

In Claude Code:

```sh
/plugin marketplace add steadybit/ai-plugin-claude
/plugin install steadybit@steadybit
```

Then run `/mcp`, pick `steadybit` and sign in, or start with `/steadybit:get-started`.

## What's inside

| Path | What |
|---|---|
| `.mcp.json` | Steadybit's remote MCP server, `https://platform.steadybit.com/mcp` (OAuth, your own Steadybit permissions) |
| `skills/get-started/` | First steps after connecting: finds out where you stand and walks you to a first result |
| `skills/steadybit/` | How to explore, design and run experiments, with the safety rules for running them |
| `.claude-plugin/` | Plugin manifest and the marketplace this repository serves |

Every action uses your own Steadybit permissions, and running an experiment injects real faults, so Claude asks for
confirmation before each run. More on the MCP server: [Remote MCP server](https://docs.steadybit.com/integrate-with-steadybit/remote-mcp-server).

## Development

- The skills here are also used by Steadybit's plugin for ChatGPT and Codex, whose build copies them from this
  repository. Keep them free of anything Claude-specific.
- Validate before releasing: `claude plugin validate . --strict --profile directory`. CI runs the same on every push
  and pull request (`.github/workflows/validate.yml`); it needs no login.
- To try a change against Steadybit's dev platform, run `claude --plugin-dir .` with the URL in `.mcp.json` temporarily
  set to `https://platform.dev.steadybit.com/mcp`.

## License

[MIT](LICENSE)
