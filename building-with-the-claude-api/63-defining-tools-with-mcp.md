---
module: 63
title: "Defining Tools with MCP"
course: building-with-the-claude-api
topics: ["FastMCP", "tool decorators", "MCP SDK", "server creation"]
---
# Defining tools with MCP

Building an MCP server becomes much simpler when you use the official Python SDK. Instead of manually writing complex JSON schemas for tools, the SDK handles all that complexity for you with decorators and type hints.

In this example, we're creating an MCP server that manages documents stored in memory. The server will provide two essential tools: one to read document contents and another to update them through find-and-replace operations.

## Setting Up the MCP Server

The Python MCP SDK makes server creation incredibly straightforward. You can initialize a complete MCP server with just one line:

    from mcp.server.fastmcp import FastMCP

    mcp = FastMCP("DocumentMCP", log_level="ERROR")

For this implementation, documents are stored in a simple Python dictionary where keys are document IDs and values contain the document content:

    docs = {
        "deposition.md": "This deposition covers the testimony of Angela Smith, P.E.",
        "report.pdf": "The report details the state of a 20m condenser tower.",
        "financials.docx": "These financials outline the project's budget and expenditure",
        "outlook.pdf": "This document presents the projected future performance of the",
        "plan.md": "The plan outlines the steps for the project's implementation.",
        "spec.txt": "These specifications define the technical requirements for the equipment"
    }

## Tool Definition with Decorators

The SDK transforms tool creation from a verbose process into something clean and readable. Instead of writing lengthy JSON schemas, you use Python decorators and type hints.

### Creating the Document Reader Tool

The first tool allows Claude to read any document by its ID. Here's the complete implementation.
