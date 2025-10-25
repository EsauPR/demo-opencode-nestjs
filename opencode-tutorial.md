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
