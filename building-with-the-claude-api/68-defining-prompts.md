---
module: 68
title: "Defining Prompts"
course: building-with-the-claude-api
topics: ["MCP prompts", "prompt templates", "prompt decorators", "reusable instructions"]
---
# Defining prompts

Prompts in MCP servers let you define pre-built, high-quality instructions that clients can use instead of writing their own prompts from scratch. Think of them as carefully crafted templates that give better results than what users might come up with on their own.

## Why Use Prompts?

Let's say you want Claude to reformat a document into markdown. A user could just type "convert report.pdf to markdown" and it would work fine. But they'd probably get much better results with a thoroughly tested prompt that includes specific instructions about formatting, structure, and output requirements.

The key insight is that while users can accomplish these tasks on their own, they'll get more consistent and higher-quality results when using prompts that have been carefully developed and tested by the MCP server authors.

## How Prompts Work

Prompts define a set of user and assistant messages that clients can use directly. When a client requests a prompt, your server returns a list of messages that can be sent straight to Claude.

The basic structure looks like this:

- Define prompts using the `@mcp.prompt()` decorator
- Add a name and description for each prompt
- Return a list of messages that form the complete prompt
- These prompts should be high quality, well-tested, and relevant to your MCP server's purpose

## Building a Format Command

Here's how to implement a document formatting prompt. First, you'll need to import the base message types:

    from mcp.server.fastmcp import base

Then define your prompt function.
