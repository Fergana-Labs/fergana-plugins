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
