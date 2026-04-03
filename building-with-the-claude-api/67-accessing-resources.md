---
module: 67
title: "Accessing Resources"
course: building-with-the-claude-api
topics: ["resource reading", "document mentions", "prompt injection", "MCP client resources"]
---
# Accessing resources

Resources in MCP allow your server to expose data that can be directly included in prompts, rather than requiring tool calls to access information. This creates a more efficient way to provide context to AI models like Claude.

## Understanding Resource Requests

When you've defined resources on your MCP server, your client needs a way to request and use them. The client acts as a bridge between your application and the MCP server, handling the communication and data parsing automatically.

The flow is straightforward: when a user wants to reference a document (like typing "@report.pdf"), your application uses the MCP client to fetch that resource from the server and include its contents directly in the prompt sent to Claude.

## Implementing Resource Reading

The core functionality requires a read_resource function in your MCP client. This function takes a URI parameter identifying which resource to fetch.
