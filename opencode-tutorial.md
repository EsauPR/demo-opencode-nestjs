## Instalation

```bash
curl -fsSL https://opencode.ai/install | bash
```

## Setup

Condigure LLM provider

```bash
opencode auth login
```

And run OpenCode

```bash
opencode
```

Next, initialize OpenCode for the project by running the following command.

```opencode project
/init
```

This will get OpenCode to analyze your project and create an AGENTS.md file in the project root.

- Scan the directory
- Build lint and test commands
- Code style guidelines
- Scan for cursor or copilot rules
- Create AGENTS.md file

## GitHub integration

```bash
opencode github install
```

This install de app on GitHub and create the main workflow to interact with.

## Models

Read: https://opencode.ai/docs/models/

Select a model

```
/models
```

config a provider

```bash
opencode auth login
```

## Tools

Tools are the main way on how the LLM can perform actions in the code.

- bash: allows the LLM to run terminal commands
- edit: performs precise edits to files by replacing exact text matches
- write: allow the LLM to create new files
- read: reads files and returns their contents
- grep: Fast content search across your codebase
- glob: search for files using glob patterns
- list: lists directory contents
- patch: useful for applying diffs and patches from various sources
- todowrite: creates and updates task lists to track progress during complex operations
- todoread: reads the current todo list state
- webfetch: allows the LLM to fetch and read web pages

**Custom tools**:
Custom tools let you define your own functions that the LLM can call

## MCP Servers

You can add external tools to OpenCode using the Model Context Protocol, or MCP.

OpenCode supports both:

Local servers
Remote servers

## Rules

You can provide custom instructions to opencode by creating an AGENTS.md file.

- Project
- Global: `~/.config/opencode/AGENTS.md`

### Custom rules

- Global: `~/.config/opencode/opencode.json`
- Project: `opencode.json`

```json
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": ["CONTRIBUTING.md", "docs/guidelines.md", ".cursor/rules/*.md"]
}
```

This allows you and your team to reuse existing rules rather than having to duplicate them to AGENTS.md.

### Referencing External Files

- Using `opencode.json`
- Using explicit reference on `AGENTS.ms`: `@test/testing-guidelines.md`


## Agents

### Primary

- Build
- Plan

Change using TAB

### Subagents

Subagents are specialized assistants:

- primary agents can invoke for specific tasks.
- invoke them by @ mentioning them in your messages.

Two ways to reference in:

- `opencode.json`
- `.opencode/agent/{agent}.md`


Create a agent

```bash
opencode agent create
```

### Uses cases

- Build agent: Full development work with all tools enabled
- Plan agent: Analysis and planning without making changes
- Review agent: Code review with read-only access plus documentation tools
- Debug agent: Focused on investigation with bash and read tools enabled
- Docs agent: Documentation writing with file operations but no system commands


## Commands

Custom commands let you specify a prompt you want to run when that command is executed in the TUI

```
/my-command
```

- You can pass arguments
- You can execute a explicit shell command
- Support file references


## Formaters

OpenCode automatically formats files after they are written or edited using language-specific formatters

## LSP servers

OpenCode integrates with your Language Server Protocol (LSP) to help the LLM interact with your codebase. It uses diagnostics to provide feedback to the LLM.

Read:

https://opencode.ai/docs/lsp/


## MCP servers

You can add external tools to OpenCode using the Model Context Protocol, or MCP.

Read:

https://opencode.ai/docs/mcp-servers/
