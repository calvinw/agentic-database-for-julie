# Agentic Codespace

A GitHub Codespace with three AI coding agents installed with `npm install -g`:

| Agent | npm package | Command |
|---|---|---|
| OpenCode | `@opencode/cli` | `opencode` |
| Codex | `@openai/codex` | `codex` |
| Claude Code | `@anthropic-ai/claude-code` | `claude` |

## Start it

Click **Code → Codespaces → Create codespace on main**. The three agents are installed
while the codespace is being created.

The Codespace also installs [Dolt](https://www.dolthub.com/docs/introduction/installation/)
2.7.3, a version-controlled SQL database. Run `dolt version` to verify the installation.
Use `dolt` for database commands or `dolt sql-server` to start a MySQL-compatible server
from a Dolt database directory.

## Shop database and reports

Our database is `calvinw/calvin-and-julie-retail-shop` on DoltHub.
To download a working copy into a new workspace, run:

```bash
dolt clone calvinw/calvin-and-julie-retail-shop
```

The downloaded database stays separate from this GitHub repository. Dolt manages
its information and history; this repository holds the workspace setup and reports.

The `exports` folder contains:

- `calvin-and-julie-shop-summary.pptx`: nine presentation slides explaining the current data.
- `products-never-bought.xlsx`: six products with no recorded purchases, plus the SQL used.
- `charts/`: charts of product popularity, customer spending, and products with no purchases,
  along with the numbers used to create them in `chart-data.json`.

These reports are saved snapshots, so they do not update automatically when the
database changes. The recorded purchases cover March 10 through April 5, 2025.
Spending totals use current product prices; the database does not specify a currency.

## Sign in

Each agent asks you to log in the first time you run it:

- `opencode`: run `opencode auth login` and pick a provider
- `codex`: sign in with your ChatGPT account, or set `OPENAI_API_KEY`
- `claude`: sign in with your Claude account, or set `ANTHROPIC_API_KEY`

To keep API keys out of the repo, add them as
[Codespaces secrets](https://github.com/settings/codespaces) instead of typing them in.
