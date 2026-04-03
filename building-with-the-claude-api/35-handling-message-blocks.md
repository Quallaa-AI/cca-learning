---
module: 35
title: "Handling Message Blocks"
course: building-with-the-claude-api
topics: ["message blocks", "tool-enabled requests", "multi-block responses"]
---
# Handling message blocks

When working with Claude's tool functionality, you'll encounter a new type of response structure that's different from the simple text responses you've seen before. Instead of just getting back a single text block, Claude can now return multi-block messages that contain both text and tool usage information.

## Making Tool-Enabled API Calls

To enable Claude to use tools, you need to include a tools parameter in your API call. Here's how to structure the request:

    messages = []
    messages.append({
        "role": "user",
        "content": "What is the exact time, formatted as HH:MM:SS?"
    })
