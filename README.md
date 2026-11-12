# Embrasure

## Your data warehouse, analytics, and beautiful dashboards, one prompt away

Get started in 30 seconds. Tell your agent what you want to know, connect your data, and let Embrasure set up your warehouse.

- Bring your databases and business tools into one place.
- Ask questions in plain English and get answers from your data.
- Build beautiful dashboards for revenue, product usage, and operations.
- Keep data in sync and give your team shared definitions for the metrics that matter.

Designed for billions of rows, so you can start small and keep growing.

## Get started

You'll need an Embrasure account and workspace. Your workspace role determines
which setup, source, and dashboard actions you can use. For account or workspace
access, [contact support](https://embrasure.ai/support).

Enable the plugin in your editor. When prompted, sign in to Embrasure in your
browser and select your workspace. Then ask:

> Set up my data warehouse and help me answer my first question.

Already connected? Use that connection. You don't need to reinstall MCP or run a
separate setup command. Source approval happens in your browser. Initial sync
time depends on the source and data volume.

You can also ask:

- Connect my revenue data and build a dashboard.
- What changed in our business this week?

## If the Embrasure tools are missing

Some clients hide a failed MCP sign-in from the agent, so the tools just don't
appear. Check the connection status:

- Codex: `codex mcp list`. If Auth shows `Not logged in`, run
  `codex mcp login embrasure`. Codex adds the tools to the same chat.
- Claude Code: `claude mcp list`. If it shows `Needs authentication`, run
  `claude mcp login plugin:embrasure:embrasure`, or use `/mcp`.

If Embrasure isn't listed or is disabled, enable the plugin. If it shows a saved
sign-in but the tools are still missing, check `https://api.embrasure.ai/health`.
A `200` means you should reconnect once; anything else means Embrasure is unavailable.
If the tools still don't appear, [contact support](https://embrasure.ai/support).

## Install in Claude Code

```text
/plugin marketplace add EmbrasureAI/embrasure-plugins
/plugin install embrasure@embrasure
```

The Cursor marketplace submission is being prepared. Use the local preview below.

## Local preview

For Claude Code, from the plugin folder:

```sh
claude --plugin-dir .
```

For Cursor, copy the plugin folder into `~/.cursor/plugins/local/embrasure`, reload
Cursor, and check Customize for the skill and MCP server. Authenticate the
Embrasure connection before asking your first question.

## Connection and privacy

The plugin connects to `https://embrasure.ai/api/mcp` using browser OAuth. It has
no install scripts, local background process, embedded credentials, or required
API keys. Tool calls send the requested inputs to Embrasure and return workspace
data to your agent. Access follows the connected user's workspace permissions.

Connected tables can contain personal data. Embrasure stores imported data,
saved definitions, and dashboards for the workspace; removing a connector stops
future syncs but does not erase previously imported data. Retention, subprocessors,
and deletion requests are described in the privacy policy below.

Source connections, ingestion, saved definitions, and dashboard edits can change
workspace state. The agent uses previews where supported and deletes a dashboard, chart,
dataset, or ingestion connection only when asked. Keep credentials in the browser connection flow.

[Documentation](https://docs.embrasure.ai/mcp) ·
[Privacy policy](https://embrasure.ai/privacy) ·
[Terms](https://embrasure.ai/terms) ·
[Support](https://embrasure.ai/support)

## License

The plugin configuration, bundled skill, and documentation are MIT licensed.
The Embrasure service remains subject to its terms. Brand names and logos are
not licensed for use as your own branding.
