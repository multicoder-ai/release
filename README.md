# Multicoder - one UI for every coding agent

Use whichever coding agent works best. One UI, full VS Code integration for Claude Code, Codex, Copilot, OpenCode, Qwen, Pi, Hermes and many others (via ACP).

![Multicoder running in VS Code with the agent picker open](https://multicoder.dev/resources/images/screen-agents.png)

Install Multicoder if you switch between multiple agents, want more visibility, better VS Code integration, or just prefer a graphical interface over the terminal. You get:

- 1-click install for 35+ agents from the [ACP registry](https://agentclientprotocol.com/get-started/registry)
- all your agent sessions in one place - CLI history included
- per-agent session params: model, thinking level, permission mode
- full session introspection: outline, reasoning blocks, tool calls, subagent runs
- changed files with aggregated and per-change diffs
- per-file change history - which session last touched it
- works in remote workspaces (SSH, WSL, containers)

## How it works

Multicoder talks to agents over the [Agent Client Protocol](https://agentclientprotocol.com) (ACP), an open protocol for connecting coding agents to editors. Many agents support ACP natively ([Copilot](https://docs.github.com/en/copilot/reference/copilot-cli-reference/acp-server), [OpenCode](https://opencode.ai/docs/acp/), [Qwen](https://qwenlm.github.io/qwen-code-docs/en/users/configuration/settings/#command-line-arguments), [Hermes](https://hermes-agent.nousresearch.com/docs/user-guide/features/acp)); for the rest ([Claude Code](https://github.com/agentclientprotocol/claude-agent-acp), [Codex](https://github.com/agentclientprotocol/codex-acp), [Pi](https://github.com/svkozak/pi-acp)) a wrapper translates the agent's SDK to ACP. Agents still run as local subprocesses, in your environment, with your own accounts and API keys. Multicoder just provides a common UI and a management layer.

## Get started

1. Install [Multicoder](https://marketplace.visualstudio.com/items?itemName=multicoder.multicoder) from the VS Code marketplace.
2. Open the Multicoder chat panel. Agents already installed on your machine are detected automatically.
3. To add one, pick **Install Agent** from the agent dropdown and choose from the registry:

    ![Agent install picker](https://multicoder.dev/resources/images/install-agent.png)

4. Select the agent, type a prompt. If the agent needs authentication, the chat panel walks you through it.

## Features

![Multicoder UI overview](https://multicoder.dev/resources/images/ui-elements.png)

### Watch the agent work

The transcript shows everything: reasoning blocks, tool calls (collapsed until you open them), subagent runs with their own instructions and output. The Outline view jumps to any point in a long session.

### Every edit tracked

The Changes view lists the files a session touched. The Timeline shows each file's change history. Open the aggregated diff for a file, or step through individual edits with prev/next in the editor.

### Permissions

Tool calls wait for your approval - allow or reject inline. A permission mode selector sets how much the agent may do on its own.

![Permission request](https://multicoder.dev/resources/images/permissions-request.png)

### Sessions

Running and finished sessions in one list, with time filters. History from the agent's CLI syncs in. Sessions survive window reloads and workspace switches - agents keep working.

### Tune per session

Model, thinking level, and permission mode selectors sit under the input. Choices persist per agent.

### Auth built in

When an agent needs credentials, the chat panel shows that agent's options - subscription login or API key. No config files to hunt down.

![Authentication options](https://multicoder.dev/resources/images/auth-required.png)

### Works where VS Code works

Remote workspaces included - the agent runs on the remote host, next to your code.

## Advanced configuration

Settings live in `~/.multicoder/settings.json` (schema-validated; open it with the **Multicoder: Edit Settings** command). Any ACP-compatible agent can be added by hand under `agentServers` - command, args, env:

![Custom agent configuration](https://multicoder.dev/resources/images/agent-config.png)

Agent sessions are managed by a small local server that outlives the VS Code window - that's what keeps agents working across reloads. By default it picks a free port; set `"port"` in `settings.json` to pin one (useful for firewall rules). The **Multicoder: Stop Server** command shuts it down.

## Feedback

- Questions and ideas: [GitHub Discussions](https://github.com/multicoder-ai/vscode-release/discussions)
- Bugs: [GitHub Issues](https://github.com/multicoder-ai/vscode-release/issues)
