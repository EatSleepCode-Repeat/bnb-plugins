# 🧩 bnb-shell Plugin Registry

Official registry and plugin monorepo for [bnb-shell](https://github.com/EatSleepCode-Repeat/bnb).

## 📂 Repository Structure

- `registry.json`: The central catalog of available plugins fetched by `bnb plugin store`.
- `official/`: Monorepo containing all official starter plugins.

## Plugin Actions

Each `plugin.toml` action is a shell command that bnb inserts into the command line when selected from the command palette. The user reviews and runs it; selection does not execute it immediately. Actions do not receive positional arguments or prompt for input, so keep commands self-contained and do not use placeholders such as `$1`. Keep registry descriptions and plugin manifest names/descriptions in sync.

Plugins are command shortcuts, not sandboxed extensions. Users should inspect an action and its command before running it, and plugin authors should avoid destructive defaults.

## 🚀 Submitting a Community Plugin

### Option A: Submit an Official Plugin (Monorepo)

1. Fork this repository.
2. Create a folder in `official/<your-plugin-name>/`.
3. Add a `plugin.toml` file defining your plugin actions.
4. Add your entry to `registry.json` with `"type": "official"` and `"path": "official/<your-plugin-name>"`.
5. Open a Pull Request!

### Option B: Register an External Repository

If you maintain your plugin in your own GitHub repository:

1. Fork this repository.
2. Add an entry to `registry.json`:
   ```json
   {
     "name": "your-plugin-name",
     "description": "A short description of what it does",
     "author": "YourName",
     "category": "Tools",
     "type": "external",
     "repo": "your-username/your-plugin-repo"
   }
   ```
