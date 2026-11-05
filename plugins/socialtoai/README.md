# SocialToAI plugin

Skills that let Claude read public social media and hand back finished work: a brand report, a comment analysis, a creator shortlist, a WeChat Official Account digest. It reads public content and does not post.

## Install

```bash
/plugin install socialtoai --marketplace socialtoai/socialtoai-skills
/mcp
```

Then pick socialtoai in `/mcp` and sign in.

## What this plugin contains

- **Nine task skills** in `skills/`, each a whole job with a stated cost and output format.
- **One reference skill**, `socialtoai`, listing every platform, call and price.
- **An MCP server reference** (`.mcp.json`) to `https://mcp.socialtoai.com/mcp`, hosted by SocialToAI.

## What it sends and where

The skills call the SocialToAI MCP server. Your AI sends each call's parameters, such as search terms and links, to that server, which answers from content publicly visible on 18 platforms. There are no hooks, scripts, or local programs in this plugin. No platform account of yours is used, and no key is stored by the plugin: you sign in with OAuth.

Sign-in gives 100 free credits, no card. Calls are charged in prepaid credits, and failed calls are free. Each answer states what it cost. Privacy: https://socialtoai.com/privacy/ . Terms: https://socialtoai.com/terms/ . Support: support@socialtoai.com.

Published by the SocialToAI team. MIT licence.
