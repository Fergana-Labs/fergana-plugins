# Fergana Labs — Claude Code Plugins

Claude Code plugins by [Fergana Labs](https://ferganalabs.com).

## Install

**Step 1:** Add the marketplace:
```
/plugin marketplace add Fergana-Labs/fergana-plugins
```

**Step 2:** Install any plugin:
```
/plugin install cohort-analysis@fergana-labs
```

**Step 3:** Restart Claude Code to activate the plugin.

## Available Plugins

| Plugin | Description |
|--------|-------------|
| **cohort-analysis** | Interactive cohort analysis dashboard — engagement retention, revenue/GP cohorts, CAC/LTV payback. Point at CSV, Excel, or a database and get live charts. |
| **general-manager** | Autonomous agent orchestrator — delegate complex tasks to persistent sub-agents that work in the background. |

## General Manager — Quick Start

**One-prompt install:**
```
/plugin marketplace add Fergana-Labs/fergana-plugins && /plugin install general-manager@fergana-labs
```

Restart Claude Code after installing. The CLI (`gm`) auto-installs on first session.

**What it does:** Gives Claude a team. When you have a complex task — refactor, feature build, monitoring, multi-file changes — Claude decomposes it and spawns persistent sub-agents that work in the background. You keep working while they handle it.

**How to use:**
- Just describe a big task naturally — Claude will suggest delegating it
- Or explicitly: `/general-manager:manage "refactor the auth module"`
- Check progress: `/general-manager:status` or "how's the task going?"
- Stop everything: `/general-manager:stop`

**Agent definitions:** Create `.gm/agents/<name>.md` in your project to define specialized agent types (monitor, reviewer, etc.). Spawn them by name: Claude will use `gm _mgr spawn --agent monitor "watch the logs"`.

**Scheduling:** Sub-agents can run on cron schedules — recurring or one-shot.

## Adding a New Plugin

1. Create the plugin in its own repo (e.g., `Fergana-Labs/new-plugin`)
2. Add an entry to `.claude-plugin/marketplace.json`:
   ```json
   {
     "name": "new-plugin",
     "source": {
       "source": "github",
       "repo": "Fergana-Labs/new-plugin"
     },
     "description": "What it does",
     "version": "1.0.0",
     "author": { "name": "Fergana Labs" }
   }
   ```
3. Push to this repo
