---
module: 11
title: "Defining Prompts"
course: introduction-to-mcp
topics: [MCP prompts, prompt templates, slash commands, prompt engineering]
---

# Defining Prompts

Prompts in MCP servers let you define pre-built, high-quality instructions that clients can use instead of writing their own prompts from scratch. Think of them as carefully crafted templates that give better results than what users might come up with on their own.

## Why Use Prompts?

Here's the key insight: users can already ask Claude to do most tasks directly. For example, a user could type "reformat the report.pdf in markdown" and get decent results. But they'll get much better results if you provide a thoroughly tested, specialized prompt that handles edge cases and follows best practices.

As the MCP server author, you can spend time crafting, testing, and evaluating prompts that work consistently across different scenarios. Users benefit from this expertise without having to become prompt engineering experts themselves.

## Building a Format Command

Let's implement a practical example: a format command that converts documents to markdown. Users will type `/format doc_id` and get back a professionally formatted markdown version of their document.

The workflow looks like this:

1. User types `/` to see available commands
2. They select format and specify a document ID
3. Claude uses your pre-built prompt to read and reformat the document
4. The result is clean markdown with proper headers, lists, and formatting

## Defining Prompts

Prompts use a similar decorator pattern to tools and resources.
