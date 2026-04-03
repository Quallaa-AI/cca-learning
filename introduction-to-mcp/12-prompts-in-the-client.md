---
module: 12
title: "Prompts in the Client"
course: introduction-to-mcp
topics: [client prompt integration, list_prompts, prompt variables]
---

# Prompts in the Client

The final step in building our MCP client is implementing prompt functionality. This allows us to list all available prompts from the server and retrieve specific prompts with variables filled in.

## Implementing List Prompts

The `list_prompts` method is straightforward. It calls the session's list prompts function and returns the prompts.
