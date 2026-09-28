---
name: socialtoai-setup
description: Use when the user asks to install, connect, configure or troubleshoot SocialToAI MCP, including 帮我配置 SocialToAI, first-use setup, connection defaults and platform exclusions. Do not use for ordinary social research, installing an unrelated MCP server, obtaining supplier keys, account billing decisions or requests to bypass tool permissions.
metadata:
  version: "0.1.0"
  contract: "v1"
---

# Set up SocialToAI

Create a working client connection and verify the settings requested by the user. Use the public [quickstart](https://socialtoai.com/docs/quickstart/) and [platform guide](references/platforms.md); check the current client's documented configuration rather than guessing its file format.

## Connect

1. Identify the client and inspect its existing SocialToAI connection when authorized. Preserve existing settings. Use Access at `https://socialtoai.com/console/` for sign-in and the personal Connector. The user should enter the secret directly into the client's credential field or environment; never ask them to paste it into the conversation.
2. The Remote HTTP MCP endpoint is `https://mcp.socialtoai.com/mcp`. Prefer `Authorization: Bearer <Key>` when supported; URL-only clients use the personal `?key=` URL from Access. Treat the entire personal URL as a secret. Use the current quickstart for Cursor's official install prompt or the client's CLI command. Installation is complete only after the client discovers the connection.
3. If you cannot write client settings, provide the exact client-specific manual steps and the nonsecret endpoint. Explain the remaining user action; do not claim the file was written or the connection tested.
4. Call free `capabilities(platform=reddit)` or a nonexcluded supported platform. The default Connector has six core verbs plus `capabilities`; do not use `account` or `ping` as the default connection test. On authentication failure, check the credential locally and use Access recovery/rotation if needed. Never echo it into an error report.

## Set requested connection preferences

Only change preferences the user requested or accepted. Build the query with a URL encoder; preserve a URL-based Key privately. Do not interpolate a raw JSON string into a shell command.

```javascript
const connection = new URL("https://mcp.socialtoai.com/mcp");
connection.searchParams.set("default_parameters", JSON.stringify({
  search: { sort: "latest", time_range: "7d", count: 5 }
}));
connection.searchParams.set("exclude_platforms", "x");
// Nonsecret configuration only. Supply the Key through the client separately.
```

The example expresses “latest, last week, five search results; exclude X.” Omit settings the user did not ask for. Allowed defaults: search `type/sort/time_range/content_type/scope/count`, trending `category`. Do not default the query, platform, IDs, cursor, Key, grants or budget. Explicit tool arguments override connection defaults, which override ordinary contract defaults. Preferences are connection-local; they do not change HTTP calls or other clients.

`exclude_platforms` is a comma-separated list of unique platform IDs. Explicit requests for an excluded platform fail free. `platforms=all` only subtracts from the default five; it never fills the set from other platforms. `packs` filters permissions already granted, and adding it cannot grant access. Do not add packs to complete basic setup. Unknown/duplicate query fields and invalid values fail instead of being silently accepted.

## Verify and hand back

1. Reconnect/reload the MCP configuration. Confirm tool discovery and `capabilities` reflect the selected exclusion. Report the endpoint and preferences with any Key redacted, not the secret URL or credential.
2. A free discovery call cannot prove paid search filters were applied. Before a paid check, inspect the actual console Balance and obtain a finite call budget if one is not already authorized. Use a supported nonexcluded platform and a harmless user-relevant query; leave intended default arguments absent. Inspect `applied_params`, `warnings` and `billing`. If the platform downgrades the requested filter, explain its actual behavior.
3. Stop before insufficient budget, on unauthorized credentials or on ambiguous timeout; do not loop retries or add extra paid verification. If a paid check cannot run, distinguish “connected” from “defaults verified.”
4. Summarize connection/discovery status, requested and effective preferences, credits spent and any remaining manual step. Point to local Skills installation/fork instructions if useful. Removing a Skill does not revoke the Connector; use Access to rotate a compromised Key.

Example: an authorized funded check omits sort/time_range and verifies `latest/7d` in the applied result. Counterexample: a successful free capabilities call alone does not prove the paid search worked or the user has funds.
